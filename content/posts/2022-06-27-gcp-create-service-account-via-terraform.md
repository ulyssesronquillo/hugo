---
title: 'gcp create service account via terraform'
author: ulysses

date: 2022-06-27
slug: gcp-create-service-account-via-terraform
draft: false
---

How to create service account in GCP via Terraform.

```
provider "google" {
  project = "your_project_id"
}
resource "google_service_account" "service_account" {
  account_id   = "your-service-account-name"
  display_name = "test service account built by terraform"
}
```