---
title: Power BI failed to refresh - exception was raised
author: matt40k
type: post
date: 2021-10-03T14:22:00+00:00
url: /2021/10/pbi-failure-exception/
type: post
description: 'Power BI refresh failure - exception was raised'
draft: false
categories:
  - Blog
tags:
  - PowerBI
---

I was recently seeing alot of Power BI data refresh failures on newly created environments, however existing environments would be fine. The errors that were occuring were as followed:

```
Failed to save modifications to the server. Error returned: 'Attempt to read when no data is present.. The exception was raised by the IDataReader interface. Please review the error message and provider documentation for further information and corrective action.
```

```
The command has been canceled.. The exception was raised by the IDbCommand interface.
```
 
``` 
There was an error when processing the data in the dataset.
```

```
Attempt to read when no data is present.. The exception was raised by the IDataReader interface. Please review the error message and provider documentation for further information and corrective action.
```

When I drilled into it, I could see that I could manually refresh ok; if I was to take the M code and copy it into Power BI desktop and connect directly to the same Azure Data Lake gen2, it would load correctly every time. So at this point I new it would have to do with the incremental refresh. It would be something to do with the pollingExpression, this is the M code that returns the max datetime of the refresh data so Power BI knows what data, or more precisely which partitions need to be processed. I went back and reviewed [Patrick's](https://twitter.com/patrickdba) video on [Handling deletes within Incremental Refresh in Power BI](https://www.youtube.com/watch?v=nKVrl0ec6uE) and spotted his comment about nulls.

It's always nulls.

```
    MaxLastUpdateTime = List.Max(#"Removed Other Columns"[Date]),
    accountForNull = if MaxLastUpdateTime = null then #datetime(1900, 01, 01, 00, 00, 00) else MaxLastUpdateTime
in
    accountForNull
```

and that was it, null. Power BI was expecting a DateTime, not a DateTime?. Which is annoying that Microsoft didn't cope with a null, but hey. It's easy to fix. Replace the null, with "empty", which for DateTime we basically set as 1900-01-01. To be fair I could have put anything before the minimum age I set to refresh from.

More information on [Incremental refresh](https://docs.microsoft.com/en-us/power-bi/connect-data/incremental-refresh-xmla) check out [Microsoft post](https://docs.microsoft.com/en-us/power-bi/connect-data/incremental-refresh-xmla). I also highly recommend using [Tabular Editor](https://docs.tabulareditor.com/te2/incremental-refresh.html), this awesome tool made the whole process a whole lot easier.
