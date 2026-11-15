---
title: 'comparing time'
author: ulysses

date: 2017-05-09
slug: comparing-time
draft: false
---

Here’s a neat little PHP script that compares a set date/time to the current time. The time() function sets the $now variable to the current Unix timestamp. The strtotime() function converts a date string to a Unix timestamp. The result is assigned to the $setdate variable. The two variables containing Unix timestamps are then compared. A simple if-then statement determines if the date is in the past or future.

```
date_default_timezone_set('America/Los_Angeles');
$setdate = strtotime("May 9, 2017 12:27PM");
$now = time();
if ( $setdate > $now ) : echo 'Future date'; else : echo 'Past date'; endif;
```

You may have to change the default timezone if your server is in a different timezone.