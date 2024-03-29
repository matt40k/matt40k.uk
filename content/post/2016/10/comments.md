---
title: Comments
author: matt40k
type: post
date: 2016-10-16T21:48:13+00:00
url: /2016/10/comments/
categories:
  - Business Intelligence
  - Microsoft
  - Power BI
  - PowerShell
  - SQL Server
  - SSDT
tags:
  - C Sharp
  - Comments
  - M
  - PowerQuery
  - PowerShell
  - T-SQL

---
One of the annoying things about working with multiple languages is they each have their differences &#8211; obviously, otherwise there would only be 1 language! Although there is good reason to have these differences they still have elements that are a pain. One of the most annoying things, other then &#8220;do you require a semicolon at the end of the statement?&#8221; is comments. Comments aren&#8217;t executed or complied but they help developers read code. Remember, the code is a interpretive language, its designed to be gateway between the machines and humans, if you write something complex your more then likely need to be include more comments explain what it does or look at refactoring so other developers can continue your work.

The few options are:

**Double dash (&#8211;)**

> &#8212; Single line quote

**Single Hash (#)**

> \# Single line quote

**Double forward-slash (//)**

> // string domain = &#8220;matt40k.uk&#8221;;

All of these are single line quotes, as in each line needs the require comment and the comment continues till the end of the line \ carriage break.

You also got:

**Forward-slash and asterisk (/*)** 

> /* Multi-Line
  
> quote */

Forward-slash and asterisk marks (**/***) the start of the comment, the comment continues until the asterisk marks and Backward-slash (***/**). The code must close any open&nbsp;Forward-slash and asterisk marks (**/***) comments in order to compile.

With&nbsp;Forward-slash and asterisk, you can comment in-line, for example

> Select \* from /\* Change the code to the right */ sys.tables

This is valid T-SQL that will return the all the columns for meta data about tables on the selected database

You can also use this across multiple lines, for example

> select
> 
> TableSchema = schema\_name(schema\_id)
> 
> ,TableName = name
> 
> /*
  
> You could also add
> 
> other tables
> 
> &nbsp;
> 
> */
  
> from
> 
> sys.tables

&nbsp;

**Power Query Formula (M) Language**

Double dash (&#8211;) **No**
  
Single hash (#) **Yes**
  
Double forward-slash (//)&nbsp;**No**
  
Forward-slash and asterisk (/*) **Yes**

**Transact-SQL (TSQL)**

Double dash (&#8211;) **Yes**
  
Single hash (#) **No**
  
Double forward-slash (//)&nbsp;**No**
  
Forward-slash and asterisk (/*) **Yes**

**C sharp (C#)**

Double dash (&#8211;) **No**
  
Single hash (#) **No**
  
Double forward-slash (//)&nbsp;**Yes**
  
Forward-slash and asterisk (/*) **Yes**

&nbsp;

Fun fact, my most commonly used comment?

**To-Do**
