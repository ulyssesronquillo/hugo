---
title: 'gcp restore'
author: ulysses

date: 2019-06-16
slug: gcp-restore
draft: false
---

How to restore from GCP Snapshots. Let’s say you have an instance called webserver with 2 disks.

Restore from snapshots:

```
gcloud compute disks create webserver-boot-r \
--project=your-project \
--source-snapshot=webserver-boot-190616 \
--zone=us-central1-a
gcloud compute disks create webserver-data-r \
--project=your-project \
--source-snapshot=webserver-data-190616 \
--zone=us-central1-a
```

Stop instance. Detach and attach disks:

```
gcloud compute instances detach-disk webserver --disk=webserver-boot --zone us-central1-a
gcloud compute instances attach-disk webserver --disk=webserver-boot-r --zone us-central1-a --boot
gcloud compute instances detach-disk webserver --disk=webserver-data --zone us-central1-a
gcloud compute instances attach-disk webserver --disk=webserver-data-r --zone us-central1-a
```

Boot instance.