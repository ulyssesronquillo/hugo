---
title: 'gcp change instance type'
author: ulysses

date: 2019-11-18
slug: gcp-change-instance-type
draft: false
---

Here’s how to change instance types via the command line

```
# Set Project
gcloud config set project your-project-id

# Change instance type to 2 CPU 20GB memory.
gcloud compute instances set-machine-type your-server-name \
--zone us-east1-a \
--machine-type n2-custom-2-20480

# Change instance type to original settings.
gcloud compute instances set-machine-type your-server-name \
--zone us-east1-a \
--machine-type n2-custom-2-15360
```