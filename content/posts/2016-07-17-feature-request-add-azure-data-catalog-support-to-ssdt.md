---
title: Feature request – Add Azure Data Catalog support to SSDT
author: matt
type: post
date: 2016-07-17T22:11:46+00:00
url: /2016/07/feature-request-add-azure-data-catalog-support-to-ssdt/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSDT

---
One of the annoy parts of building a warehouse is building the staging database, its an important first step. The staging database is replica of the source systems. <a href="http://bimlscript.com/" target="_blank" rel="nofollow">BIML</a> can provide away to accelerate this process, however its not perfect. BIML is designed to create SSIS packages &#8211; and it does this very, very, well. SQL database objects, not so well. SSDT does this well.

The first step in the designing a warehouse is discovery, <a href="https://azure.microsoft.com/en-gb/services/data-catalog/" target="_blank" rel="nofollow">Azure Data Catalog</a> is an excellent tool for doing the discovery, it allows you to connect to a wide array of data source types and gather the meta data that can be used to build the staging database.

My feature request is to add support for Azure Data Catalog to SSDT. In a nutshell add a item to this menu list

<a href="//matt40k.uk/img/2016/07/IWouldLike.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-795" src="//matt40k.uk/img/2016/07/IWouldLike.png" alt="Feature request - SSDT" width="727" height="294" srcset="https://publish.matt40k.uk/wp-content/uploads/2016/07/IWouldLike.png 727w, https://publish.matt40k.uk/wp-content/uploads/2016/07/IWouldLike-300x121.png 300w" sizes="(max-width: 727px) 100vw, 727px" /></a>

&nbsp;
