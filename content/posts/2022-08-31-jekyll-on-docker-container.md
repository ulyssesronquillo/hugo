---
title: 'jekyll on docker container'
author: ulysses

date: 2022-08-31
slug: jekyll-on-docker-container
draft: false
---

Here’s how to run Jekyll in a Docker container.

```
mkdir blog
cd blog
docker run -v $(pwd):/site bretfisher/jekyll new .
```
Start jekyll.

```
docker run -p 4000:4000 -v $(pwd):/site bretfisher/jekyll-serve
```

Another option is to use docker compose. Just create a docker-compose.yml file.

```
version: 3.5
services:
  jekyll:
    image: bretfisher/jekyll-serve
    volumes:
      - .:/site
    ports:
      - '4000:4000'
```

Start Jekyll by using docker-compose up. -d means detach or run in the background.

```
cd blog
docker-compose up -d
```

Stop Jekyll.

```
cd blog
docker-compose down
```