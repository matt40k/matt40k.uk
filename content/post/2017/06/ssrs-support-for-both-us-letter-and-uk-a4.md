---
title: SSRS support for both US Letter and UK A4
author: matt40k
type: post
date: 2017-06-13T21:10:11+00:00
url: /2017/06/ssrs-support-for-both-us-letter-and-uk-a4/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSRS

---
One of those annoying things about the US is they use different paper sizes to us Brits.

US Letter is 215.9 by 279.4 mm (8.5 by 11.0 inches)
  
The UK equivalent, A4, is 210 by 297 mm (8.26 by 11.69 inches)

One of our customers is based in the UK but has remote sales offices in the US, so their SSRS report are set to A4 and when they printed them in the US offices, the footer is cut off. The fix? Simple. Change the height to 279.4 mm.

Assuming you have a footer, it will now hover 17.6mm higher up the A4 page, which hopefully won&#8217;t be too terrible. It will now be American proof.
