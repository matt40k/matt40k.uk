---
title: Documentation
author: matt
type: post
date: 2015-08-30T21:30:14+00:00
url: /2015/08/documentation/
categories:
  - Blog
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSAS
  - SSDT
  - SSIS

---
One of the problems we have is documentation and how to keep it up-to-date. We tend to deliver a new batch of reports as part of a CR (Change Request) then make changes as part of BAU (Business as usual) unless its a particularly complex or time consuming change. The problem is often BAU changes happen rapidly often within a short time frame and time isn&#8217;t always allocated to updating documentation.

Over time a small, simple change and evolve into a major change and the documentation can significantly drift out-of-sync. Documentation is an important part of the communication between developer, analysis and the end-user, without it misunderstanding and confusing can occur and errors and mistakes happen.

Whilst investigating how other are documentation work I rediscovered the much unloved extended property MS\_Description. As you might have guess, using the description field to enter, yes, you guessed it, a description of the tables, views, stored procedure and other SQL objects. Speaking of naming &#8211; it&#8217;s also important to name things correctly. A table named dbo.Table1 helps no-one. I tend to name any temporary tables MS\_TMP &#8211; this then quickly identities me as the owner and the fact it can most likely be destroyed. Any dimensions are prefix with Dim and facts are, yes, you&#8217;ve guessed it again &#8211; Fact.

I have a TSQL script that pulls this data into a table on the staging database as part of a SSIS package, this is configured a SQL Job, however it is only execute post-deployment &#8211; we use <a href="https://www.jetbrains.com/teamcity/" target="_blank" rel="nofollow">TeamCity</a> to build the project and then <a href="http://octopusdeploy.com/" target="_blank" rel="nofollow">OctopusDeploy</a> for deploying to the various environments.

As we move towards using Analysis Services, I needed a way to document the cubes, luckily <a href="http://www.purplefrogsystems.com/about-us.html" target="_blank" rel="nofollow" class="broken_link">Alex Whittles</a> from <a href="http://www.purplefrogsystems.com/" target="_blank" rel="nofollow">Purple Frog</a> has already come up with a solution using the Dynamic Management Views (DMVs) and blogged about it &#8211; <a href="http://www.purplefrogsystems.com/blog/2010/09/olap-cube-documentation-in-ssrs-part-1/" target="_blank" rel="nofollow">http://www.purplefrogsystems.com/blog/2010/09/olap-cube-documentation-in-ssrs-part-1/</a>.

I have however modified it, I&#8217;ve followed the standard ETL process, so I&#8217;ve extracted the data from the DMVs into a staging data, like SQL objects, this is only executed post-deployment by a SQL job that is executed by <a href="http://octopusdeploy.com/" target="_blank" rel="nofollow">OctopusDeploy</a> task. I didn&#8217;t like the idea of dynamically querying the data every time and as we use continue integration\deployment I don&#8217;t need to worry about the data being out of data.

All I have left to really look at is documenting SSIS. Speaking of SSIS, I found <a href="http://sqlblog.com/blogs/jamie_thomson/archive/2012/01/29/suggested-best-practises-and-naming-conventions.aspx" target="_blank" rel="nofollow">Jamie Thomson post on naming conventions</a> very useful.
