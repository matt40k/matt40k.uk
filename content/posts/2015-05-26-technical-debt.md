---
title: Technical debt
author: matt40k
type: post
date: 2015-05-26T20:39:05+00:00
url: /2015/05/technical-debt/
categories:
  - Blog
  - MIS systems
  - SIMS .net

---
I was talking to a colleague about one of our suppliers and the progress they were making on a new product they were developing. He was surprised to hear how little progress they appear to have made, they had previously been making huge steps in very little time with very few developers, especially surprising when they have been scaling up the development team over the past few months. I explained they are burning some of the technical debt they have collected whilst they still can. This of course then led to me explaining what I meant by using a common product, which then later prompted this tweet (which irony Capita hit the favourite button on)

<blockquote class="twitter-tweet" data-width="550">
  <p lang="en" dir="ltr">
    Explaining technical debt to schools is extremely easy thanks to <a href="https://twitter.com/CapitaSIMS" target="_blank" rel="nofollow">@CapitaSIMS</a> :p
  </p>
  
  <p>
    &mdash; Matt Smith (@matt40k) <a href="https://twitter.com/matt40k/status/603139277191544832" target="_blank" rel="nofollow">May 26, 2015</a>
  </p>
</blockquote>



For secondary schools who use SIMS .net &#8211; which is most schools in the UK &#8211; this can be simply be explained by Nova-T. Nova-T6 is a perfect example. Technically, it should be written in C#/.NET, however, there is a no business case, so it&#8217;s still a Delphi program. From a end-user perspective if they re-wrote it, they would gain nothing. Personally however, this still doesn&#8217;t mean it should be ruled out. It&#8217;s easier to maintain C# code when you have a small army of C# developers vs only a hand full of aging Delphi coders. Not to mention the advantage of C# over Delphi. The longer Capita leaves it, the more the interest costs them. Just look at some of the technical problems SIMS customers have had, it can all be tracked back to that technical debt. That debt that Capita needs to pay before the interest becomes to high.
