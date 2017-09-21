---
title: Caching woes
author: matt
type: post
date: 2017-02-24T13:44:11+00:00
url: /2017/02/caching-woes/
categories:
  - Blog

---
Caching always seems to cause problems, still, we can&#8217;t have it all. Today&#8217;s caching problem was to do with <a href="http://www.red-gate.com/" target="_blank" rel="nofollow">Redgate</a> <a href="http://www.red-gate.com/products/sql-development/sql-prompt/" target="_blank" rel="nofollow">SQL Prompt</a>, a really amazing plugin that helps you write better SQL code. The problem with it is the cache of database object metadata was out-of-date. I had updated a table so when I typed select \* then press TAB to expand the \* into a list of columns, I got the old names. Luckily the fix is easy. Refresh suggestions.

<a href="//matt40k.uk/img/2017/02/sqlPromptRefresh.png" target="_blank" rel="nofollow"><img class="alignnone size-full wp-image-2410" src="//matt40k.uk/img/2017/02/sqlPromptRefresh.png" alt="" width="538" height="140" srcset="https://publish.matt40k.uk/wp-content/uploads/2017/02/sqlPromptRefresh.png 538w, https://publish.matt40k.uk/wp-content/uploads/2017/02/sqlPromptRefresh-300x78.png 300w" sizes="(max-width: 538px) 100vw, 538px" /></a>

As the screenshot shows, its either **SQL Prompt** > **Refresh suggestions** or just **Ctrl + Shift +D.**
