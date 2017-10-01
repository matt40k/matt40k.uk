---
title: Automatic build and deployment process for Microsoft BI
author: matt40k
type: post
date: 2016-02-01T22:30:30+00:00
url: /2016/02/automatic-build-and-deployment-process-for-microsoft-bi/
categories:
  - Blog
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSAS
  - SSDT
  - SSIS
  - SSRS

---
I&#8217;ve previously [blogged about how I was going to detail how I build and deploy my Microsoft BI projects][1] and to be honest, I&#8217;ve been putting it off. The main reason is my work has been looking at <a href="https://www.visualstudio.com/products/visual-studio-team-services-vs" target="_blank" rel="nofollow">Visual Studio Team Services</a>, formally <a href="https://www.visualstudio.com/products/visual-studio-team-services-vs" target="_blank" rel="nofollow">Visual Studio Online</a> and I was looking at using the Build functionality that is included. This should make the whole setup process a lot easier for anyone else trying to replicate my setup. Unfortunately this doesn&#8217;t look like its going to happen this quarter.

## How I got here

So when I started in BI we where using Microsoft SQL Server 2008.

SSIS packages used XML configuration files and deployment files were created, manually copied to the SQL Server, then you logged onto the server &#8211; via RDP, ran the SSIS deployment file &#8211; which basically created a copy of the files and changed the variables in the XML configuration file.

Database changes was done by a giant SQL script &#8211; it started out as a simple script out the database objects, but future changes happened by simply updating the SQL script, manually.

Deployments were a pain. Every deployment had to be (re)deployed to DEV, then to UAT before finally getting to PROD. They took time and because they took time you tried to avoid them. Which meant every deployment was bigger. If you **had** to do something you would try and do it easiest way, ie manually change the raw SSIS package. This of course leads to drift.

When I started my job, one of the first tasks was to bring UAT up-to-date (after setting up auditing). After a quick look at the database schema I could tell the database objects were out-of-date, database compare tools were absolute life saver. Unsurprisingly, they (who shall remain nameless) didn&#8217;t commit the code to version control either. The only copy of the code was PROD, DEV had a even more updated version, however it was left in a unfinished state.

Right, enough with the horror stories of how I started my journey in BI.

## Fresh start

When we started to talk about upgrade from SQL Server 2008 to SQL Server 2014 I thought about some of the things I wanted.

I wanted a single tool to design the whole end-to-end product. From the database, to the ETL packages to the data model all the way to the end user reports. Guess what? Its Visual Studio.

Previously I had been to <a href="http://sqlea.org.uk/2014/06/20/usergroup-meetups-8-31st-july-and-9-28th-august-announced/" target="_blank" rel="nofollow">my local SQL Pass User Group</a> where <a href="http://workingwithdevs.com/" target="_blank" rel="nofollow">Alex Yates</a> and explain the whole continuous integration and deployment methodology, but aimed at the DBA. To put it simply, it forces you to use version control, which I **love**. The continuous integration basically means build on a dedicated machine &#8211; this gets around the whole &#8220;well it works me for me&#8221; arguments, if you forgot to commit a file and the build fails, its clearly your fault. If it builds OK on the clean build server, but doesn&#8217;t build on your colleagues, you know they have a problem, not you. The deployment is pretty straight forward, you don&#8217;t really need it when you have a single component, but when you have something like BI, where you have multiple components that have dependencies on one another, like the SQL database objects, the SSIS packages and the SSAS packages, you need to create an &#8220;installer&#8221;. I also wanted to a &#8220;standard&#8221; deployment method, if the automated process failed, I want to be able to run it manually.

## The solution

For the continuous integration element, the build process, I&#8217;ve used <a href="https://www.jetbrains.com/teamcity/" target="_blank" rel="nofollow">TeamCity</a> from the very excellent <a href="https://www.jetbrains.com/" target="_blank" rel="nofollow">JetBrains</a>. <a href="https://www.jetbrains.com/teamcity/" target="_blank" rel="nofollow">TeamCity</a> is a very mature stable product, my one &#8220;grip&#8221; is that based on Tomcat, luckily <a href="https://www.jetbrains.com/" target="_blank" rel="nofollow">JetBrains</a> have bundled it very well so its not really a problem. The main reasons for using it are, its a stable product (on Windows OS), its a got excellent support (ie you can find help on the internet) and it has a free tier &#8211; Professional Server license gives you 20 build configurations.

For the continuous deployment element, I&#8217;ve used <a href="https://octopusdeploy.com/" target="_blank" rel="nofollow">OctopusDeploy</a>.

 [1]: /2016/01/automated-sql-server-bi-deployments-with-octopusdeploy/
