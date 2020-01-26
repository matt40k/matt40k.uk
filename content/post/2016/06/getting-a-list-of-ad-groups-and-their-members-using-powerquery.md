---
title: Getting a list of AD Groups and their members using PowerQuery
author: matt40k
type: post
date: 2016-06-14T20:54:36+00:00
url: /2016/06/getting-a-list-of-ad-groups-and-their-members-using-powerquery/
categories:
  - Business Intelligence
  - Microsoft
  - Power BI
tags:
  - M
  - Power BI
  - PowerQuery

---
> The Power Query Formula Language (informally known as &#8220;M&#8221;) is a powerful mashup query language optimized for building queries that mashup data. It is a functional, case sensitive language similar to F#,  which can be used with Power Query in Excel and Power BI Desktop.

A few days ago I got asked to produce a list of users (and their email address) in a number of AD Groups. I already had a SSIS package that had a script task to pull this data from Active Directory and push it into a SQL database and we have a PowerShell script to get the same data in our code repo. After work I set about repeating it but using PowerQuery.

Apart from one quirk the process was pretty straightforward. PowerQuery has built in support for Active Directory. Just click the **Data** tab, then select **New Query** > **From Other Sources** > **From Active Directory**

<a href="//matt40k.uk/img/2016/06/pq_menu.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-784" src="//matt40k.uk/img/2016/06/pq_menu.png" alt="PowerQuery - Excel > Menu" width="913" height="565" srcset="//matt40k.uk/img/2016/06/pq_menu.png 913w, //matt40k.uk/img/2016/06/pq_menu-300x186.png 300w, //matt40k.uk/img/2016/06/pq_menu-768x475.png 768w" sizes="(max-width: 913px) 100vw, 913px" /></a>

This will then pop up with a windows asking for you to select your domain, assuming your machine is joined to the domain and your logged on as a domain user, this should be prefilled in with the correct domain.

<a href="//matt40k.uk/img/2016/06/pq_connection.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-785" src="//matt40k.uk/img/2016/06/pq_connection.png" alt="PowerQuery - Excel > Connection" width="602" height="215" srcset="//matt40k.uk/img/2016/06/pq_connection.png 602w, //matt40k.uk/img/2016/06/pq_connection-300x107.png 300w" sizes="(max-width: 602px) 100vw, 602px" /></a>

The next window just asks you confirm your credentials, you&#8217;ll most likely want to use your current windows user.

After you&#8217;ve connected to your Active Directory, you&#8217;ll be able to navigator, your be able to select your domain from your forest and then select the object you want to query. For this example, select your domain then select **group**, then click **Edit**.

<a href="//matt40k.uk/img/2016/06/pq_navigator.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-786" src="//matt40k.uk/img/2016/06/pq_navigator.png" alt="PowerQuery - Excel > Navigator" width="885" height="704" srcset="//matt40k.uk/img/2016/06/pq_navigator.png 885w, //matt40k.uk/img/2016/06/pq_navigator-300x239.png 300w, //matt40k.uk/img/2016/06/pq_navigator-768x611.png 768w" sizes="(max-width: 885px) 100vw, 885px" /></a>

This will then open up the Query Editor

<a href="//matt40k.uk/img/2016/06/pq_query.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-787" src="//matt40k.uk/img/2016/06/pq_query.png" alt="PowerQuery - Excel > Query Editor" width="1534" height="582" srcset="//matt40k.uk/img/2016/06/pq_query.png 1534w, //matt40k.uk/img/2016/06/pq_query-300x114.png 300w, //matt40k.uk/img/2016/06/pq_query-768x291.png 768w, //matt40k.uk/img/2016/06/pq_query-1024x389.png 1024w, //matt40k.uk/img/2016/06/pq_query-1200x455.png 1200w" sizes="(max-width: 1534px) 100vw, 1534px" /></a>

This will then list out the groups, or at least a sample. Click on the left\right arrow on **securityPrincipal** column header, this then bring up a filter window, select **sAMAccountName** and click on OK. This will give you the friendly name your more then likely to know the groups by.

Now its a question of filtering the list &#8211; if you right-click on the **sAMAccountName** and select **Text Filters** > **Begin With**. You can select one of the other options, if you make a mistake or you want to refine it, on the right-hand side, you have **Query Settings** > **Applied Steps**, if you click the cog next to **Filtered Rows** your get

<a href="//matt40k.uk/img/2016/06/pq_filter.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-789" src="//matt40k.uk/img/2016/06/pq_filter.png" alt="PowerQuery - Filter" width="602" height="215" srcset="//matt40k.uk/img/2016/06/pq_filter.png 602w, //matt40k.uk/img/2016/06/pq_filter-300x107.png 300w" sizes="(max-width: 602px) 100vw, 602px" /></a>

this hopefully doesn&#8217;t need any explanation. You can of course filter on other columns if required, such as OU group.

Adding the users involves expanding the member

And the final M script looks like field like we did with securityPrincipal until we get to the individual user object.

The last point is where I hit a few snags. Firstly, I couldn&#8217;t expand into the user object, luckily, clicking on **Advanced Editor** on the **Home** tab revealed the M code. I&#8217;ve included my code below which I hope will help.

<div class="gist-oembed" data-gist="matt40k/7ded896bf9fc14bc21602ceebf6be7dd.json">
</div>

I&#8217;ve personally found this a useful dive into PowerQuery, hopefully you have too 🙂
