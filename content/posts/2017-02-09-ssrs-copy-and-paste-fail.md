---
title: SSRS copy and paste fail
author: matt40k
type: post
date: 2017-02-09T21:58:49+00:00
url: /2017/02/ssrs-copy-and-paste-fail/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSRS

---
In case you haven&#8217;t heard, I&#8217;ve started a new job and one of my first tasks was to speed up a SSRS report. One of the first issues I stumbled across was this:

> An error occurred during local report processing.
> 
> The definition of the report &#8216;/1. Report&#8217; is invalid.
> 
> The Value expression for the textrun &#8216;Tx412.Paragraphs[0].TextRuns[0]&#8217; contains an error: [BC30456] &#8216;RdlObjectModel&#8217; is not a member of &#8216;ReportingServices&#8217;

Looking into it the issue it appears its expanded expressions when it got copied &#8211; it&#8217;s basically making the it fully qualified.

So

> Cint

becomes:

> Microsoft.ReportingServices.RdlObjectModel.ExpressionParser.VBFunctions.Cint

The fix was to just edit to code then do a find and replace, replacing the added reference with nothing. Simple.
