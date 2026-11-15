---
title: 'extend regional persistent disks'
author: ulysses

date: 2020-09-12
slug: extend-regional-persistent-disks
draft: false
---

Here’s the command to extend your regional persistent disks.

```
gcloud compute disks resize disk-name \
--size 100 \
--project project-id \
--region us-central1
```

Or you can specify by zone.

```
gcloud compute disks resize disk-name \
--size 100 \
--project project-id \
--zone us-central1-c
```

Display the updated disk details.

```
gcloud compute disks list \
--filter="name=disk-name" \
--project project-id
```

Although you’ve increased disk size, the file system doesn’t know the extra space. Run this (for XFS).

```
xfs_growfs /dev/sdb
```