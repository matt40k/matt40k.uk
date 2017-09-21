---
title: Collation
author: matt
type: post
date: 2015-11-24T13:31:59+00:00
url: /2015/11/collation/
categories:
  - Blog

---
I don&#8217;t know a lot about Collation &#8211; I know how to set it in SQL Server, I know it&#8217;s important, it know chaos can ensure if your not careful for example if you set it to CS rather then CI*, so my general tack is to leave it as default and hope it leaves me alone.

Today however, this happened

<a href="//matt40k.uk/img/2015/11/collation.png" target="_blank" rel="nofollow"><img class="alignnone wp-image-501 size-full" src="//matt40k.uk/img/2015/11/collation.png" alt="collation" width="948" height="67" srcset="//matt40k.uk/img/2015/11/collation.png 948w, //matt40k.uk/img/2015/11/collation-300x21.png 300w, //matt40k.uk/img/2015/11/collation-648x46.png 648w, //matt40k.uk/img/2015/11/collation-583x41.png 583w" sizes="(max-width: 948px) 100vw, 948px" /></a>

Turns out in the VS SSDT package, I have forgotten to set one of the databases collation in project settings to Latin1\_General\_CI_AS to match the default on SQL Server (rather then the VS SSDT default)

* Glossary
  
CI &#8211; case insensitive &#8211; recommended
  
CS &#8211; case sensitive &#8211; avoid
