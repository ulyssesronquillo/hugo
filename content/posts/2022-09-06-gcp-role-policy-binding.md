---
title: 'gcp role policy binding'
author: ulysses

date: 2022-09-06
slug: gcp-role-policy-binding
draft: false
---

How to display the policy binding.

```
gcloud compute instances get-iam-policy SERVER --project=PROJECT_ID --zone=ZONE
```

Result

```
# There is no binding policy
etag: ACAB

# There is a binding policy
bindings:
- members:
  - serviceAccount:SERVICEACCOUNT
  role: organizations/xxxxxxxxxxxx/roles/ROLE
etag: xxxxxxxxxxx=
version: 1
```

Add a role binding policy

```
gcloud compute instances add-iam-policy-binding SERVER \
--project=PROJECT_ID \
--zone=ZONE \
--member=serviceAccount:SERVICEACCOUNT \
--role="organizations/xxxxxxxxxxxx/roles/ROLE"
```

Remove a role binding policy

```
gcloud compute instances remove-iam-policy-binding SERVER \
--project=PROJECT_ID \
--zone=ZONE \
--member=serviceAccount:SERVICEACCOUNT \
--role="organizations/xxxxxxxxxxxx/roles/ROLE"
```