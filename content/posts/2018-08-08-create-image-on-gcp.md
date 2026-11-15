---
title: 'create image on gcp'
author: ulysses

date: 2018-08-08
slug: create-image-on-gcp
draft: false
---

Here’s the command to create an image from an existing VM instance. You can create an image from disks, snapshots, images or from a cloud storage file. You can use images you built to launch and restore VM instances, as well as create Instance Templates.

```
gcloud compute --project=your-project images create your-server --source-disk=your-server --source-disk-zone=us-central1-c
```