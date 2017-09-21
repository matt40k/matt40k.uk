---
title: Where has SIMS Bulk Import gone?
author: matt
type: post
date: 2016-10-06T10:36:10+00:00
url: /2016/10/where-has-sims-bulk-import-gone/
categories:
  - Blog
  - Projects
  - SIMS Bulk Import

---
> Cut-down version, I&#8217;m not working with SIMS anymore and I can&#8217;t pass on my work without them getting a large bill from Capita for using the business objects.

Years and years ago I was working on a SIMS help desk at a Local Authority (LA). I had a school log a call asking about importing email addresses. Like many schools this school had just purchased a messaging service that allows sending emails and texts, the problem was they needed them in SIMS .net, as you can imagine the idea of manually retyping 1,000+ email addresses was rather daunting. So, after putting a call into Capita Partner Team asking for the API documentation I spend the evening building a simple import process. The next day I phoned the school to give them the good news and we imported their email addresses. A few days later a few more schools asked the same question and I decided to continue spending my evenings expanding (it imports email, telephone and User defined fields from XML, CSV and Excel spreadsheets) and refining the tool. I&#8217;ve always developed in my own time, I&#8217;ve never claimed overtime etc and I&#8217;ve never charged a penny for using it.

SIMS Bulk Import uses the SIMS .net business objects (API), its uses the the SIMS .net DLLs. Its the exact same .NET libraries that the SIMS .net library uses.

At the time we were in a partnership with BT, who had a procedure for raising new business ideas. The process involved working out what type of change it was &#8211; in this case it was a efficiency saving. To put it simply this means you can&#8217;t charge more then what you can save, in this case labour.

Capita charge the school. <a href="//matt40k.uk/img/2016/10/capita_sims_-_partner_management_document_-_apr16.pdf" target="_blank" rel="nofollow">Then they charge the partner for write access</a>, which the partner then charges on the school so the **schools end up paying twice **for support on one thing.

When you take into account the Capita charge, the handling of money costs (invoicing, collecting and chasing etc), the helpdesk costs, the fact people expect a certain standard, ie you&#8217;re going to have to invest alot more in terms of development &#8211; including documentation. It just doesn&#8217;t make sense. It&#8217;s actually more cost effective to hire a temp to manually key in all those details!! Nuts!!

So at this point I basically decide I&#8217;ll give it away. I really didn&#8217;t want to see my hard work go to waste. I basically managed to wangle it into the public domain without finding a massive Capita bill land on my desk!! Its been in a wild for many, many years (with Capita knowledge) with a grand total of ZERO corrupt SIMS databases. I find this quite an achievement. Don&#8217;t get me wrong, SIMS Bulk Import has failed a number of times, but it&#8217;s never left your SIMS system in a worse state (unless you&#8217;ve done something stupid like successfully imported the same email address to every pupil in SIMS!)

A few years later I switched teams and stopped working with SIMS .net. SIMS Bulk Import has been stable for a while and I&#8217;ve had a few commits from individuals. I&#8217;m now at the stage where I&#8217;m going to leave the LA and go work somewhere else and its unlikely to have a SIMS .net license let alone API access. I needed to find a new owner for SIMS Bulk Import. Anyone who&#8217;s talked to me would have described SIMS Bulk Import as the poor man&#8217;s <a href="http://www.salamandersoft.co.uk/active-directory/" target="_blank" rel="nofollow">Salamander Active Directory</a>, it is simply put the next logical step if you work out how you&#8217;d improve SIMS Bulk Import, its what I would have done to make SIMS Bulk Import into a commercial product. Luckily Richard agreed to take it on and even help me recover some of the costs of SIMS Bulk Import. Before you shoot off to <a href="http://www.salamandersoft.co.uk/" target="_blank" rel="nofollow">SalamanderSoft</a> to download it, let me save you the disappointment. Capita has said they would charge them a license fee for each school using it, ie it wouldn&#8217;t be free. At this point I guess you can see where I&#8217;m going with this? SIMS Bulk Import isn&#8217;t worth paying for and Richard already has the expanded version (that **IS** worth paying for).

So in short, your options are:

  1. Except you can&#8217;t bulk import anymore and get typing or copy and pasting \ hire a temp
  2. Look at automating your processes and buy <a href="http://www.salamandersoft.co.uk/active-directory/" target="_blank" rel="nofollow">Salamander Active Directory</a>
  3. Wait for Capita to come out with their own product &#8211; I suspect they will and charge. They do a limited SQL script that injects the records directly into the database, ironically bypassing the business objects (but hey, they support it so its all good right?)
  4. Switch MIS who doesn&#8217;t charge for partner access \ gives you bulk import routines (<a href="https://eduwarenetwork.com/" target="_blank" rel="nofollow">Eduware Network</a> has a list of MIS suppliers)

Option 5 is carry on using it. I&#8217;m sure even with me saying, no, don&#8217;t do that (and I&#8217;m sure Capita will agree) &#8211; someone will. So a few comments.

Make sure you have the latest (or should that be last) version &#8211; its **2.5.0**

It should be digital signed, think of it as SSL for your applications. If you right-click on **SIMSBulkImport.exe** or the .msi installer you should see an extra tab &#8211; **Digital Signature** and you should see its signed by me &#8211; **Open Source Developer, Matt40k**. If your copy doesn&#8217;t have the signature its possible code has been injected and it is unsafe.

<a href="//matt40k.uk/img/2016/10/digitalSignature.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-873" src="//matt40k.uk/img/2016/10/digitalSignature.png" alt="digitalsignature" width="396" height="280" srcset="https://publish.matt40k.uk/wp-content/uploads/2016/10/digitalSignature.png 396w, https://publish.matt40k.uk/wp-content/uploads/2016/10/digitalSignature-300x212.png 300w" sizes="(max-width: 396px) 100vw, 396px" /></a>

You should be OK as it uses whatever version of SIMS API you have installed, so it&#8217;ll just break one day and by break I mean it won&#8217;t let you login or will just give you all import failed (if it does fail in terms of SIMS database corrupt then some thing terrible has happened with Capita API, but I digress).

A few people have forked my code, for whatever reasons, I would just point out that the most up-to-date fork is **80** commits behind mine. That&#8217;s a fair amount of work that missing from those forks.

Anyway, hopefully you&#8217;ve found it useful whilst it last.
