---
title: Pretty time
author: matt
type: post
date: 2016-11-30T22:17:23+00:00
url: /2016/11/pretty-time/
algolia_searchable_posts_records_count:
  - "4"
algolia_posts_post_records_count:
  - "4"
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSAS
tags:
  - MDX

---
This week I&#8217;ve been working on another new cube which had the time spent, which is in minutes. To pretty it up it wanted to be in days, mins and hours.

Here is a simplified version of the final output

<a href="//matt40k.uk/img/2016/11/prettytime.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-948" src="//matt40k.uk/img/2016/11/prettytime.png" alt="prettytime" width="266" height="38" /></a>

and the hopefully easier to understand MDX code

<div class="gist-oembed" data-gist="matt40k/b45d73245d88405c06722d65e1a0bdfe.json">
</div>

Adding the days option isn&#8217;t much more work &#8211; it does however make the code look alot more angry. Also you have the issue of what is a day &#8211; is it 24 hours? Is it the working hours, or is it less, is it the realistic billable time after you deduce admin time?
