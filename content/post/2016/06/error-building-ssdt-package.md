---
title: Error building SSDT package
author: matt40k
type: post
date: 2016-06-10T20:05:15+00:00
url: /2016/06/error-building-ssdt-package/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSIS

---
Today my colleague had a problem opening our BI solution, the solution had multiple projects, including 3 SSDT projects. Although the project builds correctly on both my machine, the build machine and another colleague machine it refused to build stating that the reference to the object in another project was invalid.

After thinking for a few moments, I remembered I had seem this before. The problem was a bug in SSDT. The solution was to click on **Tools > Extensions and Updates**, then click **Updates** from the left-menu on the window that appears.
