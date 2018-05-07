---
title: Renaming a SQL Server
date: '2018-05-07T08:20:41+01:00'
description: 'So you''ve renamed your SQL Server, now stuff has started breaking. Yip.'
---
So you've renamed your SQL Server, but something isn't right.

```
select @@servername
```

Returns the old name. 

The fix is simple.

```
sp_dropserver <old_name>;  
GO  
sp_addserver <new_name>, local;  
GO  
```

You just need to restart the SQL instance and @@servername will return the correct name.

More info on the [Microsoft Docs.](https://docs.microsoft.com/en-us/sql/database-engine/install-windows/rename-a-computer-that-hosts-a-stand-alone-instance-of-sql-server?view=sql-server-2017)

On a similar note, [Octopus Deploy](https://octopus.com) has similar annoyance, the server name doesn't update for the server node. Again simple fix for this simple annoyance:

```
USE OctopusDeploy
GO
DECLARE   @oldname varchar(255) = '<old_name>'  ,@newname varchar(255) = '<new_name>';UPDATE   dbo.OctopusServerNodeSET   name = @newnameWHERE   name = @oldname;
```

The other thing that can get missed is the SQL Jobs.

```
DECLARE   @oldname varchar(255) = '<old_name>'  ,@newname varchar(255) = '<new_name>';UPDATE   msdb.dbo.sysjobsteps

SET   command = REPLACE(command, @oldname, @newname)

WHERE   COMMAND LIKE '%'+@oldname+'%';
```
