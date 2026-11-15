---
title: 'extend lvm volume'
author: ulysses

date: 2019-01-28
slug: extend-lvm-volume
draft: false
---

Extending a LVM logical volume can be tricky. Extending a physical volume especially a boot drive is even more challenging. To make things simple, you can just easily add a new physical disk to your physical volume group. Here are the steps:

```
# add disk to your instance. 
fdisk /dev/sdh
pvcreate /dev/sdh1
vgextend system /dev/sdh1
lvextend -l +100%FREE /dev/system/opt
resize2fs /dev/system/opt
```

The fdisk command requires a few steps inside such as creating a new partition, changing the partition to type to “8e” which is Linux LVM, and then writing your changes to disk.

The rest are pretty much self explanatory. It’s about creating a physical volume, extending the volume group, extending the logical volume, and then finally resizing the file system.