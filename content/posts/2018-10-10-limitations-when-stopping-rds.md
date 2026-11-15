---
title: 'limitations when stopping rds'
author: ulysses

date: 2018-10-10
slug: limitations-when-stopping-rds
draft: false
---

There are several cases where there will be a need to stop a RDS instance. It could be due to testing, development activity, or simply to save money. Whatever the reasons may be, you’ll need to be aware of the limitations when stopping RDS instances. Here are several cases where it may become an issue.

- You can’t stop a DB instance that has a Read Replica, or that is a Read Replica.
- You can’t stop a DB instance that is in a Multi-AZ deployment.
- You can’t stop a DB instance that uses Microsoft SQL Server Mirroring.
- You can’t modify a stopped DB instance.
- You can’t delete an option group that is associated with a stopped DB instance.
- You can’t delete a DB parameter group that is associated with a stopped DB instance.