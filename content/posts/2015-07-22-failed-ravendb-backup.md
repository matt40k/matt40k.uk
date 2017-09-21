---
title: Failed RavenDB backup
author: matt
type: post
date: 2015-07-22T11:55:55+00:00
url: /2015/07/failed-ravendb-backup/
categories:
  - Blog

---
I had a rather odd error with <a href="http://octopusdeploy.com/" target="_blank" rel="nofollow">OctopusDeploy </a>where the <a href="http://ravendb.net/" target="_blank" rel="nofollow">RavenDB</a> backups were failing. Turns out the problem was because I had assigned 1 IPv4 address to <a href="http://octopusdeploy.com/" target="_blank" rel="nofollow">OctopusDeploy </a>and another IPv4 address for <a href="https://www.jetbrains.com/teamcity/" target="_blank" rel="nofollow">TeamCity</a>. Oddly the RavenDB backup routine referenced the localhost address &#8211; 127.0.0.1, it appeared to be hardcode with no option other then changing port. This was especially weird as the <a href="http://octopusdeploy.com/" target="_blank" rel="nofollow">OctopusDeploy </a>service, was able to access it fine. To resolve &#8211; at least long enough to get a backup to migrate to v3 which uses <a href="http://www.microsoft.com/en-gb/server-cloud/products/sql-server/" target="_blank" rel="nofollow">SQL Server</a> &#8211; was to setup a port proxy so accessing TCP port 10931 on the local loopback would resolve to the same port but on a the actual public IPv4

To do this run Command Prompt as Administrator (right-click, Run As Administrator) then type

> netsh
  
> interface portproxy
  
> add v4tov4 listenaddress=127.0.0.1 listenport=10931 connectaddress={{your ip}} connectport=10931

Remember to replace {{your ip}} with the actual IP address
