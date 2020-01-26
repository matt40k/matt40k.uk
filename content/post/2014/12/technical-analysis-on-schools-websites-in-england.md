---
title: Technical Analysis on Schools websites in England
author: matt40k
type: post
date: 2014-12-05T10:31:31+00:00
url: /2014/12/technical-analysis-on-schools-websites-in-england/
categories:
  - Business Intelligence
  - Projects
  - SQL Server
tags:
  - OpenData

---
So in my <a href="http://matt40k.uk/2014/12/are-you-ready-for-ipv6/" target="_blank" rel="nofollow">last blog post</a> I asked, <a href="http://matt40k.uk/2014/12/are-you-ready-for-ipv6/" target="_blank" rel="nofollow">are you ready for IPv6</a>? The post came about when I was looking at Schools MIS data, which <a href="http://eduwarenetwork.com/mis_market_statistics/" target="_blank" rel="nofollow">Graham</a>, <a href="http://bringmoredata.blogspot.co.uk/2014/11/mis-market-moves-sims-still-dominate.html" target="_blank" rel="nofollow">Joshua</a> and <a href="http://matt40k.uk/" target="_blank" rel="nofollow">myself</a> have being look at to see who are the big movers and shakers in the Schools administration software (MIS) arena. Data is collected by what software suppliers a school uses to submit the School Census (in England) which is requested under the Freedom of Information (FOI) from <a href="https://www.gov.uk/government/organisations/department-for-education" target="_blank" rel="nofollow">Department of Education(DfE)</a> (saving having to FOI every individual school). In order to enhance this data I was joining the data onto the general schools data that can be extract from <a href="http://www.education.gov.uk/edubase/home.xhtml" target="_blank" rel="nofollow">EduBase</a>. Looking at the data I notice that the website addresses listed in the extract was of extremely poor quality. A number even had email addresses listed!

This got me thinking, are schools ready for IPv6? If Sky are running out of IPv4 addresses and offer IPv6 only connections at a lower price, how many parents are going to jump on the deal only to find out they can&#8217;t access their child&#8217;s school website later on. After a bit of scripting and a support call to <a href="https://www.mythic-beasts.com/" target="_blank" rel="nofollow">Mythic-Beasts</a> to enable a response in JSON that I could automate, I had the results. It wasn&#8217;t good.

Still, no-ones ready for IPv6 are they, sure they&#8217;ll be ready in time. Won&#8217;t they?

> We can only judge the future from what we have suffered in the past
> 
> <p style="text-align: right;">
>   Themistocles , <em>300: Rise of an Empire</em>
> </p>

<p style="text-align: left;">
  To this effect, I&#8217;ve gathered data to look at:
</p>

  * Domain registration correctness
  * Content management systems
  * Document type definition
  * Raw HTML homepage size
  * Google Analytics
  * IPv6 readiness

At the moment I&#8217;m still creating the presentation detailing my findings, but you can download the raw data from: <a href="https://github.com/matt40k/SchoolsWebsites-England" target="_blank" rel="nofollow">https://github.com/matt40k/SchoolsWebsites-England</a>
