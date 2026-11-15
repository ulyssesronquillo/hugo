---
title: 'set linux time zone'
author: ulysses

date: 2020-01-27
slug: set-linux-time-zone
draft: false
---

Here’s another way of setting Linux time zone.

Check server time.

```
# check server time
date
```

Change to local time.

```
# set to local time
rm /etc/localtime
ln -s /usr/share/zoneinfo/America/Los_Angeles /etc/localtime
```

Check server time again.

```
# check server time again
date
```