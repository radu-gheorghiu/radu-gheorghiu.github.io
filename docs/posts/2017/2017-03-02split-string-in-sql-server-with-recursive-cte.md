---
title: "Split string in SQL Server with Recursive CTE"
authors: 
    - radugheorghiu
date: 
    created: 2017-03-02
    updated: 2024-01-06
tags: []
categories: ["Data Engineering", "SQL Server"]
slug: "split-string-in-sql-server-with-recursive-cte"
---

# **Split string in SQL Server with Recursive CTE**

I decided to spend my time productively while I was monitoring a database restore, so I wanted to see if I could create a recursive CTE that could do a **split string in SQL Server** into words (or tokens), based on a certain delimiter.

And so I built the recursive CTE you can see next. Because I’m not 100% sure if the order of the words will be consistent throughout multiple executions I also added a “LVL” column to enforce the order of the rows, so that you can be 100% certain that the way the result is displayed is the actual order of the words in the phrase.

<!-- more -->

```sql title="Split string in SQL Server with Recursive CTE"
declare @string nvarchar(max) = 'the quick brown fox jumps over the lazy dog'
 , @delimiter nvarchar(10) = ' '

;with cte as (
    select @string phrase
        , cast('' as nvarchar(max)) word
        , 0 lvl

    union all

    select 
        ltrim(substring(phrase, charindex(@delimiter, phrase + ' ', 0 ), len(phrase))) phrase
        , ltrim(substring(phrase, 0, charindex(@delimiter, phrase + ' ', 0 ))) word
        , lvl + 1
    from cte
    where charindex(@delimiter, phrase + ' ', 0) <> 0
    and len(phrase) > 0)
select word
from cte
where len(word) > 0
order by lvl
```

As far as I have managed to test, this code should work on versions 2008R2 and up.

On to the next item on the SQL Bucket list!