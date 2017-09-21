---
title: Showing SIMS Bulk Import some love
author: matt
type: post
date: 2016-02-14T23:32:41+00:00
url: /2016/02/showing-sims-bulk-import-some-love/
categories:
  - Blog
  - PowerShell
  - Projects
  - SIMS Bulk Import

---
<blockquote class="twitter-tweet" data-width="550">
  <p lang="en" dir="ltr">
    Missus decided to dye her hair, so spent the time moving from <a href="https://twitter.com/teamcity" target="_blank" rel="nofollow">@teamcity</a> on <a href="https://twitter.com/Azure" target="_blank" rel="nofollow">@Azure</a> vm to <a href="https://twitter.com/appveyor" target="_blank" rel="nofollow">@appveyor</a> for <a href="https://twitter.com/simsbulkimport" target="_blank" rel="nofollow">@simsbulkimport</a>
  </p>
  
  <p>
    &mdash; Matt Smith (@matt40k) <a href="https://twitter.com/matt40k/status/698912438150938628" target="_blank" rel="nofollow">February 14, 2016</a>
  </p>
</blockquote>



So today I managed to move <a href="https://simsbulkimport.uk" target="_blank" rel="nofollow">SIMS Bulk Import</a> over to <a href="http://www.appveyor.com/" target="_blank" rel="nofollow">Appveyor</a>. So what does this mean? Well it means I don&#8217;t have to worry about going over my Azure credit limit each month for starters! <a href="http://www.appveyor.com/" target="_blank" rel="nofollow">Appveyor</a> has excellent support for <a href="https://GitHub.com" target="_blank" rel="nofollow">GitHub</a>, so each commit is automatically build, tested, and (when I enable it) a new release created.

The next release will include

  * Pupil username creation &#8211; you can blame\thank <a href="https://twitter.com/gbaman1" target="_blank" rel="nofollow">Andrew Mulholland</a> for this, I saw his project PiNet and thought <a href="http://pinet.org.uk/articles/manage-users/csv-import.html" target="_blank" rel="nofollow">we can make this better</a>.
  * PowerShell module &#8211; you can blame\thank <a href="https://twitter.com/ryanyates1990" target="_blank" rel="nofollow">Ryan Yates</a> for making me want to do this one
  * Log submission &#8211; I&#8217;ve finally started pull this together, I&#8217;ve desensitised the log file by basically creating two. One for log submissions and other for local debugging. The main issue is testing, both the web service and the application.
