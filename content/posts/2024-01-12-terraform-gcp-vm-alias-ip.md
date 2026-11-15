---
author: ulysses
title: 'terraform gcp vm alias ip'
date: 2024-01-12
slug: terraform-gcp-vm-alias-ip
draft: false
---

How to build a VM in GCP with a secondary alias IP. Assuming that you already have a compute and a local block in your Terraform file.



Go to the locals block and add the local variables you'll need.

```
locals {
  project          = "projectId"
  hostname         = "yourhostname"
}
```

Reserve an internal ip address by adding the **google_compute_address** block to your Terraform file.

```
resource "google_compute_address" "alias-ip" {
  name = "${local.hostname}-alias-ip"
  region = "us-central1"
  address_type = "INTERNAL"
  subnetwork = local.subnetwork
}
```

Inside your existing compute instance block, add the **alias_ip_range** to the network interface block.

```
  network_interface {
    network    = local.network
    subnetwork = local.subnetwork
    alias_ip_range {
      ip_cidr_range = google_compute_address.alias-ip.address
    }    
  }
```

The script will reserve an internal ip address and attach it the vm as an alias ip.
