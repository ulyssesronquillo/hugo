---
title: 'change wordpress password'
author: ulysses

date: 2016-07-18
slug: change-wordpress-password
draft: false
---

One of the worst things that could happen to your blog is losing your login credentials. It’s a rare event, but it does happen occasionally. This is particularly true if you run hundreds of blogs and websites. Keeping track of all usernames and passwords can be a bit of a challenge.

If you have forgotten your WordPress password, you can quickly recover it, by using the “Lost your password” link underneath the login form. In my case, WordPress mail was not working. So, not only I can’t remember my password, but I also can’t send out lost passwords via email.

Thankfully, I had access to PHPMyadmin, a MySQL database administration tool.

Log in to PHPMyadmin. Access the WordPress database and look for the wp\_users table. Edit the admin user and change the “user\_pass” field. The WordPress password field uses the MD5 encryption instead of being in the clear.

![password](http://uly.me/wp-content/uploads/2016/07/password.png)

Save your changes. Log in to WordPress.