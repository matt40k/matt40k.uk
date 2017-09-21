---
title: Cloudflare parser bug
author: matt
type: post
date: 2017-02-24T22:20:51+00:00
url: /2017/02/cloudflare-parser-bug/
categories:
  - Blog

---
So once again we have another major security leak. <a href="https://bugs.chromium.org/p/project-zero/issues/detail?id=1139" target="_blank" rel="nofollow">You can read about it, here</a> and below is the email CEO Matthew Prince wrote to customers:

> Dear Cloudflare Customer:
> 
> Thursday afternoon, we published a blog post describing a memory leak caused by a serious bug that impacted Cloudflare&#8217;s systems. If you haven&#8217;t yet, I encourage you to read that post on the bug:
> 
> <a href="http://cloudflare.us5.list-manage.com/track/click?u=d80d4d74266c0c044b0bcd7ca&id=3ff7537b84&e=732308dd89" target="_blank" data-saferedirecturl="https://www.google.com/url?hl=en-GB&q=http://cloudflare.us5.list-manage.com/track/click?u%3Dd80d4d74266c0c044b0bcd7ca%26id%3D3ff7537b84%26e%3D732308dd89&source=gmail&ust=1488058256890000&usg=AFQjCNER8iXt3WdcnE695zWniExz6WcB2g" rel="nofollow">https://blog.cloudflare.com/<wbr></wbr>incident-report-on-memory-<wbr></wbr>leak-caused-by-cloudflare-<wbr></wbr>parser-bug/</a>
> 
> While we resolved the bug within hours of it being reported to us, there was an ongoing risk that some of our customers&#8217; sensitive information could still be available through third party caches, such as the Google search cache.
> 
> Over the last week, we&#8217;ve worked with these caches to discover what customers may have had sensitive information exposed and ensure that the caches are purged. We waited to disclose the bug publicly until after these caches could be cleared in order to mitigate the ability of malicious individuals to exploit any exposed data.
> 
> In our review of these third party caches, we discovered data that had been exposed from approximately 150 of Cloudflare&#8217;s customers across our Free, Pro, Business, and Enterprise plans. We have reached out to these customers directly to provide them with a copy of the data that was exposed, help them understand its impact, and help them mitigate that impact.
> 
> Fortunately, your domain is not one of the domains where we have discovered exposed data in any third party caches. The bug has been patched so it is no longer leaking data. However, we continue to work with these caches to review their records and help them purge any exposed data we find. If we discover any data leaked about your domains during this search, we will reach out to you directly and provide you full details of what we have found.
> 
> To date, we have yet to find any instance of the bug being exploited, but we recommend if you are concerned that you invalidate and reissue any persistent secrets, such as long lived session identifiers, tokens or keys. Due to the nature of the bug, customer SSL keys were not exposed and do not need to be rotated.
> 
> Again, if we discover new information that impacts you, we will reach out to you directly. In the meantime, if you have any questions or concerns, please don’t hesitate to reach out.
> 
> Matthew Prince
  
> Cloudflare, Inc.
  
> Co-founder and CEO

So lets be clear

  * &#8230;the greatest period of impact was from February 13 and February 18 with around 1 in every 3,300,000 HTTP requests through Cloudflare potentially resulting in memory leakage (that’s about 0.00003% of requests).
  * Only customers who use Automatic HTTPS Rewrites, Server-Side Excludes and Email Obfuscation were affected.
  * &#8230;data that had been exposed from approximately 150 of Cloudflare&#8217;s customers across Free, Pro, Business, and Enterprise plans
  * CloudFlare is SaaS
  * Security hole was completely closed in 7hrs 11mins from being Tweeted about an issue
  * Security hole was mostly closed off in 1 hr 8mins
  * Production fix and service restored in 3 days 10 hrs 9mins
  * <a href="http://www.doesitusecloudflare.com/?url=matt40k.uk" target="_blank" rel="nofollow">People are jumping on the problem making it sound worse then it was</a> (don&#8217;t get me wrong it was bad, but no where as bad as Heartbleed, Heartbleed, still IS a problem)
  * CloudFlare have been very transparent

&#8230;And this is why I review code I take on-board, regardless if it works and advise others to review my code

&nbsp;
