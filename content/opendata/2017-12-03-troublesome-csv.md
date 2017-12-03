---
title: Troublesome CSV
author: matt40k
type: post
date: 2017-12-03T10:10:32+00:00
url: /2017/12/troublesome-csv/
categories:
  - data
tags:
  - opendata
  - csv
  - PowerShell
---
Another day, another source of bad data. This time, it was a CSV.

{{< gist matt40k d30ab2858a1c2601606f8b2841ad3440 "file-troublesome-csv" >}}

As you can see, the format changes mid file. This makes importing tricky.
The way I tend to handle importing into SQL is to create staging tables with all the columns defined as varchar, then, once its imported into SQL, then convert it.

The problem occurs when you try to determine the number of columns required. Traditionally, we let the system auto determine how many columns we have, and if we have headers, define the names, unfortunately because the format changes we can't do this otherwise it will ignore the additional columns - assuming the first row doesn't contain all the columns.

To aid in finding out how many columns we need I wrote a simple PowerShell script - after all, it might be do-able for a few small files, but when your file are in Megabytes it gets a little more tricky to do by hand.

{{< gist matt40k 633e76f80cbe45a33fed596b8016ba7f >}}