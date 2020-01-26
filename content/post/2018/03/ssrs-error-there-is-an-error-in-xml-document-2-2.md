---
title: 'SSRS Error - There is an error in XML document (2, 2)'
author: matt40k
type: post
date: '2018-03-20T20:35:22+00:00'
url: /2018/03/ssrs-error-there-is-an-error-in-xml-document-2-2/

description: >-
  SSRS Error when opening solution\project. There is an error in XML document
  (2, 2)
image: /img/image001.png
---
![There is an error in XML document (2, 2)](/img/2018/03/ssiserror.png)

I got this error when opening an SSRS project in Visual Studio. The solution. [Upgrade SSDT](https://docs.microsoft.com/en-us/sql/ssdt/download-sql-server-data-tools-ssdt).

Turns out my colleague had a higher version of SSRS component - if you go, within Visual Studio, Help > About it will give you the version number of Visual Studio then the individual component versions.
