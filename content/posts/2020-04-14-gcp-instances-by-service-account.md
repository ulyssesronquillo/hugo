---
title: 'gcp instances by service account'
author: ulysses

date: 2020-04-14
slug: gcp-instances-by-service-account
draft: false
---

Here’s how to get a list of GCP instances using a specific service account.

```
gcloud compute instances list \
--filter="serviceAccounts.email=service-account@domain.com" \
--project project-id
```

To display all instances and their service accounts in JSON format.

```
gcloud compute instances list \
--format="json(name,serviceAccounts[].email)" \
--project your-project-id
```

Display in YAML which is also the Default.

```
gcloud compute instances list \
--format="default(name,serviceAccounts[].email)" \
--project your-project-id
```