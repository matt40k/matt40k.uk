---
title: TeamCity AssemblyInfo Patcher not working
author: matt40k
type: post
date: 2014-09-20T01:16:33+00:00
url: /2014/09/teamcity-assemblyinfo-patcher-not-working/
categories:
  - Projects
  - SIMS Bulk Import

---
Tonight I was trying to get <a href="http://www.jetbrains.com/teamcity/" target="_blank" rel="nofollow">TeamCity</a> to auto-update the version number for my <a href="http://simsbulkimport.uk/" target="_blank" rel="nofollow">SIMS Bulk Import</a> application, however the simple <a href="http://confluence.jetbrains.com/display/TCD65/AssemblyInfo+Patcher" target="_blank" rel="nofollow">AssemblyInfo Patcher</a> just failed to work. No errors. Nothing.

Then I read the manual, again&#8230;

> Note that this feature will work only for &#8220;standard&#8221; projects, i.e. created by means of the Visual Studio wizard, so that all the AssemblyInfo files and content have a standard location.

So I created a new package which placed the AssemblyInfo.cs into the Properties folder, mine was in the main directory, moved it into the subfolder and bang, it works. Awesome.

&nbsp;
