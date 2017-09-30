---
title: Should I purchase Full SQL or is Express enough?
author: matt
type: post
date: 2014-05-20T18:15:35+00:00
url: /2014/05/should-i-purchase-full-sql-or-is-express-enough/
categories:
  - MIS systems
  - SIMS .net
tags:
  - Advise

---
One of the common questions I used to get asked whilst supporting <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> was, do I need Full SQL. <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> uses <a href="http://www.microsoft.com/en-gb/server-cloud/products/sql-server/default.aspx" target="_blank" rel="nofollow">Microsoft SQL Server</a> as it&#8217;s relational database management system (RDBMS) so it&#8217;s important to ensure the engine is correctly sized for job at hand. <a href="http://www.microsoft.com/en-gb/server-cloud/products/sql-server/default.aspx" target="_blank" rel="nofollow">Microsoft SQL Server</a> has come in a number of editions over the years, I won&#8217;t detail all the various editions but the two editions schools should be concerned with is Express and Standard. Express is the free edition that <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita </a>bundles as part of their installation media and Standard edition requires purchasing additional <a href="http://www.microsoft.com/" target="_blank" rel="nofollow">Microsoft</a> licenses.

Standard edition can either be licensed by the number of processor (cores) or by users. I personally tend to go for processor licenses so I don&#8217;t need to worry about buying new licenses when adding new users later on down the road. It does however come down to pricing &#8211; I tend to find processor licenses break even around the 30 user mark (based on Academic licensing anyway).

So why should you shell out of Standard edition? Now to be fair to <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> a number of features that Standard has over Express, like SSIS and the SQL Agent <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> has created tools to workaround the limitations, they&#8217;ve created a data transfer tool to extract the data from the <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> database into the <a href="http://www.capita-sims.co.uk/our-products/sims-discover-primary-schools-and-academies" target="_blank" rel="nofollow" class="broken_link">SIMS Discover</a> database for example, they&#8217;ve created routines within <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a> to create Windows Scheduled  Tasks for SQL jobs like B2B. With that said, the one thing <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> can&#8217;t get around is the hard resource limits <a href="http://www.microsoft.com/en-gb/" target="_blank" rel="nofollow">Microsoft</a> has set. Express is limited to 1GB RAM and 1 CPU (max of 4 cores).

When deciding what edition of SQL to use, I normally follow the following diagram

<img class="aligncenter wp-image-16 size-full" src="//matt40k.uk/img/2014/05/SQL_Edition_Decision_Tree.png" alt="Which SQL Edition is right for me?" width="415" height="543" />

I simply believe a Primary school doesn&#8217;t need SQL Standard edition. Secondary schools who use <a href="http://www.capita-sims.co.uk/our-products/sims-lesson-monitor-secondary-schools-and-academies" target="_blank" rel="nofollow">Lesson Monitor</a>, a <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">Capita</a> bolt-on module that is used for recording attendance for individual lessons rather then just AMPM, will be using the system pretty much all day rather then just morning and afternoons, so your concurrent users will be alot higher and therefore require more then 1GB RAM. It&#8217;s rare that a Secondary school will not be recording individual lessons, however other bolt-ons exist from third parties that will allow the same thing but not have the same impact on the server, so you may be able to get away with Express by using a web based bolt-on.
