---
title: Enterprise vs Enterprise Core
author: matt
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

<blockquote class="twitter-tweet" data-width="550">
  <p lang="en" dir="ltr">
    <a href="https://twitter.com/matt40k" target="_blank" rel="nofollow">@matt40k</a> yeah, already been on msdn. Can't believe we're being made to wait!!!
  </p>
  
  <p>
    &mdash; Dave Kerby (@davekerby) <a href="https://twitter.com/davekerby/status/737912147703934976" target="_blank" rel="nofollow">June 1, 2016</a>
  </p>
</blockquote>



I spotted something odd.

<blockquote class="twitter-tweet" data-width="550">
  <p lang="en" dir="ltr">
    So whats the diff? Enterprise is only core licensed &#8211; <a href="https://t.co/2NgZG7siUD" target="_blank" rel="nofollow">https://t.co/2NgZG7siUD</a> <a href="https://twitter.com/hashtag/sqlhelp?src=hash" target="_blank" rel="nofollow">#sqlhelp</a> <a href="https://twitter.com/SQLServer" target="_blank" rel="nofollow">@sqlserver</a> <a href="https://twitter.com/SQLServerBI" target="_blank" rel="nofollow">@SQLServerBI</a> <a href="https://t.co/SP8OC5eLvD" target="_blank" rel="nofollow">pic.twitter.com/SP8OC5eLvD</a>
  </p>
  
  <p>
    &mdash; Matt Smith (@matt40k) <a href="https://twitter.com/matt40k/status/739752396046372864" target="_blank" rel="nofollow">June 6, 2016</a>
  </p>
</blockquote>



Now, in SQL Server terms there are two types of licensing

  * Server license + CALs
  * Cores (processors)

Expect for Enterprise, you can only get Core licenses.

The next question was, have they made a edition for Windows Server Core, a cut-down version &#8211; but the files sizes are the same, so this was unlikely, Microsoft also hadn&#8217;t made any statement about a cut-down version (which you&#8217;d expect), so again, this was unlikely.

Once again, Twitter came to the rescue, more precisely <a href="https://twitter.com/jdanton" target="_blank" rel="nofollow">Joey D&#8217;Antoni</a> did. The answer is legacy. Any old Microsoft licensing agreement with software assurance (SA) can get the latest version. This means that anyone who had an old SQL Server Enterprise Server\CAL license is now on the core based licensing &#8211; there are a few gotchas which Joey refers to &#8211; your still limited my the number of CALs, but your also limited to a max of 20 cores.

So in short

  * SQL Server 2016 Enterprise Core is limited to 20 cores and is for legacy license holders.
  * SQL Server 2016 Enterprise isn&#8217;t limited.
