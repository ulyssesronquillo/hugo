---
title: 'install docker on ubuntu 20.04 lts'
author: ulysses

date: 2021-01-18
slug: install-docker-on-ubuntu-20-04-lts
draft: false
---

Here’s the script how to install Docker on Ubuntu 20.04 LTS.

```
#!/bin/bash
sudo apt-get update
# install dependencies
sudo apt-get -y install apt-transport-https ca-certificates curl software-properties-common
# add the gpg key for docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
# add the repository in the Linux mint 20
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(. /etc/os-release; echo "$UBUNTU_CODENAME") stable"
sudo apt-get update
# install docker e docker-compose
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(. /etc/os-release; echo "$UBUNTU_CODENAME") stable"
sudo apt-get -y install docker-ce docker-compose
# add the user system to sudo group, no sudo command
sudo usermod -aG docker $USER
# prints docker version =)
docker --version
```