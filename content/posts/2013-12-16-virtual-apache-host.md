---
title: 'virtual apache host'
author: ulysses

date: 2013-12-16
slug: virtual-apache-host
draft: false
---

Creating a virtual host in [Apache](http://httpd.apache.org/) allows for multiple domains to be hosted on a single IP address. This is extremely useful in terms of hosting multiple domains on a single host or VPS. As far as I know, you can have an unlimited number of virtual hosts. The only limitation is the system resources in terms of CPU usage, memory and storage. This article will show you how to add Apache virtual hosts in Ubuntu.

Typically, the web root for Apache in Ubuntu is located in /var/www. Instead, we will use a directory under the /home/username directory. So, let’s now create a directory in /home/username/fakedomain.com/. We can achieve this by typing the following:

```
$ mkdir /home/username/fakedomain.com
```

We will give it read and write permissions.

```
$ chmod 755 -R /home/username/fakedomain.com
```

Now, let’s create a new virtual host file.

```
$ sudo touch /etc/apache2/sites-available/fakedomain.com
```

We will add the following configuration.

```
<virtualhost>
ServerAdmin webmaster@localhost
Servername fakedomain.com
ServerAlias www.fakedomain.com
DocumentRoot /home/username/fakedomain.com
</virtualhost>
```

Save the file by pressing Control-O followed by Control-X.

Activate our new host.

```
$ sudo a2ensite fakedomain.com
```

Restart Apache.

```
$ sudo service apache2 restart
```

Edit your hosts file. The first line is for Ubuntu, the second for Mac OS.

```
$ sudo nano /etc/hosts
$ sudo nano /private/etc/hosts
```

Add the fakedomain.com to your hosts file. Substitute the IP address of your host.

```
192.168.0.5  fakedomain.com
```

Save the file by pressing Control-O followed by Control-X.

You can now access fakedomain.com from your browser by typing ‘http://fakedomain.com’ on the address bar.