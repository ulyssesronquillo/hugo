---
title: 'terraform in a docker container'
author: ulysses

date: 2021-07-17
slug: terraform-in-a-docker-container
draft: false
---

Run Terraform in a Docker container.

```
docker run --rm -it --name terraform -v ~/.aws:/root/.aws -v $(pwd):/workspace -w /workspace hashicorp/terraform:latest
```

Create an alias.

```
alias terraform='docker run --rm -it --name terraform -v ~/.aws:/root/.aws -v $(pwd):/workspace -w /workspace hashicorp/terraform:latest'
```

Run the command

```
terraform --version
Terraform v1.0.2
on linux_amd64
```