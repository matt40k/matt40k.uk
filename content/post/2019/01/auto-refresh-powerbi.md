---
title: Auto refreshing PowerBI
date: '2019-01-22T22:02:41+00:00'
url: /2019/01/auto-refresh-powerbi/
author: matt40k
type: post
description: 'Auto refreshing a Power BI'
draft: false
tags: 
  - Power BI
categories:
  - Power BI
---

One of the problems we hit today was getting a Power BI to automatically refresh. The underlying data is updated every 5 mins, however the actual Power BI only refreshes when the user interacts with the report despite using DirectQuery. To overcome this, we've built a simple HTML page that used a bit of JavaScript magic to force a refresh and the new Secure Embed feature.

First, we need to get a code for the report, open the report then click File > Embed
(You can select 'Publish to web' - this means you don't need to login to view the report, however anyone in the world could access the report)

![Embed](//matt40k.uk/img/2019/01/embed.png)

Once you've selected embed, you need to copy the iframe code

![Embed code](//matt40k.uk/img/2019/01/embedCode.png)

You then need to put this iframe code into a HTML file. Below is a Gist for basic HTML page with the JavaScript magic to force a refresh every 1 min.

If you copy the code below into notepad inserting the iframe code then saving it as a .html (for example report.html)

{{< gist matt40k 390b113c36f245f8ac92bacb17914b1e >}}

One thing worth changing on the iframe code Power BI generates is changing the frame size.
> <iframe width="1140" height="541.25" 
to
> <iframe width="100%" height="100%" 
This is allow Power BI to use the full web browser real estate. You can ofcourse use F11 to make most web browsers go full screen. Great for displaying Power BI on the big screen!
