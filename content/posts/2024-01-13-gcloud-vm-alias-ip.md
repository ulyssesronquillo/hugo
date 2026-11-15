---
author: ulysses
title: 'gcloud vm alias ip'
date: 2024-01-13
slug: gcloud-vm-alias-ip
draft: false
---

In my [previous post]({% post_url 2024-01-12-terraform-gcp-vm-alias-ip %}), I've provisioned a vm with an alias ip using terraform. In this post, I will do the same but will use gcloud commands.

First, let's reserve an internal ip address.

```
gcloud compute addresses create host-alias-ip \
--addresses 10.10.10.10
--region us-central1 \
--subnet projects/projectid/regions/us-central1/subnetworks/subnet-us-central1 \
--project projectid
```

To allocate automatically, leave out --addresses.

```
gcloud compute addresses create host-alias-ip \
--region us-central1 \
--subnet projects/projectid/regions/us-central1/subnetworks/subnet-us-central1 \
--project projectid
```

To check reservations, list all in the project.

```
gcloud compute addresses list --project projectid
```

Attach an alias ip to a vm instance.

```
gcloud compute instances network-interfaces update hostname \
--aliases 10.10.10.10 \
--zone us-central1-c \
--project projectid
```

To detach leave aliases blank.

```
gcloud compute instances network-interfaces update hostname \
--aliases "" \
--zone us-central1-c \
--project projectid
```  
