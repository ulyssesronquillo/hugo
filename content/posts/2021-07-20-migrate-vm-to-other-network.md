---
title: 'migrate vm to other network'
author: ulysses

date: 2021-07-20
slug: migrate-vm-to-other-network
draft: false
---

Here’s how to move a VM to another network.

Stop the VM.

```
gcloud compute instances stop server-name \
--zone=us-central1-c \
--project project-id
```

Migrate the VM. Use self link for network and subnetwork.

```
gcloud compute instances network-interfaces update server-name \
--zone=us-central1-c \
--network-interface=nic0 \
--network=your-network \
--subnetwork=your-sub-network \
--project project-id
```

Start the VM.

```
gcloud compute instances start server-name \
--zone=us-central1-c \
--project project-id
```