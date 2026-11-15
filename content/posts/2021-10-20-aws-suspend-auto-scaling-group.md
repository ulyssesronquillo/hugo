---
title: 'aws suspend auto scaling group'
author: ulysses

date: 2021-10-20
slug: aws-suspend-auto-scaling-group
draft: false
---

You can administratively suspend a process in AWS Auto Scaling group for troubleshooting purposes.

Here are the available processes.

```
Terminate
Launch
AddToLoadBalancer
AlarmNotification
AZRebalance
HealthCheck
ReplaceUnhealthy
ScheduledActions
```

If you have difficulty launching a VM, check if any of these processes are suspended.

Removed them if applicable.