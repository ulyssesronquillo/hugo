---
title: 'apache dockerfile'
author: ulysses

date: 2019-12-25
slug: apache-dockerfile
draft: false
---

This Docker image contains Apache (httpd), a web server.

Here’s the Dockerfile.

```
FROM httpd:2.4
COPY ./public-html/ /usr/local/apache2/htdocs/
```

Build and run your Docker image.

```
docker build -t my-app .
docker run -dit --name my-running-app -p 8080:80 my-app
```

Visit http://localhost:8080 to view your app.