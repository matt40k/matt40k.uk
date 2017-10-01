---
title: MDSCHEMA_CUBES DMV not returning all cubes
author: matt40k
type: post
date: 2016-06-07T20:01:13+00:00
url: /2016/06/mdschema_cubes-dmv-not-returning-all-cubes/
categories:
  - Blog
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSIS
  - SSRS

---
I had previously created a SSIS package with a simple Process Full on the SSAS MD database, however, as the project has progressed this hasn&#8217;t been ideal. Its basically all or nothing. In order reduce the damage a failure can cause I&#8217;ve setup a Process Full for each dimension and cube so each is processed independently of each other. I&#8217;ve used the data from the Analysis Services Dynamic Management Views, or DMV for short, which I&#8217;ve <a href="//matt40k.uk/2015/08/documentation/" target="_blank" rel="nofollow">used for the documentation</a> to feed the foreach loop.

However there is a major problem with the DMVs. They only list processed cubes (and their dimensions). So how do you get a list of unprocessed cubes (and their dimensions)?

Answer? Using the Analysis Management Objects (AMO). This will return the same list as SQL Server Management Studio (SSMS), rather then just the processed, like the DMV or Excel lists. I&#8217;m currently trying out a few ideas to find the best solution &#8211; so as a script component (source) or a stored procedure. As the saying goes, it&#8217;s production ready, but its not <a href="https://github.com/matt40k" target="_blank" rel="nofollow">GitHub ready</a> &#8211; not yet anyway.

Thanks again to Chris Webb for pointing me in the right direction

<blockquote class="twitter-tweet" data-width="550">
  <p lang="en" dir="ltr">
    <a href="https://twitter.com/matt40k" target="_blank" rel="nofollow">@matt40k</a> SSMS might well be using AMO or something similar from the admin interface
  </p>
  
  <p>
    &mdash; Christopher Webb (@Technitrain) <a href="https://twitter.com/Technitrain/status/732886507019767808" target="_blank" rel="nofollow">May 18, 2016</a>
  </p>
</blockquote>



&nbsp;
