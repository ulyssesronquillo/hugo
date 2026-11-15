---
title: 'install jekyll on amazon linux 2'
author: ulysses

date: 2021-02-02
slug: install-jekyll-on-amazon-linux-2
draft: false
---

Here’s the script to install Jekyll on Amazon Linux 2.

```
#!/bin/bash
sudo hostnamectl set-hostname jekyll
sudo yum update -y
sudo amazon-linux-extras install ruby2.4 -y
sudo yum install ruby ruby-devel -y
sudo yum groupinstall "Development Tools" -y
sudo gem install bundler 
sudo gem install rdoc
sudo gem update --system
sudo gem install jekyll
jekyll new myblog
```

To start the Jekyll server.

```
cd mysite
jekyll build
jekyll serve --host 0.0.0.0
```

Open your browser and point it to the external IP of your instance on port 4000.

```
http://xxx.xxx.xxx.xxx:4000
```

You may to edit your security group to allow ingress 4000 from 0.0.0.0/0.