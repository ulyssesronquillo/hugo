---
title: 'setup lvm on a vm'
author: ulysses

date: 2022-02-05
slug: setup-lvm-on-a-vm
draft: false
---

How to setup Logical Volume Manager on a VM.

Install LVM.

```
yum install lvm2
```

Check the disks available. We are going to run LVM on /dev/sdb.

```
$ lsblk
NAME   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda      8:0    0   20G  0 disk 
├─sda1   8:1    0  200M  0 part /boot/efi
└─sda2   8:2    0 19.8G  0 part /
sdb      8:16   0   20G  0 disk
```

Create a physical volume on /dev/sdb.

```
$ pvcreate /dev/sdb
  Physical volume "/dev/sdb" successfully created.
$ pvs
  PV         VG Fmt  Attr PSize   PFree
  /dev/sdb   vg lvm2 a--  
```

Create a volume group called vg.

```
$ vgcreate vg /dev/sdb
  Volume group "vg" successfully created
$ vgs
  VG #PV #LV #SN Attr   VSize   VFree  
  vg   1   0   0 wz--n- 
```

Create a 10GB logical volume group called data.

```
$ lvcreate -L 10G -n data vg
  Logical volume "data" created.
$ lvs
  LV   VG Attr       LSize  Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  data vg -wi-a----- 10.00g
```

Format the volume group and mount it.

```
$ mkfs.xfs /dev/vg/data
meta-data=/dev/vg/data           isize=512    agcount=4, agsize=655360 blks
         =                       sectsz=4096  attr=2, projid32bit=1
         =                       crc=1        finobt=1, sparse=1, rmapbt=0
         =                       reflink=1
data     =                       bsize=4096   blocks=2621440, imaxpct=25
         =                       sunit=0      swidth=0 blks
naming   =version 2              bsize=4096   ascii-ci=0, ftype=1
log      =internal log           bsize=4096   blocks=2560, version=2
         =                       sectsz=4096  sunit=1 blks, lazy-count=1
realtime =none                   extsz=4096   blocks=0, rtextents=0
Discarding blocks...Done.
$ mount /dev/vg/data /mnt
```

Check your logical volume. It says 10GB.

```
$ df -Th
Filesystem          Type      Size  Used Avail Use% Mounted on
devtmpfs            devtmpfs  385M     0  385M   0% /dev
tmpfs               tmpfs     403M     0  403M   0% /dev/shm
tmpfs               tmpfs     403M  5.5M  398M   2% /run
tmpfs               tmpfs     403M     0  403M   0% /sys/fs/cgroup
/dev/sda2           xfs        20G  2.9G   17G  15% /
/dev/sda1           vfat      200M  5.8M  195M   3% /boot/efi
tmpfs               tmpfs      81M     0   81M   0% /run/user/1000
/dev/mapper/vg-data xfs        10G  104M  9.9G   2% /mnt
```

Let's now extend the logical volume to 20GB.

```
$ lvextend -l +100%FREE /dev/vg/data
  Size of logical volume vg/data changed from 10.00 GiB (2560 extents) to 
```

Although lsblk says 20GB, our logical volume still says 10GB

```
$ lsblk
NAME      MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda         8:0    0   20G  0 disk 
├─sda1      8:1    0  200M  0 part /boot/efi
└─sda2      8:2    0 19.8G  0 part /
sdb         8:16   0   20G  0 disk 
└─vg-data 253:0    0   20G  0 lvm  /mnt
$ df -Th
Filesystem          Type      Size  Used Avail Use% Mounted on
devtmpfs            devtmpfs  385M     0  385M   0% /dev
tmpfs               tmpfs     403M     0  403M   0% /dev/shm
tmpfs               tmpfs     403M  5.5M  398M   2% /run
tmpfs               tmpfs     403M     0  403M   0% /sys/fs/cgroup
/dev/sda2           xfs        20G  2.9G   17G  15% /
/dev/sda1           vfat      200M  5.8M  195M   3% /boot/efi
tmpfs               tmpfs      81M     0   81M   0% /run/user/1000
/dev/mapper/vg-data xfs        10G  104M  9.9G   2% /mnt
```

We need to grow the file system.

```
$ xfs_growfs /dev/vg/data
meta-data=/dev/mapper/vg-data    isize=512    agcount=4, agsize=655360 blks
         =                       sectsz=4096  attr=2, projid32bit=1
         =                       crc=1        finobt=1, sparse=1, rmapbt=0
         =                       reflink=1
data     =                       bsize=4096   blocks=2621440, imaxpct=25
         =                       sunit=0      swidth=0 blks
naming   =version 2              bsize=4096   ascii-ci=0, ftype=1
log      =internal log           bsize=4096   blocks=2560, version=2
         =                       sectsz=4096  sunit=1 blks, lazy-count=1
realtime =none                   extsz=4096   blocks=0, rtextents=0
data blocks changed from 2621440 to 5241856
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
tmpfs               tmpfs      81M     0   81M   0% /run/user/1000
/dev/mapper/vg-data xfs        20G  176M   20G   1% /mnt
```

It now says 20GB.