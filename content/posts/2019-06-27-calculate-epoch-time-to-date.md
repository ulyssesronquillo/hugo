---
title: 'calculate epoch time to date'
author: ulysses

date: 2019-06-27
slug: calculate-epoch-time-to-date
draft: false
---

Here’s how to calculate epoch time using the Linux date command.

```
# Linux
date --date @1561266781
date -d @1561266781
# MacOS
date -r 1561266781
```

Output is : Sun Jun 23 05:13:01 UTC 2019

Show current epoch time.

```
date +%s
```

Output: 1561642643