---
title: 'gcp adding labels to snapshots'
author: ulysses

date: 2023-07-01
slug: gcp-adding-labels-to-snapshots
draft: false
---

Here’s how to add labels to snapshots. It will cycle through from a list of disks.

```
#!/bin/bash
ts=$(date +%Y%m%d-%H%M%S)
log="add-labels-logs-$ts"
>$log
disks='manual-disks.txt'
now=$(date +%s)
epoch=$(date +%s -d "+14 days")
while read -r project snapshot; do
   echo "Project: $project"
   gcloud compute snapshots add-labels $snapshot --labels=delete-after=$epoch --project $project
done 
```