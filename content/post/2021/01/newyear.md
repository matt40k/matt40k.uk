---
title: New Year tech clean up
author: matt40k
type: post
date: 2021-01-17T00:12:00+00:00
url: /2021/01/new-year/
type: post
description: 'New Year tech clean up'
draft: false
categories:
  - Blog
tags:
  - Cleanup
  - PowerShell
  - Git

---

Well as another weird year begins I've managed to break some time off to do a bit of housekeeping. I've remove some old forks, added licenses, tags etc.

I've also been renaming the [default branch to main](https://www.hanselman.com/blog/easily-rename-your-git-default-branch-from-master-to-main). 

```
git branch -m master main
git fetch origin
git branch -u origin/main main
```
