---
title: 'terraform gcp instance'
author: ulysses

date: 2021-02-03
slug: terraform-gcp-instance
draft: false
---

Here’s a Terraform script for launching an instance in Google Cloud Platform.

```
provider "google" {
  project = "project-id"
  region  = "us-central1"
  zone    = "us-central1-a"
}
resource "google_compute_instance" "wiki" {
  name         = "wiki"
  machine_type = "n2-standard-1"
  zone         = "us-central1-a"
  tags         = ["web-server"]
  labels = {
    name        = "wiki"
    environment = "development"
  }
  boot_disk {
    initialize_params {
      image = "centos-7-v20210122"
    }
  }
  network_interface {
    network = "default"
    access_config {
    }
  }
  service_account {
    email  = "service-account@email.com"
    scopes = ["cloud-platform"]
  }
}
```

Here’s a few Terraform commands.

```
terraform init
terraform plan
terraform apply
terraform destroy
```