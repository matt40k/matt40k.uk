---
title: Deploying SQL 2014, looking at SQL 2016 \ PowerBI
author: matt
type: post
date: 2015-11-06T13:37:02+00:00
url: /2015/11/deploying-sql-2014-looking-at-sql-2016-powerbi/
categories:
  - Blog
  - Business Intelligence
  - Microsoft

---
My current thoughts on SQL2016/PowerBI as deploying SQL2014.

Ok, so we’re looking at moving to pure SQL 2014 for our corporate BI solution. I say pure as we normally use SQL server as the backend then other tools on top, so we&#8217;re looking at enabling a lot of extra features we&#8217;ve technically had for years but just not enabled\setup\whatever. SQL2016 is on the way and we’re most likely going to upgrade pretty quick, lots of new features that look very useful. Power BI is out, but… we’re holding back, again we’re going to use it, its just a question of when it becomes the main BI tool.

So, we’ve already got the bulk of the data modelled in a multi-dimensional (MD) format, we just need to built a SSAS MD cube, the little pockets of data will be tabular cubes – users will use Excel for interacting with the data as well as end user reports – SharePoint will be the “portal” – much better then file system. SSRS will be for static reports – such as transactional reports that need to be static.

Going forward, it looks like PowerBI will replace the bulk of the Excel\SharePoint work – this will give a superior end-user interaction with the data, not only will it allow natural language interrogation of the data, but also personalised views – so you’ll see your data off the bat, you won’t have to drill down from your company, then team to get to your data. Data will come off the same ssas cube, so it’s still a single point for the data, its just a new way to interact with the data.

In terms of data security, we can limit PowerBI to just the summary data – via the ssas cube – so the fact PowerBI is hosted outside of the UK shouldn’t be a problem. The detailed stuff will still be on-prem – so SharePoint would still be needed in terms of a repository, but the bulk of the users will be using PowerBI, so its not as key, again, the data will come off the same ssas cube so we won’t have the “PowerBI says this but Excel says this” (insert caveat about people looking at different things &#8211; nb: need to check if can add url drill-down in PowerBI to say SSRS report with the detail).

The other bonus of the PowerBI is the friendly-ness towards the micro data sources – like the odd Excel spreadsheet. In terms of SQL2014, I was thinking about pushing towards Access Online – which backends the data into an Azure DB, still this will ultimately depend on policy on the data then the technology. Key is, we&#8217;ve got options.

In terms of end-user delivery SQL2014 will be perceived as SharePoint, really it will be Excel. The SharePoint is nothing more than a gloried online file share, we could in theory use OneDrive – at least until dashboards are more common but that won’t occur until the data is more readily accessible. The real power behind Excel will be using it correctly – using Excel as a visualisation tool to interact with the data and letting the SQL Server back end deal with grunt work – both in terms of the database and analysis services &#8211; rather then getting Excel to do all the grunt work and wonder why it so pants at it. The “SQL2016”/PowerBI rollout should be easier to land with end-users as there is a new thing being delivered, it’s easier to grasp a new product rather than an enabling some (new) features on an old tool. The key for delivering SQL2014 will be the SharePoint being the main place to go, it could become PowerBI. Plus side it means the SharePoint delivery is less critical as it could be replace if it doesn&#8217;t work out, if it does, lets hope this feature request goes head &#8211; <a href="https://support.powerbi.com/forums/265200-power-bi/suggestions/6740156-embed-in-sharepoint-office365" target="_blank" rel="nofollow">https://support.powerbi.com/forums/265200-power-bi/suggestions/6740156-embed-in-sharepoint-office365</a>. Does mean I have to have a look at branding and friendly urls for PowerBI.

For public data publication, in terms of “SQL2014”, I am thinking Excel to get the data, then saving as a CSV (or passing onto IT to produce a standard extract, again as CSV) – opening this in notepad or such to validate it contains no unwanted (such as protected fields) data, then publishing (onto public website\github??) – then using Tableau Public to produce graphs for public consumption – Tableau also allows easy export data (as csv). For PowerBI – I would hope you could use PowerBI to interact with the data, then export as a csv – verify it (perhaps in a basic online viewer – similar to the way github displays csv tables), then publish it – ideally on a marketplace type thing so it’s easy for others to find – again as a CSV and ideally with a <a href="https://github.com/matt40k/TabularDataPackageBuilder" target="_blank" rel="nofollow">Tabular Data Package</a> definition file, then allow embedding of a simple interaction of the data on a public website for no cost. So PowerBI license to produce, no license to see \ basic interaction of data (I guess csv file, json definition file, and d3.js) – then a PowerBI license to bring the data into own PowerBI to join with own data.
