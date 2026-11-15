---
title: 'aws sdk load config'
author: ulysses

date: 2022-02-14
slug: aws-sdk-load-config
draft: false
---

Occasionally I was getting this random error when running Terraform.

```
╷
│ Error: error configuring Terraform AWS Provider: no valid credential sources for Terraform AWS Provider found.
│ 
│ Please see https://registry.terraform.io/providers/hashicorp/aws
│ for more information about providing credentials.
│ 
│ Error: RequestError: send request failed
│ caused by: Post "https://sts.amazonaws.com/": read tcp xx.xx.xx.xx:59422->xx.xx.xx.xx:443: read: connection reset by peer
│ 
│ 
│   with provider["registry.terraform.io/hashicorp/aws"],
│   on main.tf line 10, in provider "aws":
│   10: provider "aws" {
```

Here’s the fix. Place this in your ~/.bash\_profile.

```
export AWS_SDK_LOAD_CONFIG=1
```

This forces Terraform to use both config and credentials file.