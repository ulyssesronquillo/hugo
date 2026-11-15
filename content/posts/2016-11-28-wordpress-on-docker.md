---
title: 'wordpress on docker'
author: ulysses

date: 2016-11-28
slug: wordpress-on-docker
draft: false
---

WordPress is a content management system for running blogs or websites. Meanwhile, Docker is a software container platform for building, shipping and running applications or utilities. Since there are thousands of Docker images already built, installing an application such as WordPress is fairly easy. In this article, I will show you how to install WordPress, MySQL, PHPMyadmin in a Docker environment. First things first, install Docker. Docker is agnostic, meaning it really doesn’t matter what platform you use, whether you’re on Windows, Linux or the Mac. Download Docker [Docker](https://www.docker.com/products/overview). Install.

Create A Project Folder

```
$ mkdir wordpress
$ cd wordpress
```

Create a Docker Compose file

The docker file for composing an image is called docker-compose.yml. It’s a YAML file that contains instructions on what to do and apps to use.

```
$ nano docker-compose.yml
```

Type in the following configuration in the YAML file. In this example, I’m telling docker to install WordPress, MySQL and PHPMyAdmin and using the following TCP ports, credentials, and volumes.

```
wordpress:
  image: wordpress
  links:
    - wordpress_db:mysql
  ports:
    - 8080:80
  volumes:
    - ~/Docker/wordpress/html:/var/www/html
wordpress_db:
  image: mariadb
  environment:
    MYSQL_ROOT_PASSWORD: password
phpmyadmin:
  image: corbinu/docker-phpmyadmin
  links:
    - wordpress_db:mysql
  ports:
    - 8181:80
  environment:
    MYSQL_USERNAME: root
    MYSQL_ROOT_PASSWORD: password
```

Run Docker Compose

```
$ docker-compose up -d
```

The installation may take anywhere from 5-10 mins or longer. So, grab a cup of coffee.

Access WordPress

Once installed, open up your browser and access WordPress and PHPMyadmin

```
http://localhost:8080
http://localhost:8181
```

You can access the WordPress files from your project’s “wordpress/html” directory.

![wp-docker](http://uly.me/wp-content/uploads/2016/11/wp-docker-1024x788.png)

That’s it.