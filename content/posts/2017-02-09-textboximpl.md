---
title: TextBoxImpl
author: matt40k
type: post
date: 2017-02-09T22:09:12+00:00
url: /2017/02/textboximpl/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSRS

---
Another error I hit

> Warning               1
> 
> [rsRuntimeErrorInExpression]
> 
> The Value expression for the textrun ‘Textbox28.Paragraphs[0].TextRuns[0]’
> 
> contains an error: Overload resolution failed because no Public &#8216;/&#8217; can be called with these arguments:
> 
> &#8216;Public Shared Operator /(d1 As Decimal, d2 As Decimal) As Decimal&#8217;:
> 
> Argument matching parameter &#8216;d2&#8217; cannot convert from &#8216;TextBoxImpl&#8217; to &#8216;Decimal&#8217;.
> 
> C:\Projects\Reports\1. Report.rdl

Thankfully Google found Qiuyun <a href="https://social.msdn.microsoft.com/Forums/sqlserver/en-US/023f042d-67fc-4dde-a13c-03c59192d123/ssrs-expressions?forum=sqlreportingservices" target="_blank" rel="nofollow">answer</a>. I was missing the **.Value** at the end.

So (wrong)

> =ReportItems!Textbox1

Fixed (working)

> =ReportItems!Textbox1**.Value**
