---
title: 'gcp create filestore'
author: ulysses

date: 2019-12-07
slug: gcp-create-filestore
draft: false
---

GCP Cloud Filestore is a managed file storage service for applications that require a filesystem interface and a shared filesystem for data. Filestore gives users a simple, native experience for standing up managed Network Attached Storage (NAS) with their Google Compute Engine and Kubernetes Engine instances.

With that said, let’s build one.

```
gcloud filestore instances create nfs-server \
  --project=[PROJECT_ID] \
  --zone=us-central1-c \
  --tier=STANDARD \
  --file-share=name="vol1",capacity=1TB \
  --network=name="default"
```

How to mount the filestore on clients.

```
sudo apt-get -y update
sudo apt-get -y install nfs-common
sudo mkdir /mnt/test
sudo mount 10.0.0.2:/vol1 /mnt/test
sudo chmod go+rw /mnt/test
```

Increase capacity to 3TB.

```
gcloud filestore instances update nfs-server 
  --project=myproject 
  --zone=us-central1-c 
  --file-share=name="vol1",capacity=3TB
```