---
title: 'docker stop and remove all'
author: ulysses

date: 2019-07-04
slug: docker-stop-and-remove-all
draft: false
---

Here’s the command to stop and remove all Docker containers.

```
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```