---
title: 'resizing xfs root partition in gcp'
author: ulysses

date: 2021-07-16
slug: resizing-xfs-root-partition-in-gcp
draft: false
---

How to resize a root partition in GCP.

Increase disk size.

```
gcloud compute disks resize server-boot-disk-name \
--size=50GB \
--zone us-central1-c \
--project your-project-id
```

Run growpart.

```
growpart /dev/sda 1
```

Run xfs\_growfs.

```
xfs_growfs /dev/sda1
```

To verify, run these.

```
lsblk
df -Th
```