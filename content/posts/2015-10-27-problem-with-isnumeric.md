---
title: Problem with ISNUMERIC
author: matt40k
type: post
date: 2015-10-27T21:29:07+00:00
url: /2015/10/problem-with-isnumeric/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
tags:
  - T-SQL

---
Todays problem was brought to you by a highly customizable system with poor user validation and a user who doesn&#8217;t know the difference between data and formatting. First the system. The supplier has created a highly user customizable system, they can for example create a web form with zero coding &#8211; 100% user config. The problem is, technically, it creates a mess. So your nice new form with a number of questions stores all its answers in a single table with the data going into a nvarchar(max) column &#8211; which is fine for free-text columns, but not so good for integer fields. This is especially a problem when you have a form that has drop-down options (luckily stored in a different table more efficiently) which generates an amount which the end user can overtype in order to moderate it up or down, which has zero validation.

The data is &#8220;stored&#8221; as numeric in the database so, for example, 1200.34, but is formatted as currency &#8211; so £1,200.34. The problem occurs when the user overtypes the amount, when they do, they overtype it, say as, 1201.34, but they don&#8217;t enter 1201.34. They enter £1201.34. Now this is a problem as when I load the data into the Data Mart, I store the data as a numeric(18,2), which means I need to cast it. This will of course fail if the user has overtyped it as it isn&#8217;t a numeric &#8211; which has historically happened. The way I resolved it was to strip out the £ sign using a replace then to add a ISNUMERIC statement as a fail safe.

However despite my failsafe it failed today &#8211; the problem was with ISNUMERIC &#8211; if you read the man, it says <a href="https://msdn.microsoft.com/en-us/library/ms186272.aspx" target="_blank" rel="nofollow">&#8220;ISNUMERIC returns 1 for some characters that are not numbers, such as plus (+), minus (-), and valid currency symbols such as the dollar sign ($)&#8221;</a>. What it doesn&#8217;t tell you is it also covers commas &#8211; so:
  
`select cast(replace('£1,220', '£', '') as int)`
  
will fail with
  
`Conversion failed when converting the varchar value '1,220' to data type int.`
  
this is despite ISNUMERIC returning 1 (ie valid)
  
`select ISNUMERIC('1,220')`

The fix is to replace (well remove) commas as well as the pound sign (£). Going forward, in SQL2012 Microsoft has introduced <a href="https://msdn.microsoft.com/en-us/library/hh974669.aspx" target="_blank" rel="nofollow">Try_Cast</a> which might be another option.
