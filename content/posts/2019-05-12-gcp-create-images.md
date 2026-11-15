---
title: 'gcp create images'
author: ulysses

date: 2019-05-12
slug: gcp-create-images
draft: false
---

Here’s how to create a GCP Disk Image from a Boot Drive.

- First, stop the instance.
- If you can’t, stop the applications/database from writing to disks.
- Run sudo sync .

### Create From Disk

```
gcloud compute images create the-new-image-name \
   --source-disk the-source-boot-disk \
   --source-disk-zone us-central1-a \
   --family the-image-family \
   [--force]
```

### Create From Image

```
gcloud compute images create the-new-image-name \
  --source-image the-source-image \
  --source-image-project the-project-where-the-image-is-located \
  --family the-image-family
```

### Create From Snapshot

```
gcloud compute images create the-new-image-name \
  --source-snapshot the-source-snapshot
```

For more [info](https://cloud.google.com/compute/docs/images/create-delete-deprecate-private-images).