---
title: 'cloud filestore'
author: ulysses

date: 2019-01-10
slug: cloud-filestore
draft: false
---

Cloud Filestore is a managed file service by Google Cloud. It’s a shared file system similar to Amazon’s Elastic File System offering. Users of Cloud Filestore will experience something similar to when using a NAS drive (network attached storage). Filestore is used for both Compute and Kubernetes Engine instances. Unlike EFS where storage is unlimited, you have to specify a storage size when creating a new Filestore.

Create a Filestore:

```
gcloud beta filestore instances create nfs-server \
    --project=your-project-id \
    --location=your-region \
    --tier=STANDARD \
    --file-share=name="vol1",capacity=1TB \
    --network=name="default",reserved-ip-range="10.0.0.0/29"
```

Delete a Filestore:

```
gcloud beta filestore instances delete nfs-server --project=your-project-id --location=your-region
```

Instance clients can connect to the Filestore using a NFS client.

```
sudo apt-get -y update
sudo apt-get -y install nfs-common
sudo mkdir /mnt/test
sudo mount 10.0.0.59:/vol1 /mnt/test
sudo chmod go+rw /mnt/test
```