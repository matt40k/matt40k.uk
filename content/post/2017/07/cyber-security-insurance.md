---
title: Cyber Security Insurance
author: matt40k
type: post
date: 2017-07-05T21:17:22+00:00
url: /2017/07/cyber-security-insurance/
categories:
  - Blog

---
I&#8217;ve been thinking lately about how the web industry needs to change in order to improve. Cyber attacks appears to be on the rise and alot of the time they appear to be caused by someone <a href="https://www.troyhunt.com/the-5-stages-of-data-breach-grief/" target="_blank" rel="nofollow">doing something silly</a>. Perhaps this is because everyone is a web developer, it certainly isn&#8217;t down to <a href="https://www.pluralsight.com/authors/troy-hunt" target="_blank" rel="nofollow">lack of available resources</a> on the matter.

Thinking positively about cyber security, the card companies banded together to form PCI-DSS &#8211; Payment <span class="inGlossary">Card</span> Industry Data Security Standard, with the goal to help businesses process <span class="inGlossary">card</span> payments securely and reduce <span class="inGlossary">card</span> fraud. Yes, it isn&#8217;t perfect, but it is a real benefit. Ideally this needs to be pushed beyond just card payments, it needs to be embedded (at least in the UK) with the <a href="https://ico.org.uk/" target="_blank" rel="nofollow">Information Commissioner Office (ICO)</a>. It needs to be combined with software vendors like <a href="https://www.microsoft.com/" target="_blank" rel="nofollow">Microsoft</a>, <a href="https://www.canonical.com/" target="_blank" rel="nofollow">Canonical (Ubuntu)</a>, <a href="https://www.redhat.com/" target="_blank" rel="nofollow">Redhat</a> as well framework developers like <a href="https://laravel.com/" target="_blank" rel="nofollow">Laravel</a>, <a href="https://revel.github.io/" target="_blank" rel="nofollow">Revel</a>, <a href="https://www.emberjs.com/" target="_blank" rel="nofollow">Ember.js</a> and the end developers.

Security testing shouldn&#8217;t be a tick box at the end of the process. It should be embedded throughout the process and should be more like insurance with the more effort you put in, the less you pay.

Think about your house insurance. If you live in a dangerous area, the more you pay. If you use a &#8220;dangerous&#8221; software stack (like no framework), the more you pay. If you fit a security alarm, the less you pay. If you pen test your software, use 2FA, whatever, you pay less.

The way I would see it being pay for is at the point of sale to the end customer, the final cost would take into account the risk aspect in terms of the technologies used &#8211; are they mature, track record of vulnerabilities, etc. But also how long to fix &#8211; ie if (any) one of the upstream developers release a security fix, how long will it take before it is applied. Most companies don&#8217;t upgrade for fear of IT problems. Which ultimately results in more problems just later down the line. Forcing frequent updates reduces the risk. Testing is simpler as changes are smaller. Testing happens more frequently so staff are better trained.

This would ultimately give the end customers protection from cyber attack caused from a sloppy mistake, even by a third party. Which is what they are crying out off.

The insurance company would be required to have a solid security background in order to make this work &#8211; so much so that it might be easier for a large security company to become a insurance company. They would of course require some massive legal and (ideally) government backing to ensure they can enforce the requirements or at least some pretty major end customers who demand software vendors have the required insurance.

The final point is that the insurance company would need to proactively payout. By this I mean they need to pay bug bounties. After all, it&#8217;s like flood defences

> _Flood defences_ on average prevent £8 in future _flood_ damages per £1 spent

Paying out for detailed vulnerability is cheaper then paying out damages, fines, repair costs (overtime, contractors, third parties) as well as loss of earnings and not forgetting rep.
