---
title: DacPac vs SqlCmd variables
author: matt
type: post
date: 2016-02-02T23:58:33+00:00
url: /2016/02/dacpac-vs-sqlcmd-variables/
categories:
  - Blog
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSDT
tags:
  - xml

---
I recently discovered the ability to reference other database project (I know, I know), anyway, this cause my lovely automate build\deployment process to fail. Investigating the error led me to, yes, you guessed it a <a href="http://sqlblog.com/blogs/jamie_thomson/archive/2012/11/13/a-dacpac-limitation-deploy-dacpac-wizard-does-not-understand-sqlcmd-variables.aspx" target="_blank" rel="nofollow">Jamie Thomson&#8217;s blog</a> (from 2012).

Thankfully, I managed to figure out a clean solution, the <a href="https://library.octopusdeploy.com/#!/step-template/actiontemplate-sql-deploy-dacpac" target="_blank" rel="nofollow">DacPac solution on Octopus Deploy library </a>has an option to pass **Profile Name**, which is the publish profile XML file. He is the cut-down version I&#8217;ve used, just the missing variables

<div class="gist-oembed" data-gist="matt40k/1c1999ec349d00018037.json">
</div>
