---
title: 'lightsail upstream error 515'
author: ulysses

date: 2020-07-06
slug: lightsail-upstream-error-515
draft: false
---

If you use LightSail, AWS provides an easy way for you to connect to LightSail instances via Web SSH. I normally use a terminal (ssh client) to connect to LightSail instances, but using Web SSH is very convenient. If you try to do an OS upgrade, for example from Ubuntu 18.04 LTS to Ubuntu 20.04 LTS, you will break Web SSH. AWS has added a special Web SSH configuration on LightSail base images. The error you’ll get is “Upstream Error 515.” The only way to fix this is to get AWS Support to help you apply the fix. It’s not a make or break it deal, but it can be a nuisance if you prefer to use AWS Web SSH instead of a terminal. If you need a more secure SSH connection, consider uploading your ssh-key to the server, and disable password login.

![webssh](https://uly.me/wp-content/uploads/2020/07/webssh.png)