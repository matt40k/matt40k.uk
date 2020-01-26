---
title: Incorrect x-axis dates
author: matt40k
type: post
date: 2016-07-27T09:18:04+00:00
url: /2016/07/incorrect-x-axis-dates/
categories:
  - Business Intelligence
  - Microsoft
  - Power BI

---
So yesterday I was playing with <a href="http://powerbi.com/" target="_blank" rel="nofollow">PowerBI</a> and I hit a problem.

<a href="//matt40k.uk/img/2016/07/XAxis-Error.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-802" src="//matt40k.uk/img/2016/07/XAxis-Error.png" alt="XAxis-Error" width="332" height="335" srcset="//matt40k.uk/img/2016/07/XAxis-Error.png 332w, //matt40k.uk/img/2016/07/XAxis-Error-150x150.png 150w, //matt40k.uk/img/2016/07/XAxis-Error-297x300.png 297w" sizes="(max-width: 332px) 100vw, 332px" /></a>

As you can see, the x-axis is wrong. For some reason it wasn&#8217;t creating the correct range.

After a little while I thought I&#8217;d try out Microsoft&#8217;s feedback option &#8211; the smiley faces &#8211; in the top menu you have a smiley face. Click it, then you can send feedback.

<a href="//matt40k.uk/img/2016/07/Feedback.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-805" src="//matt40k.uk/img/2016/07/Feedback.png" alt="Feedback" width="346" height="228" srcset="//matt40k.uk/img/2016/07/Feedback.png 346w, //matt40k.uk/img/2016/07/Feedback-300x198.png 300w" sizes="(max-width: 346px) 100vw, 346px" /></a>

Sure enough after a little while, Justin Schneider from the <a href="http://powerbi.com" target="_blank" rel="nofollow">Power BI </a>team replied asking a few more questions &#8211; basically asking me to check the data was correct, which was in this case and even offered a solution.

The problem was the auto options for the X-Axis range was wrong and he recommended setting it manually.

To this is simple, click on the visual with the faulty X-Axis, then on the left hand menu, click the paint brush, then expand the X-Axis and manually enter the start and end

<a href="//matt40k.uk/img/2016/07/XAxis-fix.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-803" src="//matt40k.uk/img/2016/07/XAxis-fix.png" alt="XAxis-fix" width="216" height="418" srcset="//matt40k.uk/img/2016/07/XAxis-fix.png 216w, //matt40k.uk/img/2016/07/XAxis-fix-155x300.png 155w" sizes="(max-width: 216px) 100vw, 216px" /></a>

And voilà its fixed!

<a href="//matt40k.uk/img/2016/07/XAxis-fixed.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-804" src="//matt40k.uk/img/2016/07/XAxis-fixed.png" alt="XAxis-fixed" width="342" height="335" srcset="//matt40k.uk/img/2016/07/XAxis-fixed.png 342w, //matt40k.uk/img/2016/07/XAxis-fixed-300x294.png 300w" sizes="(max-width: 342px) 100vw, 342px" /></a>
