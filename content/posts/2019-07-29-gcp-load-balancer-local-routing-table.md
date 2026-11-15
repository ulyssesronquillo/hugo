---
title: 'gcp load balancer local routing table'
author: ulysses

date: 2019-07-29
slug: gcp-load-balancer-local-routing-table
draft: false
---

Test if the GCP Load Balancer is working by sending a curl command from the backend VM.

Assume the load balancer IP address is 10.1.2.99, and the VM is called vm-a1.

```
curl http://10.1.2.99
```

The end result is …

```
Page served from: vm-a1
```

Make sure there’s an entry in the local table that matches the IP of the load balancer.

```
ip route show table local | grep 10.1.2.99
```

If not, add it.

```
ip route add to local 10.1.2.99/32 dev eth0 proto 66
```

[Documentation](https://cloud.google.com/load-balancing/docs/internal/setting-up-internal)