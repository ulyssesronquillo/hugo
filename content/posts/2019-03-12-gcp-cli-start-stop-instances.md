---
title: 'gcp cli start stop instances'
author: ulysses

date: 2019-03-12
slug: gcp-cli-start-stop-instances
draft: false
---

Here’s the CLI commands to start and stop Google Cloud instances.

```
gcloud compute instances start server-name --zone=us-central1-c
gcloud compute instances stop server-name --zone=us-central1-c
gcloud compute instances reset server-name --zone=us-central1-c
```