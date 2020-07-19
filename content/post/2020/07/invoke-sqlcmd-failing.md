---
title: Invoke-SqlCmd Failing
author: matt40k
type: post
date: 2020-07-16T22:11:42+00:00
url: /2020/07/invoke-sqlcmd-failing/
type: post
description: 'Invoke-SqlCmd Failing - can only be called from within the same thread'
draft: false
categories:
  - Blog
tags:
  - Azure
  - PowerShell
  - SQL
  - Runbook

---

A really annoying problem I hit recently with a some Azure Runbooks was the following message occuring:

>> Invoke-Sqlcmd : The WriteObject and WriteError methods cannot be called from outside the overrides of the BeginProcessing, ProcessRecord, and EndProcessing methods, and they can only be called from within the same thread. 
>> Validate that the cmdlet makes these calls correctly, or contact Microsoft Customer Support Services.

After doing some digging, I found out that Invoke-SqlCmd isn't thread safe, so other runbooks running on that Azure Automation account, could interfere with each other. Which would explain the above thread error.

Luckily <a href="https://social.technet.microsoft.com/wiki/contents/articles/40091.automating-sql-operations-with-service-management-automation-sma-and-invoke-sqlcmd-challenges-and-solutions.aspx" target="_blank" rel="nofollow">MVP Stoyan Chalakov had already blogged about a solution - here</a>.

Unfortunately, this didn't work. 

>> Unable to find type [Microsoft.SqlServer.Management.PowerShell.OutputType].

Damn.

I tried updating the SqlServer PowerShell module, no joy. Re-reading article again to see if I missed something and spotted the only question on the script.

<a href="https://gallery.technet.microsoft.com/Invoke-Sqlcmd-optimized-d6b4a0a3/view/Discussions#content" target="_blank" rel="nofollow">https://gallery.technet.microsoft.com/Invoke-Sqlcmd-optimized-d6b4a0a3/view/Discussions#content</a>

Damn. No answer to the nearly 3 year old question.

At this point I thought, <a href="https://dbatools.io">dbatools</a>. A quick look at the docs, bingo. <a href="https://docs.dbatools.io/#Invoke-DbaQuery">Invoke-DbaQuery</a>.

Few mins later I had dbatools installed in the Azure Automation account and it was just then a quick change

Replacing:

- Invoke-SqlCmd - with Invoke-DbaQuery
- Username / Password - with SqlCredential
- (and the troublesome) OutputAs - with As
- ServerInstance - with SqlInstance

(I also added -ReadOnly - its just a select statement that exports to CSV after all)

