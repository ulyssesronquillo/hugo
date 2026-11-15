---
title: 'gcp create instance from snapshot'
author: ulysses

date: 2019-09-17
slug: gcp-create-instance-from-snapshot
draft: false
---

There are two steps in creating an instance from a snapshot.

1. Create a disk from snapshot
2. Create an instance from the disk

Create a disk from snapshot.

```
gcloud compute disks create "hostname-boot" \
--project "project-id" \
--zone "us-central1-a" \
--source-snapshot "snapshot-name" \
--type "pd-standard" \
--size "100"
```

Create an instance from disk.

```
gcloud beta compute instances create hostname \
--project=project-id \
--zone=us-central1-a \
--subnet=your-subnetwork \
--machine-type=n1-standard-1 \
--no-address \
--maintenance-policy=MIGRATE \
--service-account=service.account@developer.gserviceaccount.com \
--disk=name=instance-1,device-name=instance-1,mode=rw,boot=yes,auto-delete=yes \
--reservation-affinity=any \
--labels=builtby=john.doe \
--tags=web \
--scopes= \
--metadata= 
```