---
title: 'aws xfs volume setup'
author: ulysses

date: 2020-03-31
slug: aws-xfs-volume-setup
draft: false
---

Here’s how to setup a XFS volume.

```
file -s /dev/nvme2n1
mkfs -t xfs /dev/nvme2n1
```

Mount to /data.

```
mkdir /data
mount /dev/nvme2n1 /data
```

Add to /etc/fstab.

```
vim /etc/fstab
#
#
UUID=xxxxxxxxxxxxxxxxxxxxxx /data  xfs  defaults 0 0
```