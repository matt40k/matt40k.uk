---
title: Date Format
author: matt
type: post
date: 2017-02-22T23:00:06+00:00
url: /2017/02/date-format/
categories:
  - Business Intelligence
  - Microsoft
  - SSRS

---
I&#8217;ve had a problem recently when it can to formatting a datetime as just date where FormatDateTime didn&#8217;t work

<div class="gist-oembed" data-gist="matt40k/db8cf2285c50571588d05d5aa4d1faae.json?file=gistfile1.txt">
</div>

The fix was to change it to Format.

<div class="gist-oembed" data-gist="matt40k/db8cf2285c50571588d05d5aa4d1faae.json?file=gistfile2.txt">
</div>

Oddly, despite the parameter being a datetime, I found I still had to cast it as a date.

FormatDateTime was introduced in <a href="https://msdn.microsoft.com/en-us/library/a912f2a0(v=vs.90).aspx" target="_blank" rel="nofollow">Vs 2008</a>. I&#8217;m not 100% sure why this didn&#8217;t work.
