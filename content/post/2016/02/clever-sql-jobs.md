---
title: Clever SQL Jobs?
author: matt40k
type: post
date: 2016-02-09T14:24:44+00:00
url: /2016/02/clever-sql-jobs/
categories:
  - Blog
  - Business Intelligence
  - Projects
  - SQL Server

---
Just thinking out load (because its good to get feedback)

{{< gist matt40k 697050198120464384 >}}

Just to expand on my tweet. I&#8217;ve lot of SSIS packages for load and building my BI warehouse (SSAS cubes), now currently I have a SQL job that has multiple steps

For example

  1. Load data from Source system into Staging
  2. Build ODS intermediate tables
  3. Build Warehouse tables

And this works for DataMart where they are a denormalized copy of a single source system, but when the source system, or the intermediate tables, are used multiple times, you don&#8217;t want to run them multiple times. Equally I don&#8217;t want to figure this out each time we add a new package.

I basically want a controller task that manages it.

We have a automation build\deploy process,  so you commit the (SSDT\SSIS\SSAS) packages and it deploys it and creates a SQL job for each SSIS package. We could add step to trigger the controller to update the schedules based on the change.

Now we would need to define the dependencies, basically we need build a hierarchy. Technically I could read the SSIS packages then parse the select statements then create some logic to work it out automatically, but for now, it&#8217;ll be a static table(s).

So. Do I create a SQL stored procedure to create a SQL job(s) with multiple steps or a SSIS package using something like BIML?

&nbsp;

&nbsp;
