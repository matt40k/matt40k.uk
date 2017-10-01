---
title: Swollen Business Objects database
author: matt40k
type: post
date: 2015-07-19T18:58:50+00:00
url: /2015/07/swollen-business-objects-database/
categories:
  - Blog
  - Business Intelligence
tags:
  - T-SQL

---
Our new HR system uses SAP Business Objects for transactional reporting, as this was setup by our HR supplier we haven&#8217;t really got involved with it beyond writing a few custom reports, turns out we&#8217;ve written quite a few, so much so that the Business Objects CMS database has swollen to over 30 GBs. This, as you might have guessed, is causing a few performance problems. After a discussion with the supplier, we found out it was storing all the reports, even the ad-hoc one-off reports and we should have set a parameter to limit it.

After limiting it, the database still didn&#8217;t reduce the database size. A quick <a href="http://bukhantsov.org/2012/05/removing-the-failed-instances-manually-from-the-database/" target="_blank" rel="nofollow">Google found someone saying that it is because it can&#8217;t handle over 1 million rows of old reports</a>, which makes sense, running a SQL command that would delete over 30gb of data would have insane log file grow as well as massive performance problems.

The steps to resolve this, on MS-SQL, was to:

  1. Stop the Business Objects services on the app tier
  2. Ensure you have a backup of the database
  3. Set the recovery model to simple if it isn&#8217;t already
  4. Copy out all the required rows


  5. Truncate the table
  6. Re-insert the required rows back into the table
  7. Check everything looks ok, deal with the fact the database is now tiny
  8. Create another backup
  9. Start the app tier backup
