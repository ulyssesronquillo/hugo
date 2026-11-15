---
title: 'corosync settings'
author: ulysses

date: 2021-08-05
slug: corosync-settings
draft: false
---

Here are the SAP Corosync settings.

```
[root@server ~]corosync-cmapctl | grep fail_recv_const
runtime.config.totem.fail_recv_const (u32) = 500
```