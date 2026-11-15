---
title: 'gcp extend ext4 boot volume'
author: ulysses

date: 2022-07-28
slug: gcp-extend-ext4-boot-volume
draft: false
---

Here’s how to extend an ext4 boot volume.

```
gcloud compute disks resize DISK_NAME --size DISK_SIZE --zone ZONE --project PROJECTID
```

Resize the file system. Example / is on sda3.

```
growpart /dev/sda 3
resize2fs /dev/sda3
```