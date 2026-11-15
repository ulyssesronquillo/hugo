---
title: 'internet test'
author: ulysses

date: 2020-06-26
slug: internet-test
draft: false
---

My internet has been flaky lately. I wrote a script that logs my internet connection.

I’m running it in cron every minute.

```
#!/bin/bash
log='/home/ulysses/Code/spectrum.log'
if nc -zw1 google.com 443;
then 
  echo 'Spectrum is up' $(date) >> $log
else 
  echo 'Spectrum is down' $(date) >> $log
fi
```

To view, just cat the log.

```
cat spectrum.log 
Spectrum is up Fri Jun 26 15:14:01 EDT 2020
Spectrum is up Fri Jun 26 15:15:01 EDT 2020
Spectrum is up Fri Jun 26 15:16:01 EDT 2020
Spectrum is up Fri Jun 26 15:17:01 EDT 2020
Spectrum is up Fri Jun 26 15:18:01 EDT 2020
```

So, I now have a record when it was up or down.