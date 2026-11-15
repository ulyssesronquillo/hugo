---
title: 'gcp ssl certificates'
author: ulysses

date: 2020-10-29
slug: gcp-ssl-certificates
draft: false
---

Here’s how to create a regional SSL Certificate.

```
gcloud compute ssl-certificates create my-ssl-cert \
--description "describe ssl certificate" \
--domains=domain1.com,domain2.com \
--certificate=cert.pem \
--private-key=private.key \
--region=us-central1
```

List the SSL certificates.

```
gcloud compute ssl-certificates list --project=project-id
```

Describe the SSL certificate.

```
gcloud compute ssl-certificates describe my-ssl-cert \
--region=us-central1 \
--project=project-id
```

Delete SSL certificate.

```
gcloud compute ssl-certificates delete my-ssl-cert \
--region=us-central1 \
--project=project-id
```