---
title: 'install latest terraform via homebrew'
author: ulysses

date: 2023-10-27
slug: install-latest-terraform-via-homebrew
draft: false
---

As of this writing, the latest Terraform version supported by Homebrew is version 1.5.7. It’s a bit outdated considering the latest Terraform version is 1.6.2. To force Homebrew to install the latest version of Terraform, run the following commands from your MacOS Terminal. But prior to that, check your version first.

Check current version

```
$ terraform --version
Terraform v1.5.7
on darwin_amd64
```

Upgrade Terraform

```
$ brew tap hashicorp/tap
$ brew install hashicorp/tap/terraform
```

Check version again

```
$ terraform --version
Terraform v1.6.2
on darwin_amd64
```

That’s it.