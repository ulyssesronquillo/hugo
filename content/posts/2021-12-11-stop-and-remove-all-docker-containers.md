---
title: 'stop and remove all docker containers'
author: ulysses

date: 2021-12-11
slug: stop-and-remove-all-docker-containers
draft: false
---

How to stop and remove all Docker containers.

Stop all containers

```
$ docker kill $(docker ps -q)
```

Remove all containers

```
$ docker rm $(docker ps -a -q)
```

Delete all docker images

```
$ docker rmi $(docker images -q)
```