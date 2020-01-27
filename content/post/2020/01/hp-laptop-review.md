---
title: HP Laptop review
date: '2020-01-22T19:08:37+00:00'
url: /2020/01/toshiba-laptop-update/
author: matt40k
type: post
description: 'HP Laptop review - 2020'
draft: false
tags: 
  - Blog
  - Review
  - Laptop
  - Hardware
categories:
  - Blog
---

It's the time again that I go in search of a new laptop to replace my current one. Following on from my previous success with the [Toshiba laptop](https://matt40k.uk/2015/05/toshiba-r50-b-12q/) - buying cheap and upgrading the RAM and HDD. I went in search of a cheap laptop. My requirements remained all but the same except for a Full HD screen. 

I once again settled on a Intel CPU. I did spent a large amount of time trying to find a AMD Ryzen based laptop and although they seem good I just couldn't seem to find the right one, most seemed to have a optical drive which nowadays seems like a waste of money and just adds pointless weight to the laptop. 

In the end I settled on the [HP 15s-fq0009na Laptop](https://amzn.to/2O0LDLz).

- Intel Pentium Gold 4417U - 2 cores \ 4 threads
- 4GB DDR4
- 128GB SSD
- 15.6 Inch Full HD
- Windows 10 Home

I also ordered another [4GB DDR4 stick](https://amzn.to/2tQz26Q) - I picked a [Crucial Ballistix Sport LT 4GB DDR4 2400MHz CL16](https://amzn.to/2tQz26Q). I used the [Crucial](http://crucial.com) website to check compatibility. I picked the premium Ballistix because it has a heatsink and the cost was very little extra. I did think about replacing the existing RAM stick and going for 16GB, however I wasn't sure it would be used. 

I already had a spare [Samsung 970 EVO Plus 500 GB NVMe M.2 Internal SSD](https://amzn.to/2RvaI3m) which I planned to replace the 128GB SSD with.

Amazon was also doing £10 off [Office 365](https://amzn.to/2TZ7l6M) when you purchase a laptop, so also picked this up.

And being Amazon, the laptop turned up quickly

{{< figure src="/img/2020/01/hp-laptop-box.jpg" alt="Box - HP Laptop" width="250px" link="/img/2020/01/hp-laptop-box.jpg" >}}

The packaging was pretty light

{{< figure src="/img/2020/01/hp-laptop-unboxed.jpg" alt="Unboxed - HP Laptop" width="250px" link="/img/2020/01/hp-laptop-unboxed.jpg" >}}

The laptop was in a plastic-y cover, I think this was more to protect the laptop from scratches. 

{{< figure src="/img/2020/01/hp-laptop-plastic.jpg" alt="HP Laptop" width="250px" link="/img/2020/01/hp-laptop-plastic.jpg" >}}

Interestly, they also had the abridged declaration of conformity in this plastic packaging. Which seemed, pretty pointless.

A pretty standard cover to protect the screen.

{{< figure src="/img/2020/01/hp-laptop.jpg" alt="HP Laptop" width="250px" link="/img/2020/01/hp-laptop.jpg" >}}

(Facing the screen) On the left you have the power connector - the laptop uses a 45w psu. Then 2x USB 3.0 ports.

{{< figure src="/img/2020/01/hp-laptop-left-ports.jpg" alt="Left hand ports - HP Laptop" width="250px" link="/img/2020/01/hp-laptop-left-ports.jpg" >}}

On the right a full size HDMI port, USB-C port then the power and disc led.

{{< figure src="/img/2020/01/hp-laptop-right-ports.jpg" alt="Right hand ports - HP Laptop" width="250px" link="/img/2020/01/hp-laptop-right-ports.jpg" >}}

I was slightly disappointed when I switched it on for the first time, the battery was completely flat. Luckily HP's claims of fast charge appear to be valid and it was wasn't long before the laptop had a good charge. I did receive an error because of the flat battery, however this resolved itself.

Windows 10 was in S mode. This means only applications from the Windows Store can be installed. Though this is a good idea for most users it does work for developers. Luckily "upgrading" to full Windows is easy, its just an app on the Windows Store. Once this was done, I did receive a pop up about installing McAfee. 

Once again, like I did for the [previous laptop](https:////matt40k.uk/2015/05/toshiba-r50-b-12q/), I ran a simple PowerShell script to gather the default installed software.

{{< gist matt40k 92b2aefd89f0002c0617cb1c5c9404e0 GetDefaultInstallSoftware.ps1>}}

- [Windows App](https://gist.githubusercontent.com/matt40k/92b2aefd89f0002c0617cb1c5c9404e0/raw/WindowsInstalled.txt)
- [Windows Store - All Users](https://gist.githubusercontent.com/matt40k/92b2aefd89f0002c0617cb1c5c9404e0/raw/StoreAllUsers.txt)
- [Windows Store - User](https://gist.githubusercontent.com/matt40k/92b2aefd89f0002c0617cb1c5c9404e0/raw/StoreUser.txt)

The laptop was pretty clean, most of the junkware was caused by Windows. Removing the unwanted software was again a PowerShell script.

{{< gist matt40k 92b2aefd89f0002c0617cb1c5c9404e0 Cleanup.ps1>}}

This just uses cycles through a list, [here is the list I used](https://gist.githubusercontent.com/matt40k/92b2aefd89f0002c0617cb1c5c9404e0/raw/RemoveList.txt).

The other disappointment was the fact it needed rather alot of updates.

At this pointed I shut the laptop down and set about upgrading it. Unfortunately being a cheap laptop, upgrading the SSD and memory was... a bit more difficult. Accessing the motherboard is via the bottom, removing the plastic cover. This is held in place a few screws, most of a which are hidden under a rubber strip. The rubber strip is held on by a double sided sticky tape. I had a little issue with this where the rubber strip came apart of sticky tape.

{{< figure src="/img/2020/01/hp-laptop-bottom.jpg" alt="Bottom - HP Laptop" width="250px" link="/img/2020/01/hp-laptop-bottom.jpg" >}}

The other "fun" part was separating the two parts, I'm not a fan of plastic clips.

In side the laptop was as expected

{{< figure src="/img/2020/01/hp-laptop-inside.jpg" alt="Inside - HP Laptop" width="250px" link="/img/2020/01/hp-laptop-inside.jpg" >}}

Adding the extra memory stick was easy as was swapping the SSD with a NVMe.

{{< figure src="/img/2020/01/hp-laptop-upgrade.jpg" alt="Upgrade - HP Laptop" width="250px" link="/img/2020/01/hp-laptop-upgrade.jpg" >}}

This did however require reinstalling Windows 10. A little disappointing as cloning the SSD didn't appear to work (I think it would have if I had purchased the upgraded version of Acronis).

I have also picked up a [cheap m.2 to USB adapter](https://amzn.to/2RucdyR) so I can use the old SSD as external storage. A bargin at £10.

- **Price:** Good
- **CPU:** OK
- **Memory:** Good
- **Screen:** Excellent
- **Keyboard:** OK - Rather cheap
- **Touchpad:** OK - Again, cheap
- **Battery:** Good
- **Weight:** OK - it's 15" screen
- **Build quality:** OK - it's very plastic-y

Overall, I'm pretty happy.