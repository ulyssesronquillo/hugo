---
title: 'monitor disk performance'
author: ulysses

date: 2021-02-04
slug: monitor-disk-performance
draft: false
---

Here are a few utilities that monitor disk I/O performance.

```
iostat -d 5
pidstat -dl 20
iotop --only
```

The alternative is atop, which you can set to run every 10 seconds for 3 hours. The output can be viewed later.

```
atop -a -w logfile.atop 10 10800 &
```

Use atop to read the log file.

```
atop -r /path/to/logfile.atop
```