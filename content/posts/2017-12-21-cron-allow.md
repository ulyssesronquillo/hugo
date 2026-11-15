---
title: 'cron allow'
author: ulysses

date: 2017-12-21
slug: cron-allow
draft: false
---

Some Linux distributions don’t turn on cron automatically for users. To give certain users access to cron, add them to cron.allow.

Edit cron.allow.

```
$ sudo nano /etc/cron.allow
```

Add one user per line.

```
johndoe
```

Save and close.