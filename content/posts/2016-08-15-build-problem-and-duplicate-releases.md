---
title: Build problem and duplicate releases
author: matt
type: post
date: 2016-08-15T07:14:03+00:00
url: /2016/08/build-problem-and-duplicate-releases/
categories:
  - Blog
  - PowerShell
  - Projects
  - SIMS Bulk Import

---
Yesterday I went to investigate a problem someone had reported only to discover a butt load of releases

<a href="//matt40k.uk/img/2016/08/img_4294.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-822" src="//matt40k.uk/img/2016/08/img_4294.png" alt="" width="1334" height="750" srcset="//matt40k.uk/img/2016/08/img_4294.png 1334w, //matt40k.uk/img/2016/08/img_4294-300x169.png 300w, //matt40k.uk/img/2016/08/img_4294-768x432.png 768w, //matt40k.uk/img/2016/08/img_4294-1024x576.png 1024w, //matt40k.uk/img/2016/08/img_4294-1200x675.png 1200w" sizes="(max-width: 1334px) 100vw, 1334px" /></a>
  
As you can see, I have more releases then commits. A build was triggered by a commit, but this doesn&#8217;t explain why.

I tried switching it up so it only builds when you put [build] in the commit message &#8211; which resulted in having to commit the yaml file as the feature isn&#8217;t available via the web interface, it does make sense to have this under version control. However it continued to loop.

Looking at the build history revealed it was looping, per commit

<a href="//matt40k.uk/img/2016/08/img_4296.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-824" src="//matt40k.uk/img/2016/08/img_4296.png" alt="" width="1334" height="750" srcset="//matt40k.uk/img/2016/08/img_4296.png 1334w, //matt40k.uk/img/2016/08/img_4296-300x169.png 300w, //matt40k.uk/img/2016/08/img_4296-768x432.png 768w, //matt40k.uk/img/2016/08/img_4296-1024x576.png 1024w, //matt40k.uk/img/2016/08/img_4296-1200x675.png 1200w" sizes="(max-width: 1334px) 100vw, 1334px" /></a>

An email off to support resulted in speedy response.

> Add &#8220;skip_tags: true&#8221; to your appveyor.yml.
  
> -Feodor Fitsner, AppVeyor

Bingo. It was looping because I create a GitHub release for each build and tag the release. Which was then causing a build, which created a release that then got tagged, which created a release&#8230;

I&#8217;m grateful I&#8217;m not paying per build! Hopefully this will serve as a warning for others.

I&#8217;ve started to remove the releases but I&#8217;ve hit the API limit last night. Hopefully I&#8217;ll clean up my PowerShell script to deal with it, failing that I may have to rely on the kindnesses of GitHub human.

> &#8220;I have always depended on the kindness of strangers.&#8221;
> 
> &#8211; Blanche DuBois

### Update

I&#8217;ve managed to remove the duff tags as well and <a href="https://simsbulkimport.uk/" target="_blank" rel="nofollow">SIMS Bulk Import</a> is down to two releases on <a href="https://github.com/SIMSBulkImport/SIMSBulkImport" target="_blank" rel="nofollow">GitHub</a>. I&#8217;ve been slightly heavy handed when it came to deleting. Thankfully all the duff releases where pre-release so the problem wasn&#8217;t as bad is it could have been.

Below is the PowerShell script I quickly knocked together, the tags I did over lunch at work, thus the proxy bit &#8211; note that isn&#8217;t our actual proxy address 😉

<div class="gist-oembed" data-gist="matt40k/8ca025a7b260ce59a0d9a9a461479ac8.json">
</div>
