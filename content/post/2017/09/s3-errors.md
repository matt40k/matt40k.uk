---
title: AWS S3 errors
author: matt40k
type: post
date: 2017-09-30T22:26:50+00:00
url: /2017/09/s3-errors/
categories:
  - Blog
tags:
  - AWS

---

One of the annoying things about AWS S3 is the error messages. Below is an error, see if you can figure out what it's saying.

{{< gist matt40k 697ad2e95e6f151b19d6a13e04acef88 >}}

I'll give you a hint. We've connected and authenticated.

Here is another hint, we can read from that bucket.

Give up? It's permissions. Incorrect AWS keys returns a helpful message, so does invalid bucket, as does no access to read bucket
