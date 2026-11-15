---
title: 'terraform gcloud vm image family'
author: ulysses

date: 2021-08-10
slug: terraform-gcloud-vm-image-family
draft: false
---

How to implement image family with Terraform in GCP.

Declare the machine image in terraform.tfvars.

```
image-family = "centos-7"
```

Declare data type for the machine image in maint.tf.

```
data "google_compute_image" "my_image" {
  family  = var.image-family
  project = "your-project-id"
}
```

In main.tf use “google\_compute\_instance” under boot disk section in main.tf.

```
boot_disk {
  initialize_params {
    image = data.google_compute_image.my_image.self_link
  }
}
```