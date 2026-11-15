---
author: ulysses
title: 'jekyll build'
date: 2025-12-06
slug: jekyll-build
draft: false
---
If there's a need to rebuild Jekyll running in a container, you must do the following.

1. stop the current container
```
cd ~/docker/ulyme
$ docker-compose down
```
2. once stopped, go ahead and rebuild
```
docker-compose up --build
```
3. once site is rebuilt, stop and delete it the updated container
```
$ docker stop ulyme_jekyll_1
$ docker rm ulyme_jekyll_1
```
4. finally, start a new docker container that's running it the background
```
docker-compose up -d
```

This is a requirement if you made major changes to your site such as adding or removing plugins, etc.
