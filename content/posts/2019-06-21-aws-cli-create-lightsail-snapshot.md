---
title: 'aws cli create lightsail snapshot'
author: ulysses

date: 2019-06-21
slug: aws-cli-create-lightsail-snapshot
draft: false
---

Here’s the AWS CLI for creating a LightSail snapshot.

```
aws lightsail create-instance-snapshot \
--instance-snapshot-name test-snapshot \
--instance-name your-server
```

Here’s how to delete a snapshot.

```
aws lightsail delete-instance-snapshot \
--instance-snapshot-name test-snapshot
```