---
title: 'gcp manual snapshots'
author: ulysses

date: 2023-06-01
slug: gcp-manual-snapshots
draft: false
---

Here’s how to list GCP’s manual snapshots. projectIds.txt contains a list of projects.

```
#!/bin/bash
ts=$(date +%Y%m%d-%H%M%S)
log="manual-snapshots-logs-$ts"
>$log
while read -r project; do
    snapshots=$(gcloud compute snapshots list \
                --project $project \
                --filter="sourceSnapshotSchedulePolicy!=''" \
                --format="value(name)")
    for snapshot in $snapshots
    do
        printf "%-30s %-30s \n" "$project" "$snapshot"  | tee -a $log
    done
done > projectIds.txt
```

Another option.

```
#!/bin/bash
ts=$(date +%Y%m%d-%H%M%S)
log="manual-snapshots-logs-$ts"
>$log
while read -r project; do
    snapshots=$(gcloud compute snapshots list \
                --project $project \
                --filter="-sourceSnapshotSchedulePolicy:*" \
                --format="value(name)")
    for snapshot in $snapshots
    do
        printf "%-30s %-30s \n" "$project" "$snapshot"  | tee -a $log
    done
done > projectIds.txt
```