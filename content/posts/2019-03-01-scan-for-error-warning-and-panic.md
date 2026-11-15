---
title: 'scan for error, warning and panic'
author: ulysses

date: 2019-03-01
slug: scan-for-error-warning-and-panic
draft: false
---

Here’s a command to scan for any errors, warnings and panics on the system. If the file is too large, pipe it to more.

```
sudo grep -E -i -r 'error|warning|panic' /var/log
sudo grep -E -i -r 'error|warning|panic' /var/log >error-warning-panic.log
cat error-warning-panic.log | more
```