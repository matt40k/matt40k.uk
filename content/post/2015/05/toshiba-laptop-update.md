---
title: Toshiba laptop update
author: matt40k
type: post
date: 2015-05-31T07:40:58+00:00
url: /2015/05/toshiba-laptop-update/
categories:
  - Blog

---
Just an update to <a href="//matt40k.uk/2015/05/toshiba-r50-b-12q/" target="_blank">my previous post about the Toshiba Laptop</a>, I&#8217;ve been thinking about reinstalling the Toshiba laptop with Ubuntu, but before I do that, I want a backup. Luckily, I still have the original 500GB hdd spare, I just need a USB caddy. Luckily my local Curry&#8217;s had a USB3.0 one (<a href="http://www.currys.co.uk/gbuk/computing/ipad-tablets-and-ereaders/tablets/tablet-accessories/pny-ssd-and-2-5-hard-drive-enclosure-and-upgrade-kit-22082146-pdt.html" target="_blank" rel="nofollow">PNY SSD and 2.5&#8243; Hard Drive Enclosure and Upgrade Kit</a>), before anyone comments about how I could of got one cheaper off eBay, just remember, I was able to get it same day and it included Acronis.

Before I swapped the HDD out for a SSD, I ran <a href="https://gist.github.com/matt40k/afb3623292dbd62151cd" target="_blank" rel="nofollow">a simple PowerShell script to get a list of installed applications</a>, you can see the list <a href="https://gist.github.com/matt40k/6b688214e7b8b117df3d" target="_blank" rel="nofollow">here</a>.<figure id="attachment_370" style="width: 660px" class="wp-caption aligncenter">

<a href="//matt40k.uk/img/2015/05/Desktop.png" target="_blank" rel="nofollow"><img class="wp-image-370 size-large" src="//matt40k.uk/img/2015/05/Desktop-1024x576.png" alt="Desktop" width="660" height="371" srcset="//matt40k.uk/img/2015/05/Desktop-1024x576.png 1024w, //matt40k.uk/img/2015/05/Desktop-300x169.png 300w, //matt40k.uk/img/2015/05/Desktop.png 1366w" sizes="(max-width: 660px) 100vw, 660px" /></a><figcaption class="wp-caption-text">Desktop</figcaption></figure> <figure id="attachment_369" style="width: 660px" class="wp-caption aligncenter"><a href="//matt40k.uk/img/2015/05/IE.png" target="_blank" rel="nofollow"><img class="wp-image-369 size-large" src="//matt40k.uk/img/2015/05/IE-1024x576.png" alt="IE" width="660" height="371" srcset="//matt40k.uk/img/2015/05/IE-1024x576.png 1024w, //matt40k.uk/img/2015/05/IE-300x169.png 300w, //matt40k.uk/img/2015/05/IE.png 1366w" sizes="(max-width: 660px) 100vw, 660px" /></a><figcaption class="wp-caption-text">Internet Explorer (Homepage)</figcaption></figure> <figure id="attachment_368" style="width: 660px" class="wp-caption aligncenter"><a href="//matt40k.uk/img/2015/05/hdd.png" target="_blank" rel="nofollow"><img class="wp-image-368 size-large" src="//matt40k.uk/img/2015/05/hdd-1024x576.png" alt="hdd" width="660" height="371" srcset="//matt40k.uk/img/2015/05/hdd-1024x576.png 1024w, //matt40k.uk/img/2015/05/hdd-300x169.png 300w, //matt40k.uk/img/2015/05/hdd.png 1366w" sizes="(max-width: 660px) 100vw, 660px" /></a><figcaption class="wp-caption-text">HDD Warning</figcaption></figure> 

One of the problems with traditional HDD is the fact they have moving parts, if your moving your laptop around and you bang it, it can get damage, Toshiba have implemented a safely feature where when movement is detected it moved the HDD file header to a safe position. It make sound a little bit extreme, but when your talking about a disc that spins at over 4000 RPM and is wafer thin, you kinda get why they&#8217;ve add the feature. Personally, SSD is a better fix. No moving parts 🙂
