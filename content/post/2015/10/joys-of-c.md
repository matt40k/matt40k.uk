---
title: 'Joys of C#'
author: matt40k
type: post
date: 2015-10-10T20:29:36+00:00
url: /2015/10/joys-of-c/
categories:
  - Blog
  - SQL Server
  - SSIS
tags:
  - C Sharp

---
On Friday, I had a problem raised, they want to change one of the automatic rename jobs which renames and moves export files to a shared drive. Lucky, I had created a SSIS package, which was a SQL Job that runs on a scheduled every 15 mins, which uses a script task to perform the logic. Because we also used <a href="http://www.octopusdeploy.com/" target="_blank" rel="nofollow">OctopusDeploy</a>, this really was going to be a 5 min change.

The summary of the requirement change was this, currently we export files to:

`\Client Name\Month Number-Month Name\`

so, for example, for the April export for Client A it would be:

`\Client A\04-April\`

What they wanted to change it was:

<span style="font-family: Courier New;">\Client Name\Fiscal Month Number-Month Name\</span>

so, for example, for the April export for Client A would become:

<span style="font-family: Courier New;">\Client A\01-April\</span>

Again, as this was a script task, it was just a question of adding a new method and adding it in. For reference, here is the method I quickly bosh together:

<div class="gist-oembed" data-gist="matt40k/df77c8fb8b3a2c79c4c8.json">
</div>

Thanks to some clever upfront work &#8211; with both the script task and <a href="http://www.OctopusDeploy.com" target="_blank" rel="nofollow">OctopusDeploy</a>, this change took 5 mins.
