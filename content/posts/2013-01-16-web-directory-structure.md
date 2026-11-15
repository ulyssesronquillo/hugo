---
title: 'web directory structure'
author: ulysses

date: 2013-01-16
slug: web-directory-structure
draft: false
---

If you’re a system administrator or web developer with root privileges, chances are, you probably have complete control of your web server, including root privileges. That’s a good thing. You can setup the server anyway you want. If you’re starting out to build out a new web server, some of the questions that you may have is, what’s the proper or correct way of creating a web directory structure on your web server.

The answer is, there is really no correct way. There’s no magic bullet configuration. You do have complete freedom to setup your server anyway you want. But, if you want to make it easy for yourself, you should probably look for a well-established standard, or some proven way in structuring web directories.

The following is my “suggestion” after my extensive experience with countless web servers over the years. I called it “suggestion” because it’s by no means the holy grail, but the concept has served me well over the years. You may not necessarily agree with my format, or you may have something similar, or something completely different than mine. Nevertheless, my setup is simple and it works.

Most web servers nowadays can host multiple domains. I will make an assumption that you will be running multiple domains on your web server. A typical structure would be something similar to the one below. Each domain has its own subdirectory.

```
/var/www/domain1.com/  
/var/www/domain2.com/  
/var/www/domain3.com/
```

If you have a static website, the file structure would be something like this.

```
/var/wwww/domain.com/index.html
```

If you have a dynamic website, you have something similar to this.

```
/var/www/domain.com/index.php  
/var/www/domain.com/wp-content/
```

By the way, “wp-content” is a WordPress folder where templates and plugins reside. The above structure is serviceable, but if you ever find yourself working with PHP Frameworks such as CodeIgniter, Zend Frameworks, or even Ruby on Rails, there are some additional directories and programs that you would want to hide from the public for security reasons. Here are some directories using the CodeIgniter example.

```
/var/www/domain.com/index.php  
/var/www/domain.com/application/  
/var/www/domain.com/system/
```

To make your application secure, we need to move the “application” and the “system” folders above the web root folder. With the current setup, this is where you begin to have some issues. Where exactly do we put your “application” and “system” folders if multiple domains need them. So, here’s my suggestion. We need to create a “www” folder under each domain. We will make the “www” folder the web root folder. The setup would look something like this.

```
/var/www/domain1.com/www/  
/var/www/domain2.com/www/
```

Now, that we have the “www” folder created, we can then place the “application” and “system” folders on their own directory above the web root. The setup would look something like this.

```
/var/www/domain1.com/www/index.php  
/var/www/domain1.com/application/  
/var/www/domain1.com/system/  
/var/www/domain2.com/www/index.php  
/var/www/domain2.com/application/  
/var/www/domain2.com/system/
```

So, the setup above is ideal for placing folders above the web root folder if you want a more secure application. At the same time, these folders are still under each domain. So, this is the web structure that I have implemented over the years. If there’s a better way of doing this, I would like to hear about it.