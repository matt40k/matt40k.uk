---
title: Automated SQL Server BI deployments with OctopusDeploy
author: matt40k
type: post
date: 2016-01-15T21:50:50+00:00
url: /2016/01/automated-sql-server-bi-deployments-with-octopusdeploy/
categories:
  - Blog
  - Business Intelligence
  - Microsoft
  - PowerShell
  - SQL Server
  - SSAS
  - SSDT
  - SSIS
  - SSRS

---
Today, my <a href="https://github.com/OctopusDeploy/Library/pull/278" target="_blank" rel="nofollow">pull request </a>for the <a href="https://gist.github.com/matt40k/ed6231dfee98261bf6bc" target="_blank" rel="nofollow">SSAS deployment script </a>was merged into the <a href="http://octopusdeploy.com" target="_blank" rel="nofollow">Octopus Deploy</a> <a href="https://library.octopusdeploy.com/#!/step-template/actiontemplate-deploy-ssas-from-package" target="_blank" rel="nofollow">Community Library</a>.

So what is <a href="http://octopusdeploy.com" target="_blank" rel="nofollow"><u><span style="color: #0066cc;">Octopus Deploy</span></u></a> and why should I care?

> Octopus is a friendly deployment automation tool for .NET developers.

But don&#8217;t be fooled. <a href="http://octopusdeploy.com" target="_blank" rel="nofollow"><u><span style="color: #0066cc;">Octopus Deploy</span></u></a> isn&#8217;t just limited to .NET developers deploying hip new cloud based applications, it can do much, much more. I currently use <a href="http://octopusdeploy.com" target="_blank" rel="nofollow">Octopus</a> to deploy Jasper reports to our 6 HR environments, I also use it to deploy our HR interfaces which are a series of SSIS packages and SQL objects which uses Microsoft SQL Server 2008. I use <a href="https://dbup.github.io/" target="_blank" rel="nofollow">DbUp</a>, a open source library, for database deployment and a custom C# application for SSIS package deployment. Today, we surpassed 1,000 report deployments to production, we&#8217;ve also deploy over 270 SSIS package changes in about a year.

So when it came to upgrading our BI platform from SQL 2008 to SQL 2014, one of the key things I want was deployment automation. The SQL 2008 platform required manual deployments which often lead to mistakes and ended up writing the entire day off, per deployment. Unfortunately, my current process was pretty basic. Database deployments are idempotent, it drop any objects and recreated them, every time. This is fine for interfaces where tables only hold in transit data, but for BI, the idea of dropping a staging table with 140 million rows that takes over 4 hours to load doesn&#8217;t make me want to do any deployments. Luckily, the problem is already solved. SSDT. And there is already a <a href="https://library.octopusdeploy.com/#!/step-template/actiontemplate-sql-deploy-dacpac" target="_blank" rel="nofollow">PowerShell step template </a>on the <a href="http://octopusdeploy.com" target="_blank" rel="nofollow"><u><span style="color: #0066cc;">Octopus Deploy</span></u></a> <a href="https://library.octopusdeploy.com/#!/step-template/actiontemplate-deploy-ssas-from-package" target="_blank" rel="nofollow"><u><span style="color: #0066cc;">Community Library</span></u></a>.

Also moving to SQL 2014 allowed me to use the new ISPAC, again, there is already a <a href="https://library.octopusdeploy.com/#!/step-template/actiontemplate-deploy-ispac-ssis-project-from-a-package" target="_blank" rel="nofollow">PowerShell step template </a>on the <a href="http://octopusdeploy.com" target="_blank" rel="nofollow"><u><span style="color: #0066cc;">Octopus Deploy</span></u></a> <a href="https://library.octopusdeploy.com/#!/step-template/actiontemplate-deploy-ssas-from-package" target="_blank" rel="nofollow"><u><span style="color: #0066cc;">Community Library</span></u></a>. There is even a <a href="https://library.octopusdeploy.com/#!/step-template/actiontemplate-deploy-ssrs-reports-from-a-package" target="_blank" rel="nofollow">PowerShell step template for SSRS</a>.

The only thing missing was SSAS. After watching <a href="http://blog.crossjoin.co.uk/" target="_blank" rel="nofollow">Chris Webb&#8217;s </a>video tutorial &#8211; <a href="https://projectbotticelli.com/knowledge/ssas-cube-deployment-processing-and-admin-video-tutorial" target="_blank" rel="nofollow">Cube Deployment, Processing and Admin</a> on <a href="https://projectbotticelli.com/knowledge/ssas-cube-deployment-processing-and-admin-video-tutorial" target="_blank" rel="nofollow">Project Botticelli</a>, I decided it had to use <a href="https://msdn.microsoft.com/en-us/library/ms162758.aspx" target="_blank" rel="nofollow">Microsoft.AnalysisServices.Deployment.exe</a>. After a bit of scripting and testing, I managed to write a PowerShell that updates the xml config files for the deployment &#8211; it sets the **ProcessingOption** to **&#8216;**<span class="pl-s"><strong>DoNotProcess&#8217;.</strong> It updates the <strong>Data source</strong> &#8211; where the cube will refresh the data from. The script isn&#8217;t perfect. For starters, what if you have more then one data source? Also what if your not using SQL Server 2014? Still the great thing about open source is that other can update it. Anyone can improve it, its not reliant on me having free time. So hopefully by the time we move to SQL 2016 someone will have already updated it to work with SQL 2016.</span>

In a future post I&#8217;m going to blog about <a href="http://octopusdeploy.com" target="_blank" rel="nofollow"><u><span style="color: #0066cc;">Octopus Deploy</span></u></a> in a bit more detail and how I&#8217;ve setup my SQL Server BI deployment process (in a lot of detail). I&#8217;m hoping to try using <a href="https://www.visualstudio.com/en-us/products/visual-studio-team-services-vs.aspx" target="_blank" rel="nofollow">Microsoft Visual Studio Team Services </a>to build the Octopus packages. Currently I use a on-prem <a href="https://www.jetbrains.com/teamcity/" target="_blank" rel="nofollow">TeamCity</a>, which is excellent, its just&#8230; I don&#8217;t like managing extra servers when I can use SaaS. I like development over administration.

I&#8217;ll leave you will a screenshot of my deployment screen in <a href="http://octopusdeploy.com" target="_blank" rel="nofollow"><u><span style="color: #0066cc;">Octopus Deploy</span></u></a>, and yes, that&#8217;s **one** button press to get my changes into UAT

<a href="//matt40k.uk/img/2016/01/octopusbi.png" rel="attachment wp-att-548" target="_blank" rel="nofollow"><img class="alignnone wp-image-548 size-full" src="//matt40k.uk/img/2016/01/octopusbi.png" alt="octopusbi" width="1600" height="860" srcset="//matt40k.uk/img/2016/01/octopusbi.png 1600w, //matt40k.uk/img/2016/01/octopusbi-300x161.png 300w, //matt40k.uk/img/2016/01/octopusbi-768x413.png 768w, //matt40k.uk/img/2016/01/octopusbi-1024x550.png 1024w, //matt40k.uk/img/2016/01/octopusbi-648x348.png 648w, //matt40k.uk/img/2016/01/octopusbi-357x192.png 357w" sizes="(max-width: 1600px) 100vw, 1600px" /></a>
