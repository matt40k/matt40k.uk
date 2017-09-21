---
title: SQL Compare failed
author: matt
type: post
date: 2016-05-12T21:32:03+00:00
url: /2016/05/sql-compare-failed/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSDT
tags:
  - T-SQL

---
Another day, another problem. Todays problem was incorrect column length which was causing a SSIS package to fail. Historically I use a freeware tool to compare the different environments schema, but lately I just don&#8217;t bother, I have continuous deployment so its easier just to hit the deploy button then it is to try and figure it out. Well today I decided I wanted to it old school &#8211; although I&#8217;ve been using the SSDT SQL compare in my deployments, I&#8217;ve not actually used it in terms of viewing the differences.

Doing so its pretty easy, I already have a my database project setup in Visual Studio, all I then did was right-click then Schema Compare&#8230;

The app will then open and you select, from the right hand menu, the target, the database you want to compare your project with. Then you just click the compare button.

This appeared to work but didn&#8217;t display any results. When you look at the bottom status bar it reads

> Comparison complete. No differences detected. Restricted comparison. See Error List for details.

I knew there we at least some differences. I then click on the Error List table below it which revealed

> The reverse engineering operation cannot continue because you do not have View Definition permission on the &#8216;Warehouse&#8217;

Googling the problem lead me to a number of recommendations, some didn&#8217;t work (like restricting it to only tables), others I didn&#8217;t want to do &#8211; I don&#8217;t want to give myself db_owner on production. The final solution came as a simple one liner

`GRANT VIEW Definition TO [DOMAIN\user]`

Just added it to my Database Project as Post-Deployment script and its now comparing ok within Visual Studio (SSDT).
