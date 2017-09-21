---
title: SSRS 2016 by default
author: matt
type: post
date: 2017-01-10T22:14:13+00:00
url: /2017/01/ssrs-2016-by-default/
categories:
  - Business Intelligence
  - Microsoft
  - PowerShell
  - SQL Server
  - SSRS
tags:
  - CD
  - CI
  - Continuous Deployment
  - Continuous Integration
  - Octopus Deploy
  - PowerShell
  - TeamCity

---
For the past 4 months I&#8217;ve been using Visual Studio 2015 rather then Visual Studio 2013 and yesterday, I hit a bug with SSRS (shows how much I love SSRS).

The bug appeared when it came to deployment

<a href="//matt40k.uk/img/2017/01/SSRSdeploymentError.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-2388" src="//matt40k.uk/img/2017/01/SSRSdeploymentError.png" alt="" width="858" height="711" srcset="//matt40k.uk/img/2017/01/SSRSdeploymentError.png 858w, //matt40k.uk/img/2017/01/SSRSdeploymentError-300x249.png 300w, //matt40k.uk/img/2017/01/SSRSdeploymentError-768x636.png 768w" sizes="(max-width: 858px) 100vw, 858px" /></a>

The error was deploying SSRS report

> Exception calling &#8220;CreateCatalogItem&#8221; with &#8220;7&#8221; argument(s): &#8220;The definition of this report is not valid or supported
  
> by this version of Reporting Services. The report definition may have been created with a later version of Reporting
  
> Services, or contain content that is not well-formed or not valid based on Reporting Services schemas. Details: The
  
> report definition has an invalid target namespace
  
> &#8216;http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition&#8217; which cannot be upgraded.

The report that error deploying was the one I had just changed. Looking at the code diff in <a href="https://www.visualstudio.com/team-services/" target="_blank" rel="nofollow">Visual Studio Team Services</a> you can see its added in some new 2016 goodness. I checked and double-checked my settings. Visual Studio 2015 wants to give you a 2016 file. If you manually deploy from within Visual Studio it works. Checking out the bin\debug folder reveals that it&#8217;s using the 2016 version to build a legacy version, which makes sense as the 2016 is the old (2008R2) with extra goodness slapped in &#8211; like being able to define parameter location.

So, we now have to build our SSRS reports. To do so, I&#8217;ve just created a PowerShell script that builds it using devenv.exe with the parameters for a silent build. This worked great, only it took over 50mins to run. The main lag was every time it loaded the solution it builds\checks\something with the database projects. It takes an age. The fix was to create a dedicated Report solution file (Report.sln) &#8211; I did this with a PowerShell script that copying the main solution file, which included all the SSDT (database), Integration (SSIS) packages, analysis models as well as the SSRS reports, then just removing all projects but the SSRS projects. I did this via PowerShell just because I don&#8217;t like extra manual steps. It&#8217;s a pain, when you add a new SSRS project you&#8217;d have to add it to Report.sln, which you&#8217;d probably forget and waste spend time debugging a silly mistake.

Creating the Report.sln reduce the build time down to just over 2mins (from over 50mins!), so it was worth doing.
