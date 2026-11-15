---
title: 'gcp old scheduled snapshots'
author: ulysses

date: 2023-06-01
slug: gcp-old-scheduled-snapshots
draft: false
---

Here’s how to list GCP Scheduled Snapshots older than 14 days. projectIds.txt contains a list of projects.

```
#!/bin/bash
ts=$(date +%Y%m%d-%H%M%S)
old=$(date -v -14d +%Y-%m-%dT%H:%M:%S)
log="scheduled-snapshots-logs-$ts"
>$log
while read -r project; do
    snapshots=$(gcloud compute snapshots list \
                --project $project \
                --format="value(name)" \
                --filter="creationTimestamp
```