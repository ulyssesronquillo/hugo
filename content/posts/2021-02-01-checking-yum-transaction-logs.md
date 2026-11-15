---
title: 'checking yum transaction logs'
author: ulysses

date: 2021-02-01
slug: checking-yum-transaction-logs
draft: false
---

Check if package is on the system.

```
rpm -q httpd
httpd-2.4.6-97.el7.centos.x86_64
```

Check the history logs.

```
yum history list
Loaded plugins: fastestmirror
ID     | Login user               | Date and time    | Action(s)      | Altered
-------------------------------------------------------------------------------
   115 | System <unset>           | 2021-02-01 03:40 | Update         |    1
   114 | System <unset>           | 2021-02-01 02:03 | I, U           |   10
   113 | System <unset>           | 2021-01-29 19:54 | Update         |    1
   112 | System <unset>           | 2021-01-21 14:41 | Update         |    1
</unset></unset></unset></unset>
```

Check detail transaction id.

```
yum history info 114 | grep python 
    Updated python-perf-3.10.0-1160.6.1.el7.x86_64          @updates
    Updated python-sss-1.16.5-10.el7_9.5.x86_64             @your-repo
    Updated python-sssdconfig-1.16.5-10.el7_9.5.noarch      @your-repo
```

It looks like python was updated in transaction id #114.