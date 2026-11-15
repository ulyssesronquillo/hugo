---
title: 'aws efs /etc/fstab'
author: ulysses

date: 2019-12-23
slug: aws-efs-etc-fstab
draft: false
---

To automatically mount a EFS volume after each reboot, you’ll need to add the following format to /etc/fstab.

You can use the DNS name given by AWS.

```
fs-12345678:/ /mnt/efs efs defaults,_netdev 0 0
```

Or the IP address.

```
10.0.0.22:/ /mnt/efs efs defaults,_netdev 0 0
```

Mount all with fake and verbose.

```
mount -fav
```