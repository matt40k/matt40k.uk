---
title: Companies House
date: '2018-08-07T20:48:32+00:00'
author: matt40k
type: post
description: 'Loading Companies House data into SQL Server'
---
I've added another API to seahorse - which returns Companies House data dumps. They provide it as a single zip or split up into 5 zips. Within the zip is the data in a CSV file.
<a href="//seahorse.matt40k.uk/api/companieshouse" target="_blank">seahorse.matt40k.uk/api/companieshouse</a>

The question now is, do I create a BIML script to generate a SSIS package that'll load it into SQL Server? The traditional method.

Or do I do something I bit more modern. Create Azure Function to check for a new data dump, download it into Azure Blob storage then execute a stored procedure to load it into SQL Server, utilizing the new functionality that allows SQL Server to read from Azure blobs. I admit I've previously done this but by loading it into AWS Redshift via S3 bucket.
