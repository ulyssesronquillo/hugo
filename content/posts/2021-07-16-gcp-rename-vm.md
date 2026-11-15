---
title: 'gcp rename vm'
author: ulysses

date: 2021-07-16
slug: gcp-rename-vm
draft: false
---

There’s a new beta command to rename a GCP VM.

You must stop instance first.

```
gcloud compute instances stop server-name \
--zone us-central1-c \
--project your-project-id
```

Rename the instance.

```
gcloud beta compute instances set-name old-server-name \
--new-name=new-server-name \
--zone us-central1-c \
--project your-project-id
```

Start the instance.

```
gcloud compute instances start server-name \
--zone us-central1-c \
--project your-project-id
```

Login.

```
gcloud compute ssh server-name \
--zone us-central1-c \
--project your-project-id \
--internal-ip &
```