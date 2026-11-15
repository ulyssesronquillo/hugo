---
title: 'gcp reserve alias ip'
author: ulysses

date: 2021-06-13
slug: gcp-reserve-alias-ip
draft: false
---

Make an IP alias reservation.

```
gcloud compute instances network-interfaces update instance-name \
--zone us-central1-c \
--aliases default:/32 \
--project project-id
```