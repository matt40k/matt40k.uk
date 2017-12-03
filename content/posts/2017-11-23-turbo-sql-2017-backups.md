---
title: Turbo SQL 2017 backups
author: matt40k
type: post
date: 2017-11-23T20:48:29+00:00
url: /2017/11/23/turbo-sql-2017-backups/
categories:
  - SQL Server
---

Another day, another Twitter awesome moment, <a href="http://www.sqlserverfaq.net/">Parikshit Savjani</a> was explaining how backups are now faster in SQL Server 2017.

{{< tweet 933560128250380288 >}}

For more info on how, <a href="https://blogs.msdn.microsoft.com/sql_server_team/how-we-made-backups-faster-with-sql-server-2017/">read his post</a>. TD;LR - The wait time before data is actually copied is reduced because the amount of buffers to scan is massively reduced.

> “...requires only 250 buffers to scan as opposed to 500 Million buffers with former algorithm...”

All newly created database on SQL 2017 will get this benefit, existing will require a little work

> alter database <dbname> set target_recovery_time = 60 seconds
