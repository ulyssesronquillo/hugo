---
title: 'terraform gcp firewall'
author: ulysses

date: 2021-06-06
slug: terraform-gcp-firewall
draft: false
---

How to create GCP firewall via Terraform.

Ingress

```
provider "google" {
    project = "project-id"
}
resource "google_compute_firewall" "default" {
    name    = "test-firewall"
    description = "this is a test firewall"
    priority = "1000"
    direction = "INGRESS"
    network = "projects/project-id/regions/us-east1/subnetworks/default"
    target_service_accounts = ["service-account-compute@developer.gserviceaccount.com"]
    source_ranges = ["10.128.0.0/20"]
    allow {
        protocol = "tcp"
        ports    = ["80", "8080", "1000-2000"]
    }
}
```

Egress

```
provider "google" {
    project = "project-id"
}
resource "google_compute_firewall" "default" {
    name    = "test-firewall"
    description = "this is a test firewall"
    priority = "1000"
    direction = "EGRESS"
    network = "projects/project-id/regions/us-east1/subnetworks/default"
    target_service_accounts = ["service-account-compute@developer.gserviceaccount.com"]
    destination_ranges = ["10.128.0.0/20"]
    allow {
        protocol = "tcp"
        ports    = ["80", "8080", "1000-2000"]
    }
}
```

Service account to Service account.

```
provider "google" {
    project = "project-id"
}
resource "google_compute_firewall" "default" {
    name    = "test-firewall"
    description = "this is a test firewall"
    priority = "1000"
    direction = "INGRESS"
    network = "projects/project-id/regions/us-east1/subnetworks/default"
    source_service_accounts = ["source-service-account-compute@developer.gserviceaccount.com"]
    target_service_accounts = ["target-service-account-compute@developer.gserviceaccount.com"]
    source_ranges = ["10.128.0.0/20"]
    allow {
        protocol = "tcp"
        ports    = ["80", "8080", "1000-2000"]
    }
}
```