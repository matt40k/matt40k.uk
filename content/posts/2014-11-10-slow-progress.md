---
title: Slow progress
author: matt
type: post
date: 2014-11-10T22:34:33+00:00
url: /2014/11/slow-progress/
categories:
  - dbSend
  - MIS systems
  - Projects
  - S3Unlock
  - SIMS .net
  - SIMS Bulk Import
  - Spelling
  - TidyBackups

---
I&#8217;m currently getting bogged down with other projects and unfortunately my final sprint of <a href="https://simsbulkimport.uk/" target="_blank" rel="nofollow">SIMS Bulk Import</a> has grind to a halt. On the plus side I managed to swash a few more bugs last month, get a code signing certificate. This will mean all future releases will be signed as coming from me which is great news, it adds a layer of confidence that the code you run is unaltered by a third party. I&#8217;ve also started reviewing my other projects, ensure that the code on the public repository is up-to-date, I&#8217;ve also switched over to Git and copied them all over to <a href="https://github.com/matt40k?tab=repositories" target="_blank" rel="nofollow">GitHub</a>. At bit more on that later.

Part of the updated process was to use a Continuous Integration server &#8211; specifically <a href="https://www.jetbrains.com/teamcity/" target="_blank" rel="nofollow">TeamCity</a>. Simply put, these allowed the builds to occur on a dedicated box which made the whole process quicker and easier &#8211; it also added confidence as it ensured that everything required was commit in the repository. The only downside to this is the cost &#8211; although renting a VPS from OVH is cheap, it still isn&#8217;t cost effective due to the limited amount of time I actually use it, I&#8217;m therefore looking at moving it to Azure as you only pay for provisioned resources and your can de-provision servers and only pay for the storage. Alas this means more messing about setting up servers.
