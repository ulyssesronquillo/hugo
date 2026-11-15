---
title: 'gcp move vm to another vpc'
author: ulysses

date: 2022-06-19
slug: gcp-move-vm-to-another-vpc
draft: false
---

Here’s how to move a VM to another VPC.

Stop VM.

```
gcloud compute instances stop $INSTANCE_NAME \
--zone $ZONE_NAME \
--project $PROJECT_ID
```

Move VM to another VPC.

```
gcloud compute instances network-interfaces update $INSTANCE_NAME \
--zone $ZONE_NAME \
--network-interface=nic0 \
--network $YOUR_NETWORK \
--subnetwork $YOUR_SUBNETWORK \
--project $PROJECT_ID
```

Start VM.

```
gcloud compute instances start $INSTANCE_NAME \
--zone $ZONE_NAME \
--project $PROJECT_ID
```