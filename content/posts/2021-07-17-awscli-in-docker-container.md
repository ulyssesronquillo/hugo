---
title: 'awscli in docker container'
author: ulysses

date: 2021-07-17
slug: awscli-in-docker-container
draft: false
---

This will download the latest awscli and run it in a container.

A new container will be built every time the command is run.

Your current credentials in ~/.aws will be used.

```
docker run --rm -it -v ~/.aws:/root/.aws amazon/aws-cli:latest
```

Create an alias for convenience.

```
alias aws='docker run --rm -ti -v ~/.aws:/root/.aws -v $(pwd):/aws amazon/aws-cli'
```

You can now run any aws cli after.

```
aws --version
aws-cli/2.2.20 Python/3.8.8 Linux/5.4.0-66-generic docker/x86_64.amzn.2 prompt/off
```