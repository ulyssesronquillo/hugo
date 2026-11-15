---
title: 'checking last patch'
author: ulysses

date: 2019-03-01
slug: checking-last-patch
draft: false
---

You can check when the system was last patch using the following.

```
# check RPM when the last updates were ran.
rpm -qa --last | grep kernel
# this is a bit of a stretch, but typically a reboot is performed after an upgrade.
uptime
```