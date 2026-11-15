---
title: 'gcp firewall source service account'
author: ulysses

date: 2021-02-16
slug: gcp-firewall-source-service-account
draft: false
---

Here’s how to create a firewall from service account to service account.

```
gcloud compute firewall-rules create "firewall-name" \
--description="firewall-description" \
--priority "1000" \
--direction INGRESS \
--action allow \
--network "network-name" \
--source-service-accounts="service@account.net" \
--target-service-accounts="service@account.net" \
--rules tcp:9001
```

Instead of source-range, it’s using source-service-accounts.