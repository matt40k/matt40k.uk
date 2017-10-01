---
title: SQL Auditing sucks
author: matt40k
type: post
date: 2016-07-23T00:25:55+00:00
url: /2016/07/sql-auditing-sucks/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSDT

---
Back in SQL Server 2008 Microsoft introduced auditing, specifically the Database Audit Specification. It&#8217;s pretty good &#8211; despite the title I do actually think its nice feature, it pretty much works and doesn&#8217;t have much of a performance impact, my problem is not much love has gone into it since it was released in SQL2008. It claims to meet various regulations such as the EU data Protection Directive, HIPAA, PCI DSS and to be fair, I&#8217;m sure it does. Assuming to implement it correctly.

For example, I have it enabled on ACS.DimPersonSensitive &#8211; as you can guess, it holds sensitive information about a individual. If I want to break it, all I need to do is use parameters, ie
  
`declare @per_id int = 123456<br />
select * from [ACS].[DimPersonSensitive] where per_id = @per_id`

Now if I look at the logs, I literary see @per_id, so I have no idea what id that was pass. There is no column in the audit logs that tell me what that parameter was.

The other issue I was hit with today was SSDT, it really doesn&#8217;t support it. Here is the error I got today

<a href="//matt40k.uk/img/2016/07/error-audit-ssdt.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-799" src="//matt40k.uk/img/2016/07/error-audit-ssdt.png" alt="error-audit-ssdt" width="930" height="23" srcset="//matt40k.uk/img/2016/07/error-audit-ssdt.png 930w, //matt40k.uk/img/2016/07/error-audit-ssdt-300x7.png 300w, //matt40k.uk/img/2016/07/error-audit-ssdt-768x19.png 768w" sizes="(max-width: 930px) 100vw, 930px" /></a>

It&#8217;s basically blocking me from changing the table because it has auditing enabled on it. No nice way around it. It&#8217;s another Pre-Deployment script. This isn&#8217;t terrible. The terrible bit is it doesn&#8217;t reapply the auditing once you&#8217;ve removed it and updated the table, despite the auditing being defined in SSDT project.
