---
title: 'aws rds patching'
author: ulysses

date: 2018-07-15
slug: aws-rds-patching
draft: false
---

RDS is a managed service by AWS. Patching is performed infrequently. Sometimes, it takes a few months. AWS performs these updates during the maintenance period. If no maintenance period was specified during DB creation, it will be assigned a default period. When patching is performed, AWS may need to stop and reboot your RDS instance right after patches are applied. To avoid potential downtime, make sure your RDS instances are configured in a Multi-AZ environment. Patching will be applied on each RDS instance separately, therefore avoiding downtime for your application.