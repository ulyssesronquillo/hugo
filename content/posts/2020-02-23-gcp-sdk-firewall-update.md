---
title: 'gcp sdk firewall update'
author: ulysses

date: 2020-02-23
slug: gcp-sdk-firewall-update
draft: false
---

Here’s how to update an existing GCP firewall.

Ingress

```
gcloud compute firewall-rules update "firewall-rule-name" \
--description="firewall description" \
--priority="1000"
--target-service-accounts="service-account@gserviceaccount.com" \
--source-ranges="10.0.0.0/8"
--rules tcp:80,tcp:443,udp:1000-1100
```

Egress

```
gcloud compute firewall-rules update "firewall-rule-name" \
--description="firewall description" \
--priority="1000"
--target-service-accounts="service-account@gserviceaccount.com" \
--destination-ranges="10.0.0.0/8"
--rules tcp:80,tcp:443,udp:1000-1100
```