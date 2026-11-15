---
title: 'cronjob not running'
author: ulysses

date: 2018-04-16
slug: cronjob-not-running
draft: false
---

I had issues with cron. The jobs were not running, so it seemed. It turned out that they were in fact running. The jobs were firing off based on schedule. The problem was, cron didn’t have the correct path to the commands. I realized this when I looked at a couple of log files, in /var/mail and /var/log/syslog to look for clues. The fix was to include the path in cron.

Edit cron.

```
crontab -e
```

Add the shell and path at the top of the file.

```
SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin
```