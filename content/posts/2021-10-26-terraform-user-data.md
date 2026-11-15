---
title: 'terraform user data'
author: ulysses

date: 2021-10-26
slug: terraform-user-data
draft: false
---

Here’s how to add userdata in Terraform.

```
user_data = filebase64("${path.module}/example.sh")
```