---
title: 'use curl on load balancers'
author: ulysses

date: 2019-12-18
slug: use-curl-on-load-balancers
draft: false
---

You can use the curl command to test if your load balancer is working as expected. The curl command will alternately and randomly access several instances in your load balancer. If you have 3 instances behind your load balancer, it will be cycled across all 3. The -m1 command means max time is set to 1 second.

```
while true; do curl -m1 [IP_ADDRESS]; done
```