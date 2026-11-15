---
title: 'mount and unmount efs'
author: ulysses

date: 2019-02-01
slug: mount-and-unmount-efs
draft: false
---

Here’s the command to mount and unmount AWS EFS. Assuming the EFS IP address is 10.0.0.23.

Mount:

```
mount -t nfs -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 10.0.0.23:/ /efs
```

Umount:

```
# lazy unmount
umount -l /efs
# force unmount
umount -f /efs
```

You may have to force it if it’s busy.