---
title: 'date from a year ago'
author: ulysses

date: 2023-06-18
slug: date-from-a-year-ago
draft: false
---

Here’s a handy little script that has multiple applications to calculate date from a year ago.

```
#!/bin/bash
now=$(date +%Y%m%d-%H%M%S)
# mac os
year_old=$(date -v-1y +%Y%m%d-%H%M%S) 
# linux os 
year_old=$(date -d "-1 year" +%Y%m%d-%H%M%S)
echo $now
echo $year_old
```

Mac Os and Linux has slightly different formats. Pick one based on your OS.

Results

```
20230618-084940
20220618-084940
```