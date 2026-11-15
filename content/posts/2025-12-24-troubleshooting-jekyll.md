---
author: ulysses
title: 'troubleshooting jekyll'
date: 2025-12-24
slug: troubleshooting-jekyll
draft: false
---
If you find yourself scratching your head as to why your Jekyll site is not working, pay attention to the errors when you run 'build.'

Most likely the errors you see will give you clues to what's going on during the rebuild. In my case it was a simple CSS error.

It is surprising that a small syntax CSS error can bring down Jekyll. 

Perform the following steps to troubleshoot your Jekyll site.

(1) Check if docker container is running. If it's restarting every 5 seconds, then there's definitely a problem.

```
docker ps -a
```

(2) Stop the container.

```
docker-compose stop
```

(3) Rebuild Jekyll.

```
docker-compose up --build
```

(4) Check for errors. They are usually highlighted in red.

(5) Once you fixed the errors, restart Jekyll.

```
docker stop ulyme_jekyll_1
docker rm ulyme_jekyll_1
docker-compose up -d
```

Hopefully, you'll find this helpful.
