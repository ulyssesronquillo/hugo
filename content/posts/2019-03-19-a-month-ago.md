---
title: 'a month ago'
author: ulysses

date: 2019-03-19
slug: a-month-ago
draft: false
---

How to get last month’s value. Useful with Bash scripts.

```
LASTMONTH = $(date +%Y%m -d '1 month ago')
echo $LASTMONTH
# Output is ...
201902
```