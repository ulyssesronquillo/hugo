---
title: 'gcp ilb issue targets not healthy'
author: ulysses

date: 2020-01-14
slug: gcp-ilb-issue-targets-not-healthy
draft: false
---

I ran into an issue with Google Compute Engine TCP internal load balancer. The targets are unhealthy although all configs were correct installed. At one time the targets were working, but somehow they became unhealthy. In the end, 3 things needed to be checked.

1. Make sure GCP’s guest environment is installed.
2. Add the internal load balancer VIP address to the network properties.
3. Add route via cmd. “route ADD VIP MASK 255.255.255.255”

You will need to change the server’s IP from DHCP to static to add ILB VIP.