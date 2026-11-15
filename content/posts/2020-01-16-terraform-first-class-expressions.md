---
title: 'terraform first class expressions'
author: ulysses

date: 2020-01-16
slug: terraform-first-class-expressions
draft: false
---

If you were running the older versions of Terraform, with release 0.12 and higher, there will be certain parts of your script that are no longer supported. Terraform uses expressions for dynamic configuration and dependencies. First-class expressions enable variables and operations to be performed outside of strings. In Terraform 0.11 and earlier all expressions were required to be part of interpolations in existing strings, such as “${var.foo}.

In Terraform 0.11.

```
resource "aws_instance" "example" {
  ami           = "${var.ami}"
  instance_type = "${var.instance_type}"
}
```

In Terraform 0.12.

```
resource "aws_instance" "example" {
  ami           = var.ami
  instance_type = var.instance_type
}
```

Gone are quotes, curly braces and the $ sign.