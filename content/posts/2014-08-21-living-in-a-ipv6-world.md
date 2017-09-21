---
title: Living in a IPv6 world
author: matt
type: post
date: 2014-08-21T22:12:29+00:00
url: /2014/08/living-in-a-ipv6-world/
categories:
  - Projects

---
I&#8217;ve finally gotten round to setting up the <a href="https://www.mythic-beasts.com/servers/virtual" target="_blank" rel="nofollow">VDS</a> <a href="https://www.mythic-beasts.com" target="_blank" rel="nofollow">Mythic-Beasts</a> have kindly donated to host the API backend for one of my open-source projects. A few nights ago I enabled IPv6 and today when I went to run apt-get update it just hung saying:

> 0% [Connecting to gb.archive.ubuntu.com (2a01:450:10:1::10)]

As they had previously worked, I suspect it&#8217;s IPv6 problem, quick google and&#8230;

<a href="http://askubuntu.com/questions/272796/connecting-to-archive-ubuntu-com-takes-too-long" target="_blank" rel="nofollow">http://askubuntu.com/questions/272796/connecting-to-archive-ubuntu-com-takes-too-long</a>

> <p style="color: #333333;">
>   I solved this on 12.10 by editing <strong>/etc/gai.conf</strong> and uncommenting the line:
> </p>
> 
> <pre style="color: #333333;"><code style="color: #222222;">
#
#    For sites which prefer IPv4 connections change the last line to
#
precedence ::ffff:0:0/96 100
</code></pre>

Bingo.
