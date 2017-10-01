---
title: Authenticating IoT
author: matt40k
type: post
date: 2017-01-08T21:46:21+00:00
url: /2017/01/authenticating-iot/
categories:
  - Blog
  - Projects
tags:
  - IoT
  - PayPal

---
I was re-entering my password into our <a href="https://www.nowtv.com/tv-boxes" target="_blank" rel="nofollow">NowTV box</a> in the bedroom when it occurred to me. Authentication sucks on the Internet of Things (IoT). The problem is you have a simple device with minimal extras. On the NowTV you have a basic remote that looks like this:

<a href="//matt40k.uk/img/2017/01/nowtv_remote.jpg" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-2380" src="//matt40k.uk/img/2017/01/nowtv_remote.jpg" alt="" width="800" height="450" srcset="//matt40k.uk/img/2017/01/nowtv_remote.jpg 800w, //matt40k.uk/img/2017/01/nowtv_remote-300x169.jpg 300w, //matt40k.uk/img/2017/01/nowtv_remote-768x432.jpg 768w" sizes="(max-width: 800px) 100vw, 800px" /></a>

Can you imagine entering a password with a length of over 20 that&#8217;s a mixture of numbers, special characters and both upper and lower case characters? Now imagine changing that password. Regularly.

If you have to press the arrows 5 times per character, that&#8217;s over 100 presses! That&#8217;s insane!

So, what&#8217;s the solution? Well I think the technology already exists. And <a href="https://www.paypal.com/" target="_blank" rel="nofollow">PayPal</a> already had it <a href="https://worldwide.espacenet.com/publicationDetails/biblio?FT=D&date=20161222&DB=EPODOC&locale=en_EP&CC=US&NR=2016373428A1&KC=A1&ND=4#" target="_blank" rel="nofollow">patented</a>. QR codes. Not sure if <a href="https://www.paypal.com/" target="_blank" rel="nofollow">PayPal </a>had thought about using it for IoT, I suspect they only thought about using it as a way of paying. So you have a QR code on the door then you scan it via the <a href="https://www.paypal.com/" target="_blank" rel="nofollow">PayPal</a> app, pay, then get your tickets sent to your Wallet to the club. Or scanning the code from the receipt to pay the bill.

For IoT, the device would generate a encryption key, this would be re-generated when the device is wiped, for example when it is resold, the device would then display a QR code, via a small E-Ink display or such, that would allow pairing (or such) between the device and a user account &#8211; via a internet connection to a web service. Unpairing the device from the user account would revoke the encryption key requiring the device to regenerate a new key (and a new QR code). However wiping the device would destroy the encryption key but wouldn&#8217;t revoke the key, this would cause some housekeeping to occur. Perhaps trying to unpairing first, however it shouldn&#8217;t be dependent on a internet connection to a web service in order to work. If the hard reset button is pressed, it **must** destroy the encryption key regardless if the unpairing fails or not. It must force this.

It&#8217;ll be interesting to see if <a href="https://www.paypal.com/" target="_blank" rel="nofollow">PayPal</a> expands then authentication  business beyond just for payments in the future.
