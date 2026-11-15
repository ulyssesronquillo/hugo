---
title: 'nfs fails to mount on bootup'
author: ulysses

date: 2019-07-28
slug: nfs-fails-to-mount-on-bootup
draft: false
---

Check if rpcbind is running.

```
service rpcbind status|start|stop|restart
```

Or you can also clean the NFS cache.

```
service rpcbind stop
service nfslock stop
rm -rf /var/lib/nfs/statd/sm/*
rm -rf /var/lib/nfs/statd/sm.bak/*
service rpcbind start
service nfslock start
```