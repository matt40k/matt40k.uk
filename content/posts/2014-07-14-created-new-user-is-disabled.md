---
title: Created new user is disabled
author: matt
type: post
date: 2014-07-14T11:41:18+00:00
url: /2014/07/created-new-user-is-disabled/
categories:
  - SQL Server
  - SSDT
tags:
  - T-SQL

---
I&#8217;ve created a new SQL user along with a new role in our warehouse db project using Visual Studio 2012.

> CREATE LOGIN [newuser] WITHPASSWORD='{{ RANDOM PASSWORD }}&#8217;,DEFAULT_DATABASE=[Database]
  
> GO
> 
> CREATE USER [newuser] FORLOGIN [newuser] WITHDEFAULT_SCHEMA=[dbo]
> 
> GO
> 
> ALTER ROLE [newrole] ADD MEMBER [newuser]
> 
> GO

&nbsp;

Problem is, the user is disabled. When you do it manually via SQL Management Studio, it&#8217;s enabled and working. Manually enabling the account doesn&#8217;t allow it connect either. A quick Google revealed:

<a href="http://www.sqlhammer.com/blog/creating-logins-and-users-why-i-cant-connect/" target="_blank" rel="nofollow">http://www.sqlhammer.com/blog/creating-logins-and-users-why-i-cant-connect/</a>

Bingo. Appears I need to add the following to the end of the script:

>  GRANT CONNECT TO [newuser]
