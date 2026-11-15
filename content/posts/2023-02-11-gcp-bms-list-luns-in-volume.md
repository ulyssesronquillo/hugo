---
title: 'gcp bms list luns in volume'
author: ulysses

date: 2023-02-11
slug: gcp-bms-list-luns-in-volume
draft: false
---

Here’s how to list the luns for a particular volume.

```
gcloud bms volumes luns list --project project-id --region us-central1 --volume at-xxxxxxx-volxxx
```