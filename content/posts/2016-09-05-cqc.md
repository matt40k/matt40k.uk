---
title: Care Quality Commission (CQC)
author: matt40k
type: post
date: 2016-09-05T22:36:05+00:00
url: /2016/09/cqc/
categories:
  - Blog
  - Business Intelligence
  - Microsoft
tags:
  - API
  - OpenData

---
Today one of our older SSIS packages failed which loads data into our warehouse, it turns out one of the fields had been expanded as the business had started to use a different standard for one of the codes. Despite not being told about this, it causing it fail and generate extra work on an already busy Monday it was actually a really good thing.

Firstly, once we identified the problem (and fixed it), our main business contact was aware of it, was able to explain why it was happening. The change in a nutshell was to change from using a internal-only generated code to using the national standard &#8211; <a href="https://www.cqc.org.uk/" target="_blank" rel="nofollow">Care Quality Commission (CQC)</a> ID.

Part of the next step of the change will be to bring on-board the <a href="https://www.cqc.org.uk/" target="_blank" rel="nofollow">CQC </a>data which include the Care Home ratings. This will create a unified view of placements and ensuring no-one is in Care Home rated as inadequate.

<a href="https://www.cqc.org.uk/" target="_blank" rel="nofollow">CQC</a> provides the data either by <a href="https://www.cqc.org.uk/content/how-get-and-re-use-cqc-information-and-data#directory" target="_blank" rel="nofollow">CSV\Spreadsheet</a> or an <a href="https://anypoint.mulesoft.com/apiplatform/openanswers-co-uk/#/portals/organizations/262a9203-e08f-4d1d-809d-2fc07032e8e8/apis/10878/versions/11228" target="_blank" rel="nofollow">API</a>.

Initial I thought importing the data dumps would be a good way forward, however after playing with the API, it looks like this might be a much better way forward. Below is a PowerShell script I knocked up to test the API out.

<div class="gist-oembed" data-gist="matt40k/84c133de01f29191e65852acbfa89c22/498f9a9cec327070b8e21a50020371e90a2c4b5e.json?file=cqc.ps1">
</div>

&nbsp;

It&#8217;s really good to see that APIs are being generated, its just a shame these aren&#8217;t being embedded directly into the software. Still, its a long journey, but at least its started.
