---
title: 'rebuild docker containers'
author: ulysses

date: 2021-12-12
slug: rebuild-docker-containers
draft: false
---

How to rebuild your application from scratch using Docker.

```
#!/bin/bash
docker-compose down -v
docker rmi $(docker images -a -q)
docker-compose up -d
docker-compose restart -t 10
```

Steps

- Purge the containers.
- Delete docker images.
- Reinitiate docker.
- Restart docker.