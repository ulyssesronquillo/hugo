---
author: ulysses
title: 'terraform local variables'
date: 2024-01-08
slug: terraform-local-variables
draft: false
---

If you find yourself entering the same value multiple times in your Terraform script, you can save yourself some time by declaring local variables inside a locals block and reuse them throughout your script or module.

Here's a locals block.

```
locals {
  project          = "your_project_id"
  hostname         = "your_hostname"
  machine_image    = "your_machine_image"
}
```

Once the local variables are declared, you can reuse them anywhere and as many times as you want in your Terraform script or module.

```
provider "google" {
  project = local.project
}

data "google_compute_image" "boot-image" {
  family  = local.machine_image
  project = local.project
}

resource "google_compute_instance" "instance" {
  name         = local.hostname
  machine_type = local.machine_type
  ...
}
```

Local variables are helpful if you're repeating the same values throughout your configuration. You can make a change in one place and it will apply to multiple locations. The only gotcha is to not overdo it, because it will make your code harder to read. Use it in moderation.
