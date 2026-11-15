---
title: 'gcp display roles on service account'
author: ulysses

date: 2021-10-06
slug: gcp-display-roles-on-service-account
draft: false
---

How to display roles assigned to a GCP service account.

```
gcloud projects get-iam-policy your-project-id \
--flatten="bindings[].members" \
--format='table(bindings.role)' \
--filter="bindings.members:your-service-account@your-project.iam.gserviceaccount.com"
```

Result

```
ROLE
organizations/xxxxxxxxxxxxx/roles/role-name
roles/compute.instanceAdmin.v1
roles/compute.networkViewer
roles/logging.logWriter
roles/monitoring.metricWriter
```