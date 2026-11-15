---
title: 'create a dummy file'
author: ulysses

date: 2019-02-04
slug: create-a-dummy-file
draft: false
---

Here’s the command to create a dummy file in Linux. This creates a 1GB or a 2GB file. Adjust the count to achieve the file size.

```
# 1GB
dd if=/dev/zero of=/path/to/dummyfile bs=1M count=1024
# 2GB
dd if=/dev/zero of=/path/to/dummyfile bs=1M count=2048
```