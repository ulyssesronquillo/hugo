---
title: 'display sequential write throughput'
author: ulysses

date: 2020-02-05
slug: display-sequential-write-throughput
draft: false
---

Here’s a dd command to display sequential write throughput from the command line.

```
time dd if=/dev/zero of=/mounted_backup_volume/zero.raw bs=1M count=512 status=progress
```

Output is.

```
512+0 records in
512+0 records out
536870912 bytes (537 MB) copied, 0.667813 s, 804 MB/s

real    0m0.669s
user    0m0.000s
sys     0m0.359s
```