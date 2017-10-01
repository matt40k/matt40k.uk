---
title: MSSQL server failed on Ubuntu on Windows 10
author: matt40k
type: post
date: 2017-03-05T11:40:58+00:00
url: /2017/03/mssql-server-failed-on-ubuntu-on-windows-10/
categories:
  - Business Intelligence
  - SQL Server
tags:
  - Linux
  - mssql
  - ubuntu

---
I&#8217;ve been getting errors with MSSQL server on Ubuntu on Windows 10. The error,

> Failed to connect to bus: No such file or directory
  
> dpkg: error processing package mssql-server (&#8211;remove):
  
> subprocess installed post-removal script returned error exit status 1
  
> Processing triggers for libc-bin (2.23-0ubuntu5) &#8230;
  
> E: Sub-process /usr/bin/dpkg returned an error code (1)

I managed to fix it in the end by

<div class="gist-oembed" data-gist="matt40k/a379d24a73974e2a8cd2921e29eeaa96.json">
</div>

Of course, you should try uninstalling correctly first, which is latter of the two

I&#8217;ve included remove Microsoft GPG key and un-register the Microsoft SQL Server Ubuntu repository. <a href="https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-ubuntu" target="_blank" rel="nofollow">For more read Microsoft doc</a>.
