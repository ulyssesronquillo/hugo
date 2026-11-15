---
title: 'gcp uefi compatible'
author: ulysses

date: 2020-06-08
slug: gcp-uefi-compatible
draft: false
---

When trying to boot from a disk created from snapshot and you’re getting an “UEFI feature is not available for this project” error, you’ll need to create a boot image with the –guest-os-features option set to “UEFI\_COMPATIBLE.”

```
gcloud compute disks create new-server-disk-2 \
--project=project-name \
--source-snapshot=server-disk-2 \
--zone=us-central1-b \
--guest-os-features="UEFI_COMPATIBLE"
```

It’s about enabling guest operating system features on custom images. The guest operating system features let you configure networking, security, storage, and operating system options on custom images to be used on boot disks.