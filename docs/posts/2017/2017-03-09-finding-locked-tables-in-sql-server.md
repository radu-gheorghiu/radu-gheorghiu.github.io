---
title: "Finding locked tables in SQL Server"
authors: 
    - radugheorghiu
tags: []
categories: ["Data Engineering", "SQL Server"]
slug: "finding-locked-tables-in-sql-server"
---

# **Finding locked tables in SQL Server**

Sometime this week I executed a **DELETE** query with an explicit **BEGIN TRANSACTION** on our DEV environment, the moved to another session to check some other results and forgot the transaction hanging. A few minutes later I left for home and by the time I was close to home a developer called me on my personal phone.

He was very stressed saying that he can’t do a `SELECT TOP 1 * FROM` OurBigTable and what can he do about it? It was at that point that I figured that I forgot the transaction open, without any **COMMIT** or **ROLLBACK** executed.
<!-- more -->

I tried to guide him through executing sp_who2 to find my transaction but there were too many details (rows and columns) there and I couldn’t remember the names of the relevant columns. So, I had to go back to work and sort things out, which I managed to fix in just 1 minute (find my session and kill it).

Based on this, I decided to write a more comprehensive script that would allow my developers find locked tables in SQL Server in order to kill any transactions (on our DEV environment) that might cause problems such as these or at least more easily find the query / person who is locking a table and ask if they can kill the query or not.

```sql title="Finding locked tables in SQL Server"
select locked_objects.*
from
    (select distinct
        isnull(est.text, '- No query executing at the moment -')                                        [Query]
        , db_name(tl.resource_database_id)                                                              [Database Name]
        , object_name(tl.resource_associated_entity_id)                                                 [Object Name]
        , tl.request_type                                                                               [Request Type]
        , er.command                                                                                    [Query Type]
        , er.status                                                                                     [Query Status]
        , es.host_name                                                                                  [Host Name]
        , es.program_name                                                                               [Program Name]
        , es.login_name                                                                                 [Login Name]
        , es.nt_user_name                                                                               [User Name]
        , er.start_time                                                                                 [Query Start Time]
        ,   cast(datediff(second, er.start_time, getdate()) / 60 as varchar(8)) + ' min ' +
            cast(datediff(second, er.start_time, getdate()) % 60 as varchar(8)) + ' sec'                [Query Running For]
        , er.percent_complete                                                                           [Query % Completed]
        , er.transaction_id                                                                             [Transaction ID]
        , case
            when er.command = 'ROLLBACK TRANSACTION'
                then ''
            else N'Kill ' + cast(es.session_id as nvarchar(100)) + ';'
          end  [Kill Command]
    from sys.dm_tran_locks tl
        inner join sys.dm_exec_sessions es on tl.request_session_id = es.session_id
        left join sys.dm_exec_requests er on es.session_id = er.session_id
        outer apply sys.dm_exec_sql_text (er.sql_handle) est
    where 1 = 1
        and tl.resource_type = 'OBJECT'
        and right(tl.request_mode, 1) = 'X'
        and tl.resource_associated_entity_id <= 2147483647) locked_objects
cross apply (   select name
                from sys.objects
                where OBJECT_ID(name, 'U') = OBJECT_ID(locked_objects.[Object Name], 'U')) checkObjects
where 1 = 1
    and checkObjects.name = 'tblB';     -- replace with table name HERE
```

This query will show you all the information that you need for this specific scenario to help you make the right decision. It shows you both what queries are running at the moment and locking the table or the locks that remained on a table after a query has been executed – probably an uncommitted transaction:

<div align="center">
    <img src="/assets/blog_images/2017-03-09-finding-locked-tables-in-sql-server/transaction.png" alt="Finding locked tables in SQL Server" />
</div>

And it also works for scenarios where a ROLLBACK is executing and keeping a resource locked, so you can see how much time it has been running for as well as the percentage of completion for that ROLLBACK operation so you will know in one glance approximately how much more you’ll need to wait.

<div align="center">
    <img src="/assets/blog_images/2017-03-09-finding-locked-tables-in-sql-server/rollback.png" alt="Finding locked tables in SQL Server" />
</div>

**Use it wisely!**