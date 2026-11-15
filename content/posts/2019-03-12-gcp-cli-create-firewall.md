---
title: 'gcp cli create firewall'
author: ulysses

date: 2019-03-12
slug: gcp-cli-create-firewall
draft: false
---

Here’s how to add a firewall rule in Google Cloud Platform CLI

```
gcloud compute firewall-rules create "firewall-name" \
--description="firewall-description" \
--priority "1000" \
--direction INGRESS \
--action allow \
--network "network-name" \
--target-service-accounts="service@account.net" \
--source-ranges="10.0.0.0/8" \
--rules tcp:9001
```

Describe firewall rule.

```
gcloud compute firewall-rules describe firewall-name
```

Delete firewall rule.

```
gcloud compute firewall-rules delete firewall-name
```