---
title: 'gcp compute startup script'
author: ulysses

date: 2022-02-12
slug: gcp-compute-startup-script
draft: false
---

How to add startup and shutdown scripts on GCP Compute Engine.

Startup Script

```
gcloud compute instances add-metadata servername \
--project project-id \
--zone us-central1-c \
--metadata=startup-script='#! /bin/bash
sudo -i
echo "Time: $(date)" >> /tmp/date.txt'
```

Shutdown Script

```
gcloud compute instances add-metadata servername \
--project project-id \
--zone us-central1-c \
--metadata=shutdown-script='#! /bin/bash
# Shuts down Apache server
/etc/init.d/apache2 stop'
```