---
title: Renaming a SQL Server
author: matt40k
type: post
date: '2018-05-07T08:20:41+01:00'
url: /2018/05/renaming-a-sql-server/
description: 'So you''ve renamed your SQL Server, now stuff has started breaking. Yip.'
---
So you've renamed your SQL Server, but something isn't right.

{{< gist matt40k f384b0791fbc18549618ed8fbf39c258 "selectServername.sql" >}}

Returns the old name. 

The fix is simple.

{{< gist matt40k f384b0791fbc18549618ed8fbf39c258 "renameSql.sql" >}}

You just need to restart the SQL instance and @@servername will return the correct name.

More info on the [Microsoft Docs.](https://docs.microsoft.com/en-us/sql/database-engine/install-windows/rename-a-computer-that-hosts-a-stand-alone-instance-of-sql-server?view=sql-server-2017)

On a similar note, [Octopus Deploy](https://octopus.com) has similar annoyance, the server name doesn't update for the server node. Again simple fix for this simple annoyance:

{{< gist matt40k f384b0791fbc18549618ed8fbf39c258 "updateOctopusNode.sql" >}}

The other thing that can get missed is the SQL Jobs.

{{< gist matt40k f384b0791fbc18549618ed8fbf39c258 "renameSQLjobserver.sql" >}}
