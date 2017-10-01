---
title: Why Microsoft Business Intelligence is on my radar
author: matt40k
type: post
date: 2014-07-03T23:11:40+00:00
url: /2014/07/why-microsoft-business-intelligence-is-on-my-radar/
categories:
  - Business Intelligence
  - IBM Cognos
  - Microsoft
  - SQL Server

---
In my day job I&#8217;ve been looking at SQL Server 2012 recently (I know SQL Server 2014 out before you say anything!), I&#8217;ve had a developer license for a while but unfortunately other priorities have been consuming my time and I&#8217;ve only managed to get a dev server build, SQL 2012 installed and not much else up till a few days ago.

Our current Business Intelligence platform is using SQL Server 2008 (not R2) for the database backend and SQL Server Integration Services (SSIS) BIDS for the ETL. We use IBM Cognos Business Intelligence for the presentation layer, which we upgraded to 10.2.1 at the being of the year from 8.4.1, after a massive sprint with a mix of in house and a third party company. In total we created over 100 reports in about 6 months between us! Half of them being created by us in house staff &#8211; which was 2 full-time report writers (me being one) and the odd bit of time from the 2 report writers when it got a bit hairy. It was nice upgrading to 10.2.1, other then waiting for Fix Pack 2 to resolve the Tomcat memory leak, as allowed me to sink my teeth into the technical side which is my background &#8211; techy. Beyond the techy side of it it was a big team effort to get some of the reports re-written as the method we used to do the drill-downhierarchy was &#8220;fixed&#8221; in 10.2.1 so it stopped working and after battling for days with ancestors we just re-did it. It did give us really good in-depth knowledge of the reports the third party had written which has helped us supporting them going forward and also helped us improve our techniques and knowledge &#8211; we&#8217;re always re-factoring our work to bring about improvements!

A few weeks ago, we had to novate our Cognos license, turns out, at the last minute I might add, we couldn&#8217;t do it. IBM wouldn&#8217;t allow it. So we had to relicense. IBM had just hit our list of suppliers we don&#8217;t like. Bad news, big bill, good news, all our licenses now had Query Studio licenses &#8211; ie they can run ad-hoc queries. Bad news, our models are really designed for our static reports and our staff aren&#8217;t all trained in Query Studio. Starting to see why we&#8217;re looking at other BI tools?

So, I basically started looking at Microsoft BI because&#8230;

  * I had a developer license for SQL 2012 &#8211; cost, less then £20, which allowed me to build and demo anything I created. IE I&#8217;m not spend thousands on a tool that I maybe able to use without expensive training
  * Our data warehouse is SQL Server
  * We had just signed a Microsoft Enterprise Agreement
  * Our staff know Excel &#8211; everything ends up in Excel data wise

&nbsp;

&nbsp;
