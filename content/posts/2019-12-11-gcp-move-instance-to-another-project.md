---
title: 'gcp move instance to another project'
author: ulysses

date: 2019-12-11
slug: gcp-move-instance-to-another-project
draft: false
---

Here’s how to copy a disk from one project to another.

```
gcloud compute disks create lamp-server \
--source-snapshot https://www.googleapis.com/compute/v1/projects/project-id/global/snapshots/lamp-server \
--project next-project-id \
--zone us-central1-a
```

Once all the disks are copied. You can create a snapshot of the boot.

```
gcloud compute disks snapshot lamp-server
```

Create an instance from snapshot.

```
gcloud compute disks create "hostname-boot" \
--project "project-id" \
--zone "us-central1-a" \
--source-snapshot "snapshot-name" \
--type "pd-standard" \
--size "100"
```