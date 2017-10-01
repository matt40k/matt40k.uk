---
title: Auditing – Who’s viewed my record?
author: matt40k
type: post
date: 2016-04-05T23:22:09+00:00
url: /2016/04/auditing-whos-viewed-my-record/
categories:
  - Blog

---
As some of you are aware I currently working for a local authority and anyone who has been following local government news in England will know the bonds between local authority and the health authority, aka the NHS, are growing. As are other parts of the government for that matter, both central, other local authorities as well as charities, but for now, I am focusing on the health part. Specifically the part around what that means. Health data has much stricter rules, the data is no more sensitive then some data already held by the local authority in my opinion. Perhaps, they are perceived as stricter when in fact they are, more evolved. Sharing health data is a lot more common nowadays, it&#8217;s more defined, it&#8217;s been through the growing pains (boy has the NHS had some IT growing pains) and has grown into stable mature process. This is of course making the local authority sound bad, it isn&#8217;t, they have been quietly learning from its elder brother, observing what has gone wrong and using the things that have gone right. There is however, still too much manual spreadsheets occurring, it&#8217;s a long road and but progress is being made.

So with the new business intelligence platform being developed, we need to review our existing platform, for this post, I&#8217;m talking (well writing) about auditing. Auditing on old platform was enabled. But it wasn&#8217;t really auditing. It was usage. It had a business focus.&nbsp;

  * What? Reports / Users
  * When? When was it run
  * Why? Was it worth writing the report

On the new platform we need true auditing. We almost need the same level of auditing as banks. BI is however, read-only, our auditing requirement needs to only be reactive, we don&#8217;t need to define triggers on the data to kick off workflow. We can get away with running an ETL job to extract the audit logs and transform it into a standard star fact/dimensions data structure.

The solution I have design for us, is to use the uber fast multi dimensional cube for analysis (which is what it designed for) and Reporting Services (SSRS) using raw T-SQL for detail. Sensitive data is not placed in the cube. The idea is cube has numbers with the ability to slice and dice using a variety of items (dimensions) &#8211; to a certain point. So for example, say there are 50 children in care, you could then slice this by gender, then by age group, then by ethnicity and so on. This data in itself isn&#8217;t sensitive. If you print this off and left it on a train, what would happen? Not much. This data is often published by the government and quoted by charities. NB: A word of warning however, a direct link into the raw system can be a dangerous things. Entering data is prone to mistakes and giving direct access will remove the quality gate data stewards provide, that said more prompt data more frequently, even with a few mistakes is often going to be better then out-of-date.

This leads me up to the detail. The detail allows a select few to go beyond those numbers, to drill into those numbers into a SSRS report. Now, one of the nice abilities of having an on-prem BI platform is we can store the raw uncut original data from the source system. This means we can work our way down to the bottom grain of data. Which makes debugging and testing a lot easier. It however make the definition of what is sensitive a lot harder. It sounds simple, but it can get rather messy when you get down to the nitty gritty. This nitty gritty gets audited. It gets audited using the standard Audit feature in SQL Server which has been a part of SQL Server since 2008 version. This has, from what I&#8217;ve seen from UAT, reading and talking to others, provided a low performance impact binary file audit log. This in turn gets ETL via a SSIS package into warehouse. They was a little design consideration round the to-be audited star schema, luckily the sensitive fields were already in one dimension and bit of ETL magic to make it a bit more bulletproof.

The end result. The business controls access for users to self-serve data analysis, in near realtime, without buying a license, in short they can give users access without access to the raw data. The business can use the same tools and drill down to the raw data. Access to the raw is fully audited and can be reported on by the business so we can be held accountable. It&#8217;s all about trust.
