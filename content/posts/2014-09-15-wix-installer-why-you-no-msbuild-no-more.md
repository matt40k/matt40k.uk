---
title: WIX installer why you no MSBUILD no more?
author: matt40k
type: post
date: 2014-09-15T21:13:36+00:00
url: /2014/09/wix-installer-why-you-no-msbuild-no-more/
categories:
  - MIS systems
  - PowerShell
  - Projects
  - SIMS Bulk Import

---
Last night I chopped up my WIX installer project &#8211; I basically split the actual installer parts into one file &#8211; CoreMsi.wxs, the versions into a variable file &#8211; Version.wxi and the file list into a separate fragment file &#8211; SimsBulkImport.wxs. This worked.

Great I thought, simple PowerShell script to generate the file list, I can even grab the main repository complied bin as a artifact dependency &#8211; got to love TeamCity.

Problem was, it fails to build.

> <i class="mark error_msg  status_err">error CNDL0104: Not a valid source file; detail: &#8216;.&#8217;, hexadecimal value 0x00, is an invalid character. Line 2, position 1.</i>

bit of trial and error later I figured it out. It was my old friend Mr Encoding. After adding

> <span class="n">-Encoding</span> <span class="s2">&#8220;UTF8&#8221; </span>

to the end of the Out-File and it builds again.
