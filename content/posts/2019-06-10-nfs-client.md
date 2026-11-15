---
title: 'nfs client'
author: ulysses

date: 2019-06-10
slug: nfs-client
draft: false
---

Services to check.

```
chkconfig nfs on
service rpcbind start
service nfs start
mount -a
```

If missing, install it.

```
yum install nfs-utils nfs-utils-lib
```

Mount it.

```
mount -a
mount 192.168.1.200:/home /mnt/nfs/home
```

Add to /etc/fstab.

```
10.10.10.10:/home on /mnt/nfs/home type nfs (rw,noatime,nolock,bg,nfsvers=2,intr,tcp,actimeo=1800,addr=10.10.10.10)
```