---
title: 'gcp compute add startup-script to metadata'
author: ulysses

date: 2022-02-02
slug: gcp-compute-add-startup-script-to-metadata
draft: false
---

How to add a startup-script to metadata. The script executes every time VM is started.

```
gcloud compute instances add-metadata instance-name \
--project your-project-id \
--zone us-central1-c \
--metadata=startup-script='#! /bin/bash
sudo -i
echo "Time: $(date)" >> /tmp/date.txt'
```