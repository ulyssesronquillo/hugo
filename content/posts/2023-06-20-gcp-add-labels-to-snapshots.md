---
title: 'gcp add labels to snapshots'
author: ulysses

date: 2023-06-20
slug: gcp-add-labels-to-snapshots
draft: false
---

Here’s the command to add labels to a snapshot.

```
gcloud compute snapshots add-labels SNAPSHOTNAME --labels=KEY=VALUE --project PROJECT
```