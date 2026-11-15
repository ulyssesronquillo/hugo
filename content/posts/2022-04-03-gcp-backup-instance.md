---
title: 'gcp backup instance'
author: ulysses

date: 2022-04-03
slug: gcp-backup-instance
draft: false
---

Here’s the script to backup GCP disks.

```
#!/bin/bash
now=$(date +%s)
disks=$(gcloud compute disks list --project project-id --filter="users:instance" --format="value(name)")
for disk in $disks
do
  gcloud compute disks snapshot $disk \
  --snapshot-names=$disk-$now \
  --zone=us-central1-a \
  --project=project-id \
  --async
done
```