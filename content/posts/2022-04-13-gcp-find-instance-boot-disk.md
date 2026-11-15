---
title: 'gcp find instance boot disk'
author: ulysses

date: 2022-04-13
slug: gcp-find-instance-boot-disk
draft: false
---

How to find a boot disk from an instance.

```
gcloud compute instances describe servername \
--format='get(disks[0].source)' \
--zone=us-central1-c \
--project project-id
```

Result

```
https://www.googleapis.com/compute/v1/projects/project-id/zones/us-central1-f/disks/servername-boot
```