---
author: ulysses
title: 'nodejs web server docker'
date: 2025-11-17
slug: nodejs-web-server-docker
draft: false
---
Create a node.js web server running on docker.

create an index.js.

```
// index.js
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('Hello from Node.js in Docker!');
});

app.listen(port, () => {
  console.log(`App listening at http://localhost:${port}`);
});
```

install node 

```
sudo apt install npm
npm init -y
npm install express
```

create a Dockerfile

```
# Dockerfile
FROM node:alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "index.js"]
```

create docker-compose.yml file

```
# docker-compose.yml
version: '3.8'
services:
  web:
    build: .
    ports:
      - "3000:3000"
    volumes:
      - .:/app
    environment:
      NODE_ENV: development # Or production
```

finally, start the node.js web application in a docker container

```
docker-compose up -d
```
