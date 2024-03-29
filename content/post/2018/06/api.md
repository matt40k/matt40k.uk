---
title: API
date: '2018-06-08T23:12:41+00:00'
url: /2018/06/api/
author: matt40k
type: post
description: 'WHOIS API'
---
Towards the end of last year I was writing .net core AWS Lambda. I was super impressed with how .net core (and even PowerShell) works on Linux.
I would have to say C# is by far my favorite programming language, the only exception might be T-SQL and the idea of being about to write code and get it to run on Linux is amazing. Mainly because Linux servers are, to be blunt, cheaper.

What I've done is:

Setup a virtual server on <a href="//www.civo.com" target="_blank" rel="nofollow">Civo</a>, which is running Ubuntu.
Created a c# dotnet core web api project
Uses VSTS for version control, CI (automated builds) and CD (automated deployment).
Used NGinx as a proxy
LetsEncrypt for (free) an SSL certificate.

Currently I have 2 APIs, both only work for .UK domains and are under the https://seahorse.matt40k.uk/api namespace. They both return Json.

### Domains
This uses the Nominet WHOIS2 service - its basically the standard WHOIS service only I can proxy - basically I pass the end-user IP rather then mine so I don't eat into my own quote. The other thing I've done it to return the results as Json.
<a href="//seahorse.matt40k.uk/api/domains" target="_blank">https://seahorse.matt40k.uk/api/domains</a>

For example:
<a href="//seahorse.matt40k.uk/api/domains/matt40k.uk" target="_blank">https://seahorse.matt40k.uk/api/domains/matt40k.uk</a>

### Websites
This basically queries the website for basic information. Url, domain name, if it has HTTPS, the generator tool used to create the webpages (using the Meta tag) - for example WordPress, etc, etc, etc
<a href="//seahorse.matt40k.uk/api/websites" target="_blank">https://seahorse.matt40k.uk/api/websites</a>

For example:
<a href="//seahorse.matt40k.uk/api/websites/matt40k.uk" target="_blank">https://seahorse.matt40k.uk/api/websites/matt40k.uk</a>

At some point I'm going to split it out into it's own domain and look at setting up CloudFlare, however I haven't quite decided how exactly to expand the project. I was working on updating the <a href="https://github.com/matt40k/SchoolsWebsites-England">data on schools websites</a>, however because of GDPR, Nominet has stopped publishing the owner of websites- which kinda put a stopper on my idea of pointing out how bad Nominet are when it comes to schools - hint, I found a large number of incorrectly registered school domains. For example, a number were registered as UK Individual. A schools domain should never be registered as to an individual. 

If you find the APIs useful, let me know, or if there is anything that is broken or missing - drop me a <a href="//twitter.com/matt40k">tweet</a> or email.


