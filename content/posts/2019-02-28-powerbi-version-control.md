---
title: Version control in PowerBI
date: '2019-02-28T20:28:21+00:00'
author: matt40k
type: post
description: 'Adding version control support in PowerBI'
draft: false
tags: 
  - Power BI
categories:
  - Power BI
---
PowerBI is a awesome self-service reporting tool that has a low-level of entry for new comers, that allows end-users (ie Non-IT folks) to deliver elegant insight into data via interactive reports.

It’s biggest flaw however is it doesn’t have any kinda of code version control support. Like it’s impossible.

Various people/companies have developed hacky solutions however this goes against PowerBI core design of being a simple, self service tool.

PowerBI needs simple, transparent to the end user version control support. With Microsoft moving towards Git and their recent purchase of GitHub, built in Git makes the most sense.

PowerBI Desktop should create git repository for each report/dataset/project/workspace. 

The .gitignore could be used to exclude the data.

The “save” function should then be changed into “export” 

> .pbix - export with data

> .pbit - export without data

This will promote not only git but version control to new developers. Currently there a number of “scripters” who develop solutions that believe their work isn’t worthy of being put into version control, or believe it’s too complex. It’s always worth putting code into version control and it doesn’t have to be hard.

This will also allow IT to define where repositories are push too, give them access and in the future apply tests - such as recommending using a M code to generate a column at ETL rather then DAX which is generated every time it is required (ie a massive performance hit)

[Please vote to make this happen](https://ideas.powerbi.com/forums/265200-power-bi-ideas/suggestions/36978934-built-in-git-support-in-powerbi-desktop)
