---
title: 'gcp list snapshots older than'
author: ulysses

date: 2023-06-16
slug: gcp-list-snapshots-older-than
draft: false
---

Here’s how to list snapshots older than a certain date. In this example, it’s snapshots older than 2023-12-14.

```
gcloud compute snapshots list --project $project --filter="creationTimestamp < 2023-12-14" --format="get(name,creationTimestamp)"
```
