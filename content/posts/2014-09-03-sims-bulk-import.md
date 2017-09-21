---
title: SIMS Bulk Import
author: matt
type: post
date: 2014-09-03T21:58:27+00:00
url: /2014/09/sims-bulk-import/
categories:
  - MIS systems
  - Projects
  - SIMS .net
  - SIMS Bulk Import

---
## Overview

If your in the UK, the chances are your local school is using <a href="http://www.capita-sims.co.uk/" target="_blank" rel="nofollow">SIMS .net</a>. <a href="http://web.archive.org/web/20150909213728/http://www.capita-sims.co.uk/facts-and-figures" target="_blank" rel="nofollow">Just checkout the stats on their site</a>. 22,000 schools taking <span style="color: #57585a;">2,500,000 children&#8217;s attendance, every day. That&#8217;s impressive.</span>

So what is SIMS .net? Well its a MIS system, but what is a MIS system? In the simplest terms its a database that holds the school records, for both students and staff.  So it makes sense that you are going to want to interface with it as it&#8217;s your at your core when it comes to data sources.

Now extracting data is pretty straightforward. Capita have created a custom reporting engine that allows simple report creation that can then be scheduled and produce exports of data. The problem is getting data back into SIMS .net. Take for example identity management, it&#8217;s easy enough to export a list of students, then write a PowerShell script to generate user accounts, but wouldn&#8217;t it be good to get that username added back into your core data source? Or what about adding in new students home email addresses and telephone numbers? Well it isn&#8217;t that straightforward to bulk import. Although Capita provide a API it isn&#8217;t as straightforward and certainly isn&#8217;t as friendly as a RESTful web service and certainly requires a programming background to understand it which rules out many schools being able to use it.

Back in May 2012 I was working on a SIMS support desk doing technical support and one of our customers asked if he could bulk import email addresses back into SIMS .net. This resulted in me asking Capita for documentation regarding the API which they provided, at no cost, along with a few snippets of example code. I then spent the following nights coding away at home to what has become SIMS Bulk Import.

## About

So what are SIMS Bulk Import features

  * It&#8217;s free &#8211; Thank you <a href="https://twitter.com/phil_neal" target="_blank" rel="nofollow">Phil Neal</a> for waiving the licensing costs 🙂
  * It uses the SIMS .net Business Objects (no large Capita charges for corrupting your SIMS .net database!)
  * Imports from CSV, Excel spreadsheets and XML files
  * Matches the file fields with SIMS .net fields

## The future

I&#8217;ve since moved away from SIMS support and I&#8217;ve been trying to find a suitable new home for SIMS Bulk Import. Whether that&#8217;ll be Capita writing a replacement, or someone else taking up the project it isn&#8217;t clear. For now I&#8217;ll continue to support it. But to as part of this I&#8217;ve moved the source over to <a href="https://github.com/SIMSBulkImport" target="_blank" rel="nofollow">GitHub</a>, the releases will still be via <a href="http://simsbulkimport.uk/" target="_blank" rel="nofollow">CodePlex</a>.  I&#8217;ve also created a separate organisation on <a href="https://github.com/SIMSBulkImport" target="_blank" rel="nofollow">GitHub</a>, <a href="https://github.com/SIMSBulkImport" target="_blank" rel="nofollow">SIMSBulkImport</a>, which effectively &#8220;owns&#8221; the code. I fork the code from  <a href="https://github.com/SIMSBulkImport" target="_blank" rel="nofollow">SIMSBulkImport</a> into <a href="https://github.com/matt40k" target="_blank" rel="nofollow">my personal repository</a>, and do a pull request to merge the code back into the main <a href="https://github.com/SIMSBulkImport" target="_blank" rel="nofollow">SIMSBulkImport</a> repository. This will help should the &#8220;owner&#8221; of SIMS Bulk Import change in the future.

I&#8217;ve also created a number of sub-projects &#8211; the SIMS interface library will be moved from <a href="https://unfuddle.com/" target="_blank" rel="nofollow">Unfuddle</a> onto <a href="https://github.com/SIMSBulkImport" target="_blank" rel="nofollow">GitHub</a>, also the installer element will become a separate repository. I&#8217;m looking at setting up <a href="http://www.jetbrains.com/teamcity/" target="_blank" rel="nofollow">TeamCity</a> to automate the build process so building and creating releases is a lot more streamlined and less time consuming. Also a simple web site setup giving easy advise for getting started.

Another change is a web API &#8211; this allows checking for newer versions and secure uploading of log files to the developers (OK, me). <a href="https://www.mythic-beasts.com/" target="_blank" rel="nofollow">Mythic-Beasts</a> have kindly donated a server hosted in Cambridge, UK to host this. This written in <a href="http://www.php.net/" target="_blank" rel="nofollow">PHP</a> using the <a href="http://laravel.com/" target="_blank" rel="nofollow">Laravel</a> framework, I&#8217;ve started writing it based on some of <a href="http://bobbyallen.me/" target="_blank" rel="nofollow">Bobby Allen</a> original code.

Going forward I would like some (official) recommendation from schools and support teams, ideally I&#8217;d like to put together some sort of list or program detailing where you can get support from, for example:

<p style="padding-left: 30px;">
  Your Local SIMS Team supports SIMS Bulk Import!
</p>

<p style="padding-left: 30px;">
  Your Local SIMS Team is a SIMS Bulk Import silver partner!
</p>

It&#8217;s just difficult making a business case to people when your product is free. The main reason I want to do this is I&#8217;m find the odd problem where someone need to remote in, this is difficult without some sort of support agreement and T and Cs &#8211; most of the problems are actual SIMS problems like the SIMS client hasn&#8217;t be installed correctly which their SIMS support team could resolve. I appreciate working in the dark isn&#8217;t easy and you can&#8217;t know about every SIMS third party product, so your going to get a element of from pillar to post. Ideally I need a main backer to act as data controller with regards to the log files, at the moment I&#8217;m investigating if I could get around it by limiting the data it could spit out but that&#8217;s going to limit the usefulness of the logs. It&#8217;ll also been good to get the program <a href="http://en.wikipedia.org/wiki/Digital_signature" target="_blank" rel="nofollow">digitally signed</a>.

If anyone is willing to help out feel free to drop me a email &#8211; matt [at] matt40k [dot] uk
