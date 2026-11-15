---
title: 'gcp manually move instance'
author: ulysses

date: 2021-01-10
slug: gcp-manually-move-instance
draft: false
---

Here’s how to move a VM instance from one zone to another. Moving an instance will involve destroying the instance from the source zone, and then recreating a replacement instance in the destination zone. To make the move easier, we will use a machine image to recreate the instance. We will also take advantage of the compute and IP address reservations to guarantee that we use the same IP address machine type. Some large machine types are hard to come by.

Get a list of compute and IP reservations.

```
gcloud compute addresses list
gcloud compute reservations list
```

Make reservations.

```
gcloud compute addresses create centos-ip-reservation --addresses 10.128.15.216 --region us-central1 --subnet default
gcloud compute reservations create centos-us-central1-b --machine-type=n1-standard-1 --vm-count=1 --zone us-central1-b
```

Create a machine image.

```
gcloud compute instances stop centos
gcloud beta compute machine-images create centos-image-00 --source-instance centos
```

Delete original instance.

```
gcloud compute instances delete centos
```

Create an instance from image in the new zone. Use the compute and ip reservations previously made.

```
gcloud beta compute instances create centos \
--no-address \
--private-network-ip 10.128.15.216 \
--source-machine-image=centos-image-00 \
--subnet=https://www.googleapis.com/compute/v1/projects/airy-totality-151318/regions/us-central1/subnetworks/default \
--machine-type=n1-standard-1 \
--reservation-affinity=any \
--reservation=centos-us-central1-b \
--zone=us-central1-b
```

Finally, clean it up once you are done.

```
gcloud compute instances delete centos --zone us-central1-b
gcloud compute addresses delete centos-ip-reservation 
gcloud compute reservations delete centos-us-central1-b --zone us-central1-b
gcloud beta compute machine-images delete centos-image-00
```