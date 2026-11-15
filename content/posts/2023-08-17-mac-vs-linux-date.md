---
title: 'mac vs linux date'
author: ulysses

date: 2023-08-17
slug: mac-vs-linux-date
draft: false
---

Converting Mac and Linux Dates

Linux

```
#!/bin/bash
start_time=$(date +%s)
log=$(date -d @$start_time +%Y%m%d-%H%M%S) 
start=$(date -d @$start_time)
echo $start_time
echo $log
echo $start
sleep 10
stop_time=$(date +%s)
stop=$(date -d @$stop_time)
echo $stop_time
echo $stop 
```

Mac

```
#!/bin/bash
start_time=$(date +%s)
log=$(date -r $start_time +%Y%m%d-%H%M%S) 
start=$(date -r $start_time)
echo $start_time
echo $log
echo $start
sleep 10
stop_time=$(date +%s)
stop=$(date -r $stop_time)
echo $stop_time
echo $stop
```

Same output for both

```
1692292771
20230817-171931
Thu Aug 17 05:19:31 PM UTC 2023
1692292781
Thu Aug 17 05:19:41 PM UTC 2023
```