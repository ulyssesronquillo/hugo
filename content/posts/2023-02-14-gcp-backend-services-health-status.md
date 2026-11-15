---
title: 'gcp backend services health status'
author: ulysses

date: 2023-02-14
slug: gcp-backend-services-health-status
draft: false
---

Here’s how to get health status of a GCP Load Balancer Backend Services.

For all load balancers except target pool.

```
gcloud compute backend-services get-health BACKEND_SERVICE_NAME \
--region us-central1 \
--project project-id
```

For target pool load balancers, use this command.

```
gcloud compute target-pools get-health TARGET_POOL_NAME \
--region us-central1 \
--project project-id
```