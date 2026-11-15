---
title: 'gcp create instance with reservations'
author: ulysses

date: 2020-09-14
slug: gcp-create-instance-with-reservations
draft: false
---

Here’s how to create an instance with CUD (committed used discounts) reservations.

```
gcloud compute instances create instance-name \
--no-address \
--private-network-ip 10.0.0.24 \
--source-machine-image=projects/project-id/global/machineImages/image-name \
--subnet=https://www.googleapis.com/compute/v1/projects/your-project/regions/us-central1/subnetworks/your-sub-network \
--machine-type=n1-standard-4 \
--reservation-affinity=specific \
--reservation=your-reservation-name \
--zone=us-central1-a \
--project=your-project-id
```