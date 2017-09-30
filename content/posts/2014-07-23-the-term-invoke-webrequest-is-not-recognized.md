---
title: The term ‘Invoke-WebRequest’ is not recognized
author: matt
type: post
date: 2014-07-23T22:02:05+00:00
url: /2014/07/the-term-invoke-webrequest-is-not-recognized/
categories:
  - PowerShell
tags:
  - PowerShell

---
I&#8217;ve currently been working on a PowerShell script to build a virtual server using <a href="https://www.digitalocean.com/" target="_blank" rel="nofollow">DigitalOcean</a> excellent <a href="https://developers.digitalocean.com/" target="_blank" rel="nofollow">RESTful API</a>. So far this has gone extremely well and I have been impressed with both PowerShell and <a href="https://www.digitalocean.com/" target="_blank" rel="nofollow">DigitalOcean&#8217;s</a> <a href="https://developers.digitalocean.com/" target="_blank" rel="nofollow">API</a>. Today however I tried running on another machine (an important part of development) only to find it doesn&#8217;t work. The first error that appears is:

> The term &#8216;Invoke-WebRequest&#8217; is not recognized as the name of a cmdlet, function, script file, or operable progr
  
> am. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
  
> At line:1 char:18
  
> + Invoke-WebRequest <<<<
  
> + CategoryInfo          : ObjectNotFound: (Invoke-WebRequest:String) [], CommandNotFoundException
  
> + FullyQualifiedErrorId : CommandNotFoundException

In simple terms it&#8217;s saying it can&#8217;t find the <span style="font-style: italic;">&#8216;Invoke-WebRequest&#8217; cmdlet. This should be a built-in cmdlet in PowerShell, so off I went to TechNet to find the details of the cmdlet &#8211; </span>

<a href="http://technet.microsoft.com/en-us/library/hh849901.aspx" target="_blank" rel="nofollow">http://technet.microsoft.com/en-us/library/hh849901.aspx</a>

The key bit of information was this line:

> <span style="color: #2a2a2a;">This cmdlet was introduced in Windows PowerShell 3.0.</span>

The other way is at the top of such documents on TechNet it defaults to the most recent version of the, in this case, cmdlet and next to it gives you the option select a older version, clicking it reveals previous versions and does indeed confirm the above statement that it was not present in any version of PowerShell prior to 3.0.<figure id="attachment_155" style="width: 654px" class="wp-caption aligncenter">

<a href="//matt40k.uk/img/2014/08/invoke-webrequest1.png" target="_blank" rel="nofollow"><img class="wp-image-155 size-full" src="//matt40k.uk/img/2014/07/invoke-webrequest.png" alt="TechNet" width="654" height="394" /></a><figcaption class="wp-caption-text">TechNet</figcaption></figure> 

Next question, is PowerShell 4.0 installed? Well for Windows 8.1 and Windows Server 2012 R2 it&#8217;s built-in, you can check by running (in PowerShell)

>     $PSVersionTable.PSVersion

sure enough, the other machine (which is Windows 7 Enterprise x64) returns

> Major  Minor  Build  Revision
  
> &#8212;&#8211;  &#8212;&#8211;  &#8212;&#8211;  &#8212;&#8212;&#8211;
  
> 2      0      -1     -1

For help installing PowerShell 4.0 go to: <a href="http://social.technet.microsoft.com/wiki/contents/articles/21016.how-to-install-windows-powershell-4-0.aspx" target="_blank" rel="nofollow">http://social.technet.microsoft.com/wiki/contents/articles/21016.how-to-install-windows-powershell-4-0.aspx</a>

&nbsp;

&nbsp;

&nbsp;
