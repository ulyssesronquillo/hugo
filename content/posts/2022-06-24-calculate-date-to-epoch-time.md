---
title: 'calculate date to epoch time'
author: ulysses

date: 2022-06-24
slug: calculate-date-to-epoch-time
draft: false
---

Here’s a script to convert date to epoch time on Mac OS.

```
#!/bin/bash
if [[ -z $1 ]]; then
  echo "Format: date2epoch.sh 2022/01/01-04:58:06"
else
  echo "$1"; date -j -f date -j -f "%Y/%m/%d-%T" "$1" +"%s"
fi
```

Result

```
$ ./date2epoch.sh 2022/08/31-22:00:00
2022/08/31-22:00:00
1661997600
```