---
title: Swollen SSISDB caused by Continuous Deployment
author: matt40k
type: post
date: 2017-01-10T20:00:15+00:00
url: /2017/01/swollen-ssisdb-caused-by-continuous-deployment/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSDT
  - SSIS

---
I recently had incident logged where the drive that hosted SSISDB database filled up on the UAT environment. We had SSISDB set to only keep 2 copies of the projects, however the additional copies are only removed when the SQL job is run &#8211; **SSIS Server Maintenance job**.

The SQL job is scheduled to run at 00:00 (midnight) every day, which is the default, which runs two steps

**SSIS Server Operation Records Maintenance**
  
TSQL Script: EXEC [internal].[cleanup\_server\_retention_window]

**SSIS Server Max Version Per Project Maintenance**
  
TSQL Script: EXEC [internal].[cleanup\_server\_project_version]

The problem is we do Continuous Deployment (CD), we use <a href="https://octopus.com/" target="_blank" rel="nofollow">Octopus Deploy</a> to automate our deployment process &#8211; it&#8217;s so effective we often do multiple releases a day. This in turned caused the log file to swell when a large number of old projects are removed, which results in the drive filling &#8211; despite the recovery model being set to simple.

The solution was simple, add an additional log file, located on another drive (I used the backup drive as it has tons of free space), run the job, truncate the log files, then remove the extra log file. Then it was just a question of running the two cleanup stored procedures post deployment.
