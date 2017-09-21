---
title: Dangers of distribution lists
author: matt
type: post
date: 2016-11-15T23:23:15+00:00
url: /2016/11/dangers-of-distribution-lists/
categories:
  - Business Intelligence
  - Power BI
tags:
  - Active Directory
  - PowerQuery

---
Distribution list are amazing things, they allow us to send mail to our team without having to remember who exactly is in our team, this is especial true in this modern age where we are part of many different teams, sometimes without even realising. These lists can contain hundreds or even thousands of members and the latest NHS IT bug has left IT departments maybe wanting to double-check their distribution lists &#8211; hopefully before the security team comes a knocking.

<blockquote class="twitter-tweet" data-width="550">
  <p lang="en" dir="ltr">
    NHS 850k reply-all email fail: State health service blames Accenture for config cockup < by me <a href="https://t.co/TZ1AOqsdKC" target="_blank" rel="nofollow">https://t.co/TZ1AOqsdKC</a>
  </p>
  
  <p>
    &mdash; Gareth Corfield (@GazTheJourno) <a href="https://twitter.com/GazTheJourno/status/798494144062689280" target="_blank" rel="nofollow">November 15, 2016</a>
  </p>
</blockquote>



Luckily, this is really easy in Excel 2016. Built into Excel 2016 is PowerQuery and one of the out-of-box connectors is Active Directory. With a bit of PowerQuery magic, you can easily pull this data out.

So we want to:

  * Connect to our Active Directory
  * List out all our Groups
  * Filter to email-able Groups
  * Include 
      * the group owner
      * the members
      * any security \ restrictions on who can email the list

Note: If your unluckily enough to be running an old version of Excel, it possible to do the same thing in <a href="https://powerbi.microsoft.com/en-us/" target="_blank" rel="nofollow">Power BI Desktop</a>, which is a <a href="https://powerbi.microsoft.com/en-us/" target="_blank" rel="nofollow">free download</a>.

Below is the M code to do this:

<div class="gist-oembed" data-gist="matt40k/ad9aa51201e73f112e790655fb90049a.json">
</div>

<a href="https://matt40k.uk/2016/06/getting-a-list-of-ad-groups-and-their-members-using-powerquery/" target="_blank" rel="nofollow">For more help on how to enter the M code into Excel see my previous post.</a>

UPDATE: Please note that this only works with Active Directory and doesn&#8217;t work with Azure Active Directory. Others have said this is possible via odata or such however I haven&#8217;t tried&#8230; yet.
