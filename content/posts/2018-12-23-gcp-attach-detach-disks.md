---
title: 'gcp attach detach disks'
author: ulysses

date: 2018-12-23
slug: gcp-attach-detach-disks
draft: false
---

Google Cloud Platform just recently released a beta feature called detaching and attaching boot disks. Previously, boot disks were permanently attached to their VM instances. Now you have the ability to detach boot disk from your instance and attach it to another instance without deleting the original instance. You can also replace the boot disks for an instance rather than recreating the entire instance. I’ve tested it on my test account, and it works quite nicely.

I have 2 servers called blue-server and red-server. I’m detaching the disks on blue-server and attaching it to the red-server.

```
gcloud compute instances detach-disk blue-server --disk=blue-server-disk --zone us-central1-c
gcloud compute instances attach-disk cyan-server --disk=blue-server-disk --zone us-central1-c
gcloud compute instances detach-disk cyan-server --disk=blue-server-disk --zone us-central1-c
gcloud compute instances attach-disk blue-server --disk=blue-server-disk --zone us-central1-c
```

Results:

![](https://uly.me/wp-content/uploads/2018/12/gcp-attach-detach.png)

GCP: Attach and Detach Disks

This new GCP feature is still beta. There might be a few quirks here and there, but overall, it’s a must have feature if you are managing OS.