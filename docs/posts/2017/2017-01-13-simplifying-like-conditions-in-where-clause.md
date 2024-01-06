---
title: "Simplifying LIKE conditions in WHERE clause"
authors: 
    - radugheorghiu
date: 
    created: 2017-01-13
    updated: 2024-01-06
tags: []
categories: ["Data Engineering", "SQL Server"]
slug: "simplifying-like-conditions-in-where-clause"
---

# **Simplifying LIKE conditions in WHERE clause**

Let’s say you have a query with a long WHERE clause in which you’re checking if a set of characters exist in a column and the only way you’re thinking of doing this is with a set of LIKE conditions in your where clause, like below:

<!-- more -->

```sql title="Simplifying LIKE conditions in WHERE clause"
DECLARE @tbl TABLE (col1 VARCHAR(10));
 
INSERT @tbl
VALUES ('abc / 123')
    , ('abc , 123')
    , ('abc & 123')
    , ('abc : 123')
    , ('abc ^ 123');
 
SELECT *
FROM @tbl
WHERE col1 LIKE '%/%'
    OR col1 LIKE '%,%'
    OR col1 LIKE '%&%'
    OR col1 LIKE '%:%'
    OR col1 LIKE '%^%';
```

But if you have to check for a large number of parameters then the query can get very big and it can look very messy.

Thankfully, there’s a way you can achieve the same logic as with multiple **LIKE** and **OR** conditions combined. All you have to do is to simplify the **LIKE** condition and put the characters you’re searching for into square brackets in a single **LIKE** clause, just like in the following example.

```sql title="The simplified LIKE condition"
SELECT *
FROM @tbl
WHERE col1 LIKE '%[/&,^:]%';
```