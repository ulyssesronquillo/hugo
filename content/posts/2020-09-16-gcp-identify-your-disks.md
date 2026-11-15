---
title: 'gcp identify your disks'
author: ulysses

date: 2020-09-16
slug: gcp-identify-your-disks
draft: false
---

Here’s how to identify your disks on the system to cross check with GCP Dashboard.

```
ls -l /dev/disk/by-id
```

Result:

```
[root@servername ~]# ls -l /dev/disk/by-id
total 0
lrwxrwxrwx. 1 root root  9 Sep 15 05:30 google-boot -> ../../sda
lrwxrwxrwx. 1 root root 10 Sep 15 05:30 google-boot-part1 -> ../../sda1
lrwxrwxrwx. 1 root root  9 Sep 15 05:30 google-persistent-disk-1 -> ../../sdb
lrwxrwxrwx. 1 root root  9 Sep 15 05:30 scsi-0Google_PersistentDisk_boot -> ../../sda
lrwxrwxrwx. 1 root root 10 Sep 15 05:30 scsi-0Google_PersistentDisk_boot-part1 -> ../../sda1
lrwxrwxrwx. 1 root root  9 Sep 15 05:30 scsi-0Google_PersistentDisk_persistent-disk-1 -> ../../sdb
```