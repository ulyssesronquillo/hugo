---
title: 'laravel 5.1 with forge'
author: ulysses

date: 2015-06-14
slug: laravel-5-1-with-forge
draft: false
---

Laravel 5.1 was released in June 9, 2015. So, I updated my development environment with version 5.1 and updated it to GitHub. From there, I spun a server via Forge at Digital Ocean. Then, I deployed my development repository via GitHub.

However, I faced two issues:

1. I was getting an error saying that there is not enough memory. The simple fix is to do a **composer update** in your dev environment and then upload your changes to GitHub. If you have automatic deploy turned on, then the changes will be updated on the server.
2. The other error was a missing app key. You can fix this by simply running **artisan key:generate** on the server. You must have a .env file on the Laravel directory. I believe it’s under /home/forge/default. You can create one or copy the .env.example.

Hopefully, I save you some time with troubleshooting if you run into these issues.