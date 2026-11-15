---
title: 'gcp change vm service account'
author: ulysses
classic-editor-remember:
    - classic-editor
date: 2023-06-01
slug: gcp-change-vm-service-account
draft: false
---

Here’s how to change a VM’s service account in GCP

```
#!/bin/bash
read -p "project       : " project
read -p "instance      : " instance
read -p "srvAcct email : " serviceaccount
# stop instance
gcloud compute instances stop $instance --project $project 
# change service account
gcloud compute instances set-service-account $instance --service-account $serviceaccount --scopes cloud-platform --project $project 
# start instance 
gcloud compute instances start $instance --project $project
```