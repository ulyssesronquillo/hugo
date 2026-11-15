---
title: 'take a gcp snapshot'
author: ulysses

date: 2018-08-08
slug: take-a-gcp-snapshot
draft: false
---

Here’s the gcloud command to create a snapshot of your GCP instance.

```
gcloud compute disks snapshot your-server \
--snapshot-names=your-server-180808 \
--project=your-project \
--zone=us-central1-c
```