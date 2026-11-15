---
title: 'gcp sdk firewall rule ah and esp'
author: ulysses

date: 2020-02-26
slug: gcp-sdk-firewall-rule-ah-and-esp
draft: false
---

Here’s how to add a GCP firewall rule with the AH (authentication header) and ESP (Encapsulating Security Payload) protocols.

```
gcloud compute firewall-rules update "firewall-name" \
    --description="firewall description" \
    --priority "1000" \
    --target-service-accounts="service-account@gserviceaccount.com" \
    --destination-ranges="10.0.0.0/8" \
    --rules 50,51,tcp:80,udp:1000
```

There is no need to add protocols for AH and ESP. Just the port numbers.