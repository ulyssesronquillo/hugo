---
title: 'create instance with alias ip'
author: ulysses

date: 2021-01-14
slug: create-instance-with-alias-ip
draft: false
---

How to create an instance from a snapshot with alias IP and reserved IPs.

```
#!/bin/bash
gcloud beta compute instances create jump-server \
--network-interface=aliases=10.128.1.0/24,private-network-ip=jump-server,subnet=default \
--machine-type=n1-standard-1 \``
--network-tier=PREMIUM \
--maintenance-policy=MIGRATE \
--service-account=xxxxxxxxxxxxx-compute@developer.gserviceaccount.com \
--tags=int-webserver \
--image=debian-10-buster-v20201216 \
--image-project=debian-cloud \
--boot-disk-size=20GB \
--boot-disk-type=pd-standard \
--boot-disk-device-name=jump-server-1 \
--no-shielded-secure-boot \
--shielded-vtpm \
--shielded-integrity-monitoring \
--labels=name=jump-server \
--reservation-affinity=any \
--zone=us-central1-a \
--project=airy-totality-151318
```

The default command uses –private-network-ip and –subnet options separately.

```
--private-network-ip 10.0.0.24 \
--subnet=default \
```

But when dealing with aliases, reserved IPs and subnets, use a single –network-interface option instead.

```
--network-interface=aliases=10.128.1.0/24,private-network-ip=jump-server,subnet=default \
```