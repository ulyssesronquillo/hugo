---
title: 'gcp convert standard to ssd'
author: ulysses

date: 2019-08-20
slug: gcp-convert-standard-to-ssd
draft: false
---

How to convert Persistent Standard disk to SSD.

First create a snapshot of the disk.

```
gcloud compute disks snapshot your-server \
--snapshot-names manual-snapshot-disk-1 \
--project your-project \
--zone us-central1-c
```

Restore snapshot to SSD format.

```
gcloud compute disks create disk-1-ssd \
--source-snapshot manual-snapshot-disk-1 \
--project your-project \
--zone us-central1-a \
--type pd-ssd \
--size 10GB
```

Swap disks using GCP attach and detach.