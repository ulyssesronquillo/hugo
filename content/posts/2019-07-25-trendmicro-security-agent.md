---
title: 'trendmicro security agent'
author: ulysses

date: 2019-07-25
slug: trendmicro-security-agent
draft: false
---

How to start/stop/restart/status TrendMicro Security agent.

```
/etc/init.d/ds_agent start
/etc/init.d/ds_agent stop
/etc/init.d/ds_agent restart
/etc/init.d/ds_agent status
/etc/init.d/ds_agent reset
```

Check if installed.

```
rpm -qa | grep 'ds_agent'
```

Install with verbose and hash.

```
rpm -ivh package-name
```

Uninstall with verbose.

```
rpm -ev package-name
```