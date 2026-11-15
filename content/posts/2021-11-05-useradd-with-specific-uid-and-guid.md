---
title: 'useradd with specific uid and guid'
author: ulysses

date: 2021-11-05
slug: useradd-with-specific-uid-and-guid
draft: false
---

Here’s the command to create a Linux user with a specific user id and group id.

```
sudo groupadd -r -g 1234567 username
sudo useradd -r -u 1234567 -g 1234567 -m -d /home/username -s /bin/bash nexus -c "my new account"
```