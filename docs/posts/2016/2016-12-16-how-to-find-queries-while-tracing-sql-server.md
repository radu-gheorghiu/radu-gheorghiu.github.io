---
title: "How to find queries while tracing in SQL Server"
authors: 
    - radugheorghiu
date: 
    created: 2016-12-16
    updated: 2024-01-05
tags: []
categories: ["Data Engineering", "SQL Server"]
slug: "how-to-find-queries-while-tracing-sql-server"
---

# **How to find queries while tracing in SQL Server**

Let’s say you’re working on a DEV database and you’re trying to get some information from **SQL Server Profiler** about the number of READS or WRITES that your queries are making and / or CPU time spent or other metrics. On a database with a lot of users running queries on the DB at the same time this can be difficult. But luckily there’s an easy fix to find those queries.
<!-- more -->
So, if you’re running queries from SSMS and want to identify your queries much easier in SQL Server Profiler you can filter the trace by Server Process ID (SPID). Now, in order to get this value let’s remember that each tab in SSMS has its own session / process communicating with the DB, so each tab will have a different Server Process ID.

<div align="center">
    <img src="/assets/blog_images/2016-12-16-how-to-find-queries-in-profiler/sql_server_profiler.png" alt="execution_plan">
</div>

So, to find out the corresponding SPID for a specific query tab all you need to do is:

> SELECT @@SPID

Be mindful though, that this is available only for SQL Server 2008 and up.

I hope this saves you a lot of time, it certainly did it for me, whenever I had to use SQL Server Profiler on a busy database.