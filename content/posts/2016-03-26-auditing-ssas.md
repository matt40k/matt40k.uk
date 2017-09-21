---
title: Auditing – SSAS
author: matt
type: post
date: 2016-03-26T23:30:16+00:00
url: /2016/03/auditing-ssas/
categories:
  - Blog
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSAS
  - SSDT
tags:
  - T-SQL

---
There are various types of Auditing in the Microsoft BI stack. There is auditing in SSRS, SharePoint, SSAS and not forgetting SQL has its own auditing.

Today I am looking at the SSAS auditing &#8211; you can find out more about it on <a href="https://technet.microsoft.com/en-us/library/cc917676.aspx" target="_blank" rel="nofollow">TechNet</a>.

<a href="https://gallery.technet.microsoft.com/scriptcenter/Basic-OlapQueryLog-Analysis-20ba455d" target="_blank" rel="nofollow">Olaf Helper</a> has published some TSQL code for querying the audit data -on the <a href="https://gallery.technet.microsoft.com/scriptcenter/Basic-OlapQueryLog-Analysis-20ba455d" target="_blank" rel="nofollow">Script Center</a>.

But first, we need a table to store the data, here is a TSQL script for creating the table:

<div class="gist-oembed" data-gist="matt40k/5e0ce19d66216a25be02.json">
</div>

&nbsp;
