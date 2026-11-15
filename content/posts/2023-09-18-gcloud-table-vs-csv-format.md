---
title: 'gcloud table vs csv format'
author: ulysses

date: 2023-09-18
slug: gcloud-table-vs-csv-format
draft: false
---

Differences using gcloud table vs CSV format.

Table format

```
gcloud compute snapshots list \
--filter="sourceSnapshotSchedulePolicy ~ $POLICY AND sourceDisk~$disk$" \
--format="table(sourceDisk.basename(),name,creationTimestamp,sourceSnapshotSchedulePolicy.basename())" \
--sort-by "~creationTimestamp" \
--project="$PROJECT"
```

CSV format

```
gcloud compute snapshots list \
--filter="sourceSnapshotSchedulePolicy ~ $POLICY AND sourceDisk~$disk$" \
--format="csv[separator=','](sourceDisk.basename(),name,creationTimestamp,sourceSnapshotSchedulePolicy.basename())" \
--sort-by "~creationTimestamp" \
--project="$PROJECT"
```

Output to file

```
gcloud compute snapshots list \
--filter="sourceSnapshotSchedulePolicy ~ $POLICY AND sourceDisk~$disk$" \
--format="csv[separator=','](sourceDisk.basename(),name,creationTimestamp,sourceSnapshotSchedulePolicy.basename())" \
--sort-by "~creationTimestamp" \
--project="$PROJECT" > output.csv
```