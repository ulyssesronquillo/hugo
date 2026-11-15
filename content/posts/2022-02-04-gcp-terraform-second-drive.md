---
title: 'gcp terraform second drive'
author: ulysses

date: 2022-02-04
slug: gcp-terraform-second-drive
draft: false
---

How to add a second drive on GCP Compute Engine using Terraform.

```
provider "google" {
  project = "your-project-id"
  zone    = "us-central1-c"
}

resource "google_compute_disk" "data-drive" {
  name = "data-drive"
  type = "pd-standard"
  zone = "us-central1-c"
  size = "20"
}

resource "google_compute_attached_disk" "attach-data-drive" {
  count    = 1
  disk     = google_compute_disk.data-drive.id
  instance = google_compute_instance.test.id
}

resource "google_compute_instance" "test" {
  name         = "test"
  machine_type = "e2-micro"

  boot_disk {
    initialize_params {
      image = "rocky-linux-cloud/rocky-linux-8"
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