---
title: 'adding to crontab in bash'
author: ulysses

date: 2019-01-10
slug: adding-to-crontab-in-bash
draft: false
---

Here’s a neat command to append a job to a crontab within a Bash script.

```
crontab -l | { cat; echo "0 1 * * * /dir/script.sh > /logs/script.cronlog 2>&1"; } | crontab -
```

To validate, perform crontab -l to see if your changes are there.

```
crontab -l
```