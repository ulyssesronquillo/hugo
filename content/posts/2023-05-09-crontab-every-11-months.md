---
title: 'crontab every 11 months'
author: ulysses

date: 2023-05-09
slug: crontab-every-11-months
draft: false
---

If you want to run a script every 11 months, here’s the crontab entry.

```
* * 1 */11 * /bin/bash /path/to/script.sh 
```