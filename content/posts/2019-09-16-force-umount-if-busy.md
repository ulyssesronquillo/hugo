---
title: 'force umount if busy'
author: ulysses

date: 2019-09-16
slug: force-umount-if-busy
draft: false
---

If device is busy and you can’t umount it, try it with -l option (lazy unmount). Or you can force it.

```
# standard
umount /mnt/data
# lazy umount
umount -l /mnt/data
# force
umount -f /mnt/data
```

Lazy unmount is safer since it will detach immediately and clean up all references to the file system. Force is a bit more drastic.