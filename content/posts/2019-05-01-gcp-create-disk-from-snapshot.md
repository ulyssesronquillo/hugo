---
title: 'gcp create disk from snapshot'
author: ulysses

date: 2019-05-01
slug: gcp-create-disk-from-snapshot
draft: false
---

Here’s how to create a disk from a snapshot via Google SDK.

```
gcloud compute disks create new-server-disk-2 \
--project=project-name \
--source-snapshot=server-disk-2 \
--zone=us-central1-b
```