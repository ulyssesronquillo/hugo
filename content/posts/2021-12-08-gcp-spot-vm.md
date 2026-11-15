---
title: 'gcp spot vm'
author: ulysses

date: 2021-12-08
slug: gcp-spot-vm
draft: false
---

Spot VMs are preemtible, they can be reclaimed by the Cloud provider.

However you can get deep discounts using them.

Launch a spot instance in GCP using Terraform.

```
provider "google" {
  project = "airy-totality-151318"
  zone    = "us-central1-c"
}

resource "google_compute_instance" "test" {
  name         = "test"
  machine_type = "e2-micro"

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  scheduling {
    preemptible       = true
    automatic_restart = false
  }

  network_interface {
    network = "default"
    access_config {
    }
  }
}
```