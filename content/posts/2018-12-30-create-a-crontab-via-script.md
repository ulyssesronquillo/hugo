---
title: 'create a crontab via script'
author: ulysses

date: 2018-12-30
slug: create-a-crontab-via-script
draft: false
---

How do you create a crontab entry via a Bash script? That’s a good question. Here is one solution:

```
(crontab -l 2>/dev/null; echo "* 11 * * * /path/to/job -with args") | crontab -
```

If you want to run it as a specific user, use the following:

```
(crontab -l -u user 2>/dev/null; echo "* 11 * * * /path/to/job -with args") | crontab -
```