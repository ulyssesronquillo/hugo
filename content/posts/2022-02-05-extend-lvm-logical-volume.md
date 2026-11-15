---
title: 'extend lvm logical volume'
author: ulysses

date: 2022-02-05
slug: extend-lvm-logical-volume
draft: false
---

How to extend a LVM logical volume.

Extend the physical drive.

```
gcloud compute disks resize data-drive --size=40GB
```

SSH to a server and extend the physical volume.

```
$ pvresize /dev/sdb
  Physical volume "/dev/sdb" changed
  1 physical volume(s) resized or updated / 0 physical volume(s) not resized
```

```
$ pvs
  PV         VG Fmt  Attr PSize   PFree 
  /dev/sdb   vg lvm2 a--  
```

```
$ vgs
  VG #PV #LV #SN Attr   VSize   VFree 
  vg   1   1   0 wz--n- 
```

```
$ lvs
  LV   VG Attr       LSize   Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  data vg -wi-ao---- 
```

Extend the logical volume.

```
$ lvresize -l +100%FREE /dev/vg/data
```

Size of logical volume vg/data changed from 

Check the volume size.

```
$ lsblk
NAME      MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda         8:0    0   20G  0 disk 
├─sda1      8:1    0  200M  0 part /boot/efi
└─sda2      8:2    0 19.8G  0 part /
sdb         8:16   0   40G  0 disk 
└─vg-data 253:0    0   40G  0 lvm  /mnt
```

Still at 30GB.

```
$ df -Th
Filesystem          Type      Size  Used Avail Use% Mounted on
devtmpfs            devtmpfs  385M     0  385M   0% /dev
tmpfs               tmpfs     403M     0  403M   0% /dev/shm
tmpfs               tmpfs     403M  5.5M  398M   2% /run
tmpfs               tmpfs     403M     0  403M   0% /sys/fs/cgroup
/dev/sda2           xfs        20G  2.9G   17G  15% /
/dev/sda1           vfat      200M  5.8M  195M   3% /boot/efi
/dev/mapper/vg-data xfs        30G  247M   30G   1% /mnt
tmpfs               tmpfs      81M     0   81M   0% /run/user/1001
```

Extend the file system.

```
$ xfs_growfs /dev/vg/data
meta-data=/dev/mapper/vg-data    isize=512    agcount=12, agsize=655360 blks
         =                       sectsz=4096  attr=2, projid32bit=1
         =                       crc=1        finobt=1, sparse=1, rmapbt=0
         =                       reflink=1
data     =                       bsize=4096   blocks=7863296, imaxpct=25
         =                       sunit=0      swidth=0 blks
naming   =version 2              bsize=4096   ascii-ci=0, ftype=1
log      =internal log           bsize=4096   blocks=2560, version=2
         =                       sectsz=4096  sunit=1 blks, lazy-count=1
realtime =none                   extsz=4096   blocks=0, rtextents=0
data blocks changed from 7863296 to 10484736
```

Let's check again.

```
$ df -Th
Filesystem          Type      Size  Used Avail Use% Mounted on
devtmpfs            devtmpfs  385M     0  385M   0% /dev
tmpfs               tmpfs     403M     0  403M   0% /dev/shm
tmpfs               tmpfs     403M  5.5M  398M   2% /run
tmpfs               tmpfs     403M     0  403M   0% /sys/fs/cgroup
/dev/sda2           xfs        20G  2.9G   17G  15% /
/dev/sda1           vfat      200M  5.8M  195M   3% /boot/efi
/dev/mapper/vg-data xfs        40G  319M   40G   1% /mnt
tmpfs               tmpfs      81M     0   81M   0% /run/user/1001
```

The logical volume is now at 40GB.