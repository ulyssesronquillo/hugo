---
title: 'install docker on amazon linux 2'
author: ulysses

date: 2021-12-11
slug: install-docker-on-amazon-linux-2
draft: false
---

Steps how to install Docker and Docker Compose on Amazon Linux 2.

Install Docker

```
$ sudo amazon-linux-extras install docker
$ sudo service docker start
$ sudo usermod -a -G docker ec2-user
```

Start at boot.

```
$ sudo chkconfig docker on
```

Install git (optional).

```
$ sudo yum install -y git
```

Install Docker Compose

```
$ sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) \
-o /usr/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose 
```

Check

```
docker --version
docker-compose --version
```