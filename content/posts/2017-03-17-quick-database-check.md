---
title: 'quick database check'
author: ulysses

date: 2017-03-17
slug: quick-database-check
draft: false
---

Here’s a quick PHP script to check if your web server can connect to your MySQL database. It’s a neat little script if you don’t have any application installed yet, and you just want to see if your web server setup can quickly connect to the database. All you have to do is create a new file called connect.php, and place the following code inside. Just change the username, password and database. Most likely the hostname will be localhost.

```
$ sudo nano /var/www/html/connect.php
$username = "user";
$password = "password";
$hostname = "hostname";
$database = "database";

$dbhandle = mysql_connect($hostname, $username, $password) or die("Unable to connect to MySQL");
echo "Successfully Connected to the MySQL Database.<br></br>";

$selected = mysql_select_db("$dbname", $dbhandle) or die("Could not select database");
echo "Successfully Connected to Database called: $database";
```

It’s also available on my Github [gist](https://gist.github.com/ulyssesr/2085bc6d1a97e3b4d21688a35b112646).