---
title: Version control in PowerBI
date: '2019-02-28T20:28:21+00:00'
url: /2019/02/powerbi-version-control/
author: matt40k
type: post
description: 'Adding version control support in Power BI'
draft: false
tags: 
  - Power BI
categories:
  - Power BI
---
Power BI is a awesome self-service reporting tool that has a low-level of entry for new comers, that allows end-users (ie Non-IT folks) to deliver elegant insight into data via interactive reports.

It’s biggest flaw however is it doesn’t have any kinda of code version control support. Like it’s impossible.

Various people/companies have developed hacky solutions however this goes against Power BI core design of being a simple, self service tool.

Power BI needs simple, transparent to the end user version control support. With Microsoft moving towards Git and their recent purchase of GitHub, built in Git makes the most sense.

Power BI Desktop should create git repository for each report/dataset/project/workspace. 

The .gitignore could be used to exclude the data.

The “save” function should then be changed into “export” 

> .pbix - export with data

> .pbit - export without data

This will promote not only git but version control to new developers. Currently there a number of “scripters” who develop solutions that believe their work isn’t worthy of being put into version control, or believe it’s too complex. It’s always worth putting code into version control and it doesn’t have to be hard.

This will also allow IT to define where repositories are push too, give them access and in the future apply tests - such as recommending using a M code to generate a column at ETL rather then DAX which is generated every time it is required (ie a massive performance hit)

[Please vote to make this happen](https://ideas.powerbi.com/forums/265200-power-bi-ideas/suggestions/36978934-built-in-git-support-in-powerbi-desktop)

## Update

Just to expand on the "why version control \ git" from newbie point of view.

Version control is essential for any developer regardless of level. Version control allows you to track changes. It's highly unlikely you are going to ever develop a perfect solution, even if you are a expert, first time that isn't going to require any changes. By tracking changes it allows you to quickly identify WHEN something has changed, WHAT has changed - as you can "diff" the old vs the new file and if you have added a useful commit message, WHY something has changed.

Git is a distributed version control system. This means there is no spoon. I mean there is no server. Every copy has everything and is equal. Because of this commits are performed locally and you "push" them to remote servers, this means you can develop offline then push when you are back online. Pushing basically means you have a backup and allows others to "clone" your work (permissions willing). Git has become the defacto code version control.

The current problem is Power BI Desktop creates PBIX or PBIT which are .zip binary files. This means you can't "diff" the files, so you can't track changes - you can't see that you've changed the [Price] measure to [Price - Exc VAT]. In addition because you can't "diff", you can't merge changes - which you need to do if you have more then one developer working on a project. So if Dev-A changes [Price] to [Price - Exc VAT] and Dev-B adds [Price - Inc VAT] you can't work independently then merge the two together. This limits Power BI development to a single developer.
