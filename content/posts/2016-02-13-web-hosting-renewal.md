---
title: Web hosting renewal
author: matt
type: post
date: 2016-02-13T22:00:00+00:00
url: /2016/02/web-hosting-renewal/
categories:
  - Blog

---
One of the bad habbits I have picked up from working in Local Government is reviewing your options, regularly. As I approach my renewal for this site&#8217;s web hosting, I decided to revaluate the market.

(Short version, I&#8217;m with <a href="https://mythic-beasts.com" target="_blank" rel="nofollow">Mythic-Beasts</a> for another year)

Currently, I have the site hosted with <a href="https://mythic-beasts.com" target="_blank" rel="nofollow">Mythic-Beasts</a>. They are pretty cool folks, unfortantely one of there DC had a power cut recently &#8211; ok, only a few hours and I pay peanuts so I don&#8217;t expect much in terms of reduancy or fancy SLAs, but it did make me look at my options for a bit longer then normal.

Recently, I discovered <a href="http://projectnami.org/" target="_blank" rel="nofollow">Project Nami</a>, a fork of WordPress that replaces the MySQL database with MS-SQL (which I quite like). As you would expect, its bundled really nice for <a href="https://azure.microsoft.com/en-gb/" target="_blank" rel="nofollow">Azure</a>. I setup a quick test site on <a href="https://azure.microsoft.com/en-gb/" target="_blank" rel="nofollow">Azure</a> and had a play, it worked a exceedingly well, but the lack of IPv6 left me with a bitter taste. Why hasn&#8217;t Microsoft added support for IPv6! This would mean I would have to use <a href="https://www.cloudflare.com/" target="_blank" rel="nofollow">CloudFlare</a>, which isn&#8217;t exactly a problem. The summary outcome was Azure was overly complex, I&#8217;m not saying Microsoft hasn&#8217;t done a excellent job making it simple to setup and use, its just its overly complex for what I want, my content is static. Again, <a href="http://projectnami.org/" target="_blank" rel="nofollow">Project Nami</a> is excellent, its just, an extra complexity. <a href="https://www.cloudflare.com/" target="_blank" rel="nofollow">CloudFlare</a>, I&#8217;m still 50/50 on. I have another site using <a href="https://www.cloudflare.com/" target="_blank" rel="nofollow">CloudFlare</a> and I&#8217;ve had no problem, its just, again, its overly complex solution to simple problem. Lots of bells and whistles.

Going the other way, I looked at <a href="https://www.wordpress.com" target="_blank" rel="nofollow">WordPress.com</a>. This would the similest solution, but that comes at a price, at nearly 3x times the cost per year and alot more restrictions &#8211; no PowerBI iframes (well they haven&#8217;t added support&#8230; yet)*

So, now I&#8217;m back to <a href="https://mythic-beasts.com" target="_blank" rel="nofollow">Mythic-Beasts</a>, they have IPv6 support, are UK based, have excellent support, good value for money. They&#8217;ve also added support for <a href="https://letsencrypt.org" target="_blank" rel="nofollow">LetsEncrypt</a>. So HTTPS is free and only a few clicks &#8211; something that you can do with Azure, but with a £45 or above package. Sigh.

If nothing else this &#8220;forced&#8221; me to look at <a href="http://projectnami.org/" target="_blank" rel="nofollow">Project Nami</a> and look deeper into <a href="https://azure.microsoft.com/en-gb/" target="_blank" rel="nofollow">Azure</a>. <a href="https://azure.microsoft.com/en-gb/" target="_blank" rel="nofollow">Azure</a> is a pretty big beast thats getting bigger by the day. I&#8217;ve also reconfigured a few bits on my websites on <a href="https://mythic-beasts.com" target="_blank" rel="nofollow">Mythic-Beasts</a> (I still have a few things left to do!), so as always, it was worth reviewing the market.

* Yes, I am aware I haven&#8217;t published any public PowerBI reports&#8230; yet!
