---
title: 'gcp create ssl certificate'
author: ulysses

date: 2021-06-13
slug: gcp-create-ssl-certificate
draft: false
---

```
gcloud compute ssl-certificates create certificate-name \
--description="ssl cert for domain-name.com" \
--domains=domain-name.com \
--certificate=certificate-file \
--private-key=private-key \
--region=us-central1-c \
--global
```