---
title: 'gitlab community edition'
author: ulysses

date: 2017-02-07
slug: gitlab-community-edition
draft: false
---

[Git](https://git-scm.com/) is the most popular version control software for managing your code. If you’re looking for the best version control system out there, Git is the pretty much the de-facto standard of version control. Although you can run Git locally without a server, you’ll need some kind of repository to share your code with others.

Enter [Github](http://github.com). Github provide free and paid Git repositories. Github public repositories are free, while private ones require subscription. For $7 dollars a month, you can have up to 5 private repositories. For $50 per month, you can use up to 50 repositories.

If you want to run your own Git repository either on the cloud or on your own private network (it’s more secure this way), then you’ll need to look at Gitlab’s Community Edition (Github.com is proprietary). Gitlab requires that you install their software on a Linux server (I’m using Ubuntu Server).

I tried running Gitlab CE on the cheapest server ($5 per month) I can find at [Digital Ocean](http://digitalocean.com). It works but, it’s painfully slow. I don’t recommend it. The $5 per month server only has 1 CPU core and 512 MB of RAM. I recommend that you go for a system that has 2 CPU cores and 2GB of RAM. This system will cost $20 per month.

By the way, if you don’t want managing your own server, you can simply sign up with Gitlab.com. It’s free! They offer unlimited private and public repositories up to 10GB of disk space per project. Of course, Gitlab has other [products](https://about.gitlab.com/products/). For a paid subscription you can get enterprise support and more advanced features.

Visit [Gitlab](http://gitlab.com) for more details.