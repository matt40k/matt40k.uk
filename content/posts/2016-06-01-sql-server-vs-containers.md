---
title: SQL Server vs Containers
author: matt40k
type: post
date: 2016-06-01T08:56:30+00:00
url: /2016/06/sql-server-vs-containers/
categories:
  - Blog
  - SQL Server
  - SSDT

---
I was at event that <a href="https://twitter.com/simon_sabin" target="_blank" rel="nofollow">Simon Sabin</a> arranged, <a href="https://www.eventbrite.com/e/sql-server-tools-and-ssdt-shape-the-future-tickets-25256718525" target="_blank" rel="nofollow">SQL SERVER TOOLS and SSDT shape the future</a> and one of the questions that was asked, sorry, I forgot who asked (joys of leaving it too long before blogging about it &#8211; I want to say <a href="https://twitter.com/Gavin592" target="_blank" rel="nofollow" class="broken_link">Gavin</a>) was,

> How does (Windows) Containers fit into SQL Server?

This is basically Microsoft integrating the Docker technology into the Windows OS, so you in effect, ship a more complete solution. So for example, traditionally you&#8217;d ship the .NET application, with &#8220;Docker&#8221; you&#8217;d ship .NET and the OS along with the application &#8211; its not quite right, but that&#8217;s the basic idea.

At one of my local user groups, <a href="http://www.meetup.com/Suffolk-Developers/events/225341172/" target="_blank" rel="nofollow">Suffolk Devs, back in Sept 2015, Richard Vickerstaff done a talk on Docker</a>. One of the things I took away was this was very dev friendly, Richard was honest in the fact he has yet to deploy to production in this manner and the general feedback from the room at the time was no one else had &#8211; this doesn&#8217;t mean no-one has since of course, but you start to get the feeling the DBAs back home wouldn&#8217;t be happy. The other thing was the dev nature of it, for example, when your developing, you don&#8217;t want to be held back by &#8220;rules&#8221; that protect data, it is after all, development, your not going to have production data in your dev environment, right? So, if you don&#8217;t &#8220;pin&#8221; your storage to a persistent path, it&#8217;ll get purge when you stop your docker image. Can you image if you forgot to set the production config correctly and come a reboot all your data disappears? I can already here my friendly DBA screaming.

To get a docker\container for SQL Server, you&#8217;d either have to select one from list of images with SQL Server and its going to be huge, at least until they get SQL Server 2016 on <a href="https://blogs.technet.microsoft.com/windowsserver/2015/04/08/microsoft-announces-nano-server-for-modern-apps-and-cloud/" target="_blank" rel="nofollow">Nano Server</a>. Or you&#8217;d have to have PowerShell DSC to install and configure SQL Server.

In terms of Microsoft SQL Server, or really any database, I don&#8217;t believe you&#8217;d need to have it in a container, docker or otherwise. Since SQL Server 2012 you could have contained databases, this is where the login information that is normally stored in the instance master database within the application database. This pretty much made database independent of each other within the same SQL Server instance. I&#8217;d admit this was introduced for Azure, but this leads me onto my next point.

The best thing to manage is the the thing you don&#8217;t have to manage. So why would you want to spend time setting up SQL Server (as developer), regardless of if its in a container if you can just click a button or run a script to auto provision a Azure DB? Surely if your developing anything new, which is going to use a SQL Server database, surely you should be aiming for Azure DB? Even if you&#8217;re not, there aren&#8217;t that many types of SQL Server, you don&#8217;t often run into dependency hell with SQL Server, none that justifies building individual containers, at least, in my opinion.
