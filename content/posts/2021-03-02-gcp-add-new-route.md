---
title: 'gcp add new route'
author: ulysses

date: 2021-03-02
slug: gcp-add-new-route
draft: false
---

Here’s how to add a new route in Google Cloud Platform.

```
gcloud compute routes create name-of-new-route \
  --destination-range=200.20.0.0/15 \
  --next-hop-gateway=default-internet-gateway \
  --project=host-project \
  --network="default" \
  --priority=900
```