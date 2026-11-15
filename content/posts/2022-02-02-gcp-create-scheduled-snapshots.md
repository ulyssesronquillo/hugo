---
title: 'gcp create scheduled snapshots'
author: ulysses

date: 2022-02-02
slug: gcp-create-scheduled-snapshots
draft: false
---

How to create scheduled snapshots in GCP.

```
gcloud compute resource-policies create snapshot-schedule hourly \
--description "my hourly schedule" \
--max-retention-days 7 \
--start-time 00:00 \
--hourly-schedule 1 \
--region us-central1 \
--on-source-disk-delete keep-auto-snapshots \
--storage-location US
```

Add snapshot schedule to a disk.

```
gcloud compute disks add-resource-policies disk-name \
--resource-policies hourly \
--zone us-central1-a
```

```
gcloud compute disks create disk-name \
--resource-policies hourly \
--zone us-central1-a
```

List snapshot schedules.

```
gcloud compute resource-policies list
```

Describe snapshot schedule.

```
gcloud compute resource-policies describe hourly
```