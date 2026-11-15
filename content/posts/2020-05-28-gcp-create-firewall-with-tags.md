---
title: 'gcp create firewall with tags'
author: ulysses

date: 2020-05-28
slug: gcp-create-firewall-with-tags
draft: false
---

Here’s another way to create a firewall in GCP using network tag as targets.

```
gcloud compute firewall-rules create "firewall-name" \
    --description="egress rule to allow port 8000 to destination" \
    --priority "1000" \
    --direction EGRESS \
    --action allow \
    --network "your-network" \
    --target-tags="your-network-tag" \
    --destination-ranges="10.0.0.1/32" \
    --rules tcp:8000
```