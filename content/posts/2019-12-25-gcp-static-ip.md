---
title: 'gcp static ip'
author: ulysses

date: 2019-12-25
slug: gcp-static-ip
draft: false
---

Create a static IP.

```
gcloud compute addresses create your-app-static-ip \
--region us-central1
```

List static IP.

```
gcloud compute addresses list your-static-ip-name --region us-central1
# or
gcloud compute addresses list --filter="name=('live-tfc-static-ip-address')"
```

Release static IP.

```
gcloud compute addresses delete your-app-static-ip \
--region us-central1
```