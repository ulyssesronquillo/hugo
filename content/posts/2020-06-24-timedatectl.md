---
title: timedatectl
author: ulysses

date: 2020-06-24
slug: timedatectl
draft: false
---

Here’s another way of setting your server’s timezone. See all the options under North America.

```
timedatectl list-timezones | grep -i America
```

Set timezone.

```
timedatectl set-timezone America/New_York
```

To check.

```
date
```

Restart cron if needed.

```
systemctl restart cron.service
```