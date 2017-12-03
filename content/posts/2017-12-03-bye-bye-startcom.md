---
title: Bye bye Startcom
author: matt40k
type: post
date: 2017-12-03T12:25:32+00:00
url: /2017/12/bye-bye-startcom/
categories:
  - security
tags:
  - ssl
  - security
  - https
---
In the old days, you would have to throw money at a trusted Certificate Authority (CA) who would sell you a SSL certificate. The alternative was to self-sign or use someone like <a href="http://www.cacert.org/">cacert</a>, the problem is out-of-the-box, no browser\OS supports this so you get a security warning, which isn't something you want when your trying to be secure.

StartCom, was a trusted CA who issued free SSL certificates. Microsoft Internet Explorer, Google Chrome, Mozilla Firefox all trusted StartCom which means you could get a free SSL certificate without the warnings. The StartCom reasoning behind giving away free SSL certificates was the freemium model. It doesn't cost a lot to issue a SSL certificate, it costs to verify. For a basic SSL certificate you just need to verify the domain, which is really an automated process, so the cost is extremely low, the more expensive verifications which require checking individual ID or organisations, that's where you make the money.

> # StartCom model was give the certificates away for free and charge for verification.

Then <a href="https://cloudflare.com">CloudFlare</a> offered free SSL certificates. Then <a href="https://letsencrypt.org">Let's Encrypt</a> appeared.

StartCom, Israel based company, <a href="https://docs.google.com/document/d/1C6BlmbeQfn4a9zydVi2UvjBGv6szuSB4sMYUcVrR8vQ/">was sold on 1st November 2015 to Qihoo 360</a>, China based - who own WoSign. Later in December StartCom switched over to WoSign infrastructure. I personally see this as a move of getting out before you go out of business.

It wasn't helped by the <a href="https://arstechnica.com/information-technology/2017/07/google-drops-the-boom-on-wosign-startcom-certs-for-good/">fact WoSign (and thus StartCom) got revoked by the major browsers/OS</a>.

So yesterdays email annocument came as no suprise:

> Dear customer,
> 
> As you are surely aware, the browser makers distrusted StartCom around a year ago and therefore all the end entity certificates newly issued by StartCom are not trusted by default in browsers.
>
> The browsers imposed some conditions in order for the certificates to be re-accepted. While StartCom believes that these conditions have been met, it appears there are still certain difficulties forthcoming. Considering this situation, the owners of StartCom have decided to terminate the company as a Certification Authority as mentioned in Startcom´s website.
>
> StartCom will stop issuing new certificates starting from January 1st, 2018 and will provide only CRL >and OCSP services for two more years.
>
> StartCom would like to thank you for your support during this difficult time.
>
> StartCom is contacting some other CAs to provide you with the certificates needed. In case you don't want us to provide you an alternative, please, contact us at certmaster@startcomca.com
>
>Please let us know if you need any further assistance with the transition process. We deeply apologize for any inconveniences that this may cause.
>
> Best regards,
>
> StartCom Certification Authority
