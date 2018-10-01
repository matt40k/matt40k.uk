---
title: vardecimal support is enabled for the database but disabled for the project
date: '2018-10-01T21:06:12+01:00'
description: >-
  vardecimal support is enabled for the database but disabled for the project.
  See SQL Server Books Online for more information about how to turn off
  vardecimal support.
---
I had a bit of a weird one where one of the SSDT projects failed to deploy. The package would successfully deploy locally, but failed from the deployment server.

An extract from the log:

> vardecimal support is enabled for the database but disabled for the project. See SQL Server Books Online for more information about how to turn off vardecimal support.

![null](img/2018/09/error.png)

The short version of the story is the deployment server was trying to msdb.dacpac, which had been added to the package, to the user database. The fix was to get the deployment server to ignore msdb.dacpac and only deploy the user database. 
