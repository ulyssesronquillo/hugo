---
title: 'gcp compute disks move'
author: ulysses

date: 2019-09-21
slug: gcp-compute-disks-move
draft: false
---

Here’s how to move a GCP disk between zones.

1. Make sure disk is detached from instance.
2. Use the GCloud Disk Move command.

```
# Detach disk from instance
gcloud compute instances detach-disk server --disk=server-boot
# Move disk from us-central1-b to us-central1-f
gcloud compute disks move example-disk-1 --zone us-central1-b --destination-zone us-central1-f
```