---
title: Using PowerShell to check setup
author: matt40k
type: post
date: 2015-12-09T20:16:49+00:00
url: /2015/12/using-powershell-to-check-setup/
categories:
  - Blog
tags:
  - PowerShell

---
So I was handed over some new servers, before I got started I wanted to check everything was as it was suppose to be, so I wrote a few PowerShell scripts to check each server was setup correctly. I wanted my DEV to 100% match my UAT and so on.

First, I wanted to check who has local administrator access on the servers.

<div class="gist-oembed" data-gist="matt40k/e1bcdefbe89b27c069aa.json">
</div>

Next, I wanted to check the drives &#8211; I wanted to make sure each drive letter was the same across environments and all had a proper label.

<div class="gist-oembed" data-gist="matt40k/632dd4b90688efac3bbd.json">
</div>

Finally, I wanted to check the service accounts that my SQL services were running as, again, PowerShell to the rescue.

<div class="gist-oembed" data-gist="matt40k/ec2b9237a112380d878c.json">
</div>
