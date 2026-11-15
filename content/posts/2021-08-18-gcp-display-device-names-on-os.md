---
title: 'gcp display device names on os'
author: ulysses

date: 2021-08-18
slug: gcp-display-device-names-on-os
draft: false
---

In GCP console you can see the VM’s Device Names. In this case, it’s boot and persistent-disk-1.

```
Name		          Device name
server-boot               boot	
server-data               persistent-disk-1	
```

To display the volume names on the OS, run this command.

```
$ ls -l /dev/disk/by-id
total 0
lrwxrwxrwx. 1 root root  9 Aug  2 01:12 google-boot -> ../../sda
lrwxrwxrwx. 1 root root 10 Aug  2 01:12 google-boot-part1 -> ../../sda1
lrwxrwxrwx. 1 root root  9 Aug 18 18:48 google-persistent-disk-1 -> ../../sdb
lrwxrwxrwx. 1 root root  9 Aug  2 01:12 scsi-0Google_PersistentDisk_boot -> ../../sda
lrwxrwxrwx. 1 root root 10 Aug  2 01:12 scsi-0Google_PersistentDisk_boot-part1 -> ../../sda1
lrwxrwxrwx. 1 root root  9 Aug 18 18:48 scsi-0Google_PersistentDisk_persistent-disk-1 -> ../../sdb
```

As you can see, boot and persistent-disk-1 are displayed along with its device names /dev/sda and /dev/sdb.