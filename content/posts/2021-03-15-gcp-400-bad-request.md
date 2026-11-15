---
title: 'gcp 400 bad request'
author: ulysses

date: 2021-03-15
slug: gcp-400-bad-request
draft: false
---

After logging in, I tried to run Terraform in GCP and received this error:

```
oauth2: cannot fetch token: 400 Bad Request
```

Here’s the fix. Login using application-default.

```
gcloud auth application-default login
```

You can then Terraform.

```
terraform apply
```