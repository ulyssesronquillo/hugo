---
title: 'gcp create internal ip reservation'
author: ulysses

date: 2020-09-29
slug: gcp-create-internal-ip-reservation
draft: false
---

Here’s how to create an internal IP reservation in GCP.

```
gcloud compute addresses create my-private-ip-reservation \
--addresses 10.128.0.15 \
--region us-central1 \
--subnet default \
--project project-id
```

To list your reserved IPs.

```
gcloud compute addresses list \
--project project-id
```