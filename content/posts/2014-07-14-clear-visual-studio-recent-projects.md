---
title: Clear Visual Studio recent projects
author: matt
type: post
date: 2014-07-14T11:55:43+00:00
url: /2014/07/clear-visual-studio-recent-projects/
categories:
  - SQL Server
  - SSDT

---
Another little gem, clearing out those pesky recent projects from your menu on Visual Studio 2012. Fire up RegEdit and navigate to:

  * Files: HKCU\SOFTWARE\Microsoft\Visual Studio\11.0\FileMRUList\
  * Proj: HKCU\SOFTWARE\Microsoft\Visual Studio\11.0\ProjectMRUList\

Usual disclaimer
  
<a style="color: purple;" title="This external link will open in a new window" href="http://nathondalton.wordpress.com/2011/10/13/clear-visual-studio-recent-project-and-files/" target="_blank" rel="nofollow">http://nathondalton.wordpress.com/2011/10/13/clear-visual-studio-recent-project-and-files/</a>
