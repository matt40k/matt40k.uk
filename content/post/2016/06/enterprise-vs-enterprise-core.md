---
title: Enterprise vs Enterprise Core
author: matt40k
type: post
date: 2016-06-07T20:32:57+00:00
url: /2016/06/enterprise-vs-enterprise-core/
categories:
  - Blog
  - Business Intelligence
  - Microsoft
  - SQL Server

---
This month saw the release of SQL Server 2016, which from a BI\Report point of view is huge. Once we had access to it

{{< tweet 737912147703934976 >}}

I spotted something odd.

{{< tweet 739752396046372864 >}}

Now, in SQL Server terms there are two types of licensing

  * Server license + CALs
  * Cores (processors)

Except for Enterprise, you can only get Core licenses.

The next question was, have they made a edition for Windows Server Core, a cut-down version &#8211; but the files sizes are the same, so this was unlikely, Microsoft also hadn&#8217;t made any statement about a cut-down version (which you&#8217;d expect), so again, this was unlikely.

Once again, Twitter came to the rescue, more precisely <a href="https://twitter.com/jdanton" target="_blank" rel="nofollow">Joey D&#8217;Antoni</a> did. The answer is legacy. Any old Microsoft licensing agreement with software assurance (SA) can get the latest version. This means that anyone who had an old SQL Server Enterprise Server\CAL license and upgrades is still on the old "non-core" licensing &#8211; there are a few gotchas which Joey refers to &#8211; your still limited my the number of CALs, but your also limited to a max of 20 cores.

So in short

  * SQL Server 2016 Enterprise is limited to 20 cores and is for legacy license holders.
  * SQL Server 2016 Enterprise Core isn&#8217;t limited.
