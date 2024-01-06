---
title: "No errors raised for overflowing data when using CHAR and VARCHAR data types in SQL Server"
authors: 
    - radugheorghiu
date: 
    created: 2017-08-23
    updated: 2024-01-06
tags: []
categories: ["Data Engineering", "SQL Server"]
slug: "no-errors-raised-for-overflowing-data-when-using-char-and-varchar-data-types-in-sql-server"
---

# **No errors raised for overflowing data when using CHAR and VARCHAR data types in SQL Server**

It’s not always possible to predict when problems will occur with your database’s architecture and it’s always a shock when it does, especially because most of the unexpected problems occur after a deploy to production (in this scenario I’ve inherited the database, I wasn’t the one to design it, or at least not this failing part).

The latest problem I’ve faced was with data which was 9 characters long attempted to be stored into a CHAR(8) column. Have a look and test the below script to see what happens:

<!-- more -->

```sql title="No errors raised for overflowing data when using CHAR and VARCHAR data types in SQL Server"
declare @testInsertOverflow table (col varchar(3));
 
insert into @testInsertOverflow values ('1'), ('22'), ('333');
 
select *
from @testInsertOverflow
 
declare @x int = 123456;
 
insert into @testInsertOverflow
select @x;
 
insert into @testInsertOverflow (col) values (@x);
 
select *
from @testInsertOverflow;
```

If you would have asked me before, I would have said that the 2nd and 3rd INSERT statements would fail since there would be an obvious truncation of data and we would get the infamous **“Arithmetic overflow error converting expression to data type…”**

But you don’t, and instead of throwing an error, SQL Server will insert rows with asterisks.

<div align="center">
    <img src="/assets/blog_images/2017-08-23-no-errors-overflow-data/error-217x300.png" alt="Overflowing data" title="Overflowing data" />
</div>

This happens for the **CHAR** and **VARCHAR** datatypes, while **NCHAR** and **NVARCHAR** will throw the expected truncation error.

It happens with all types of tables: variables, temporary and persisted and it happens even in ***SQL Server 2016**.

***Disclaimer:***

I’m not sure if this issue is known or not, I couldn’t really find any posts about this specific problem and that’s why I decided to write this short article to then more easily share and maybe raise awareness and a red-flag about this problem so others can check they environments and plan accordingly, before the problem occurs.

If anyone has experience with this or knowledge about why this happens I’d really appreciate it if you could add a comment.