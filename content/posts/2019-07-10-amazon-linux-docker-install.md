---
title: 'amazon linux docker install'
author: ulysses

date: 2019-07-10
slug: amazon-linux-docker-install
draft: false
---

Here’s the installation of Docker for the original Amazon Linux.

```
# To install docker
sudo yum install docker
sudo service docker start
# Validate it's working
docker --version
docker run hello-world
docker ps -a
docker image ls
```