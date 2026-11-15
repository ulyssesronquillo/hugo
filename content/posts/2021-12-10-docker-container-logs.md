---
title: 'docker container logs'
author: ulysses

date: 2021-12-10
slug: docker-container-logs
draft: false
---

How to check Docker container logs. Look for the container ID.

```
$ docker ps -a
3e2c1193915f
```

To view the logs for the container.

```
docker logs 3e2c1193915f
# or
docker container logs 3e2c1193915f
```