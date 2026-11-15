---
title: 'mysql and access via odbc'
author: ulysses

date: 2013-05-24
slug: mysql-and-access-via-odbc
draft: false
---

A client of mine had a request to connect Microsoft Access to MySQL via an ODBC connector. The MySQL ODBC setup is not very common, but is entirely possible. MySQL does provide an ODBC connector for other database clients. The setup is a bit tricky. Unfortunately, there’s not a lot of information and documentation online for this type of setup. After some trial and error, I got it to work.

First of all, here are some details. The MySQL server runs on Ubuntu 12.04. The ODBC client, MS Access 2010, runs on a Windows 7 machine. Assuming MySQL is already installed, we just need to make sure the MySQL server ODBC library is installed first.

```
sudo apt-get install libmyodbc
```

Now, let’s create an ODBC Data Source. Not sure if this step is required or optional. I did it anyways.

```
sudo nano /etc/odbc.ini
```

Add the following entries:

```
[ODBC Data Sources]
testodbc = MyODBC 5.2.5 Driver DSN

[testodbc]
Driver       = MySQL
Description  = MySQL ODBC 5.2.5 Driver DSN
Server       = localhost
Port         =
User         = user
Password     = password
Database     = test
Option       = 3
Socket       =
```

Let’s secure your MySQL database by answering the following questions.

```
sudo mysql_secure_installation
```

Answer the following questions:

```
Enter current password for root. Enter password.
Change root password? [Y/n] n
Remove anonymous users? [Y/n] Y
Disallow root login remotely? [Y/n] n
Remove test database and access to it? [Y/n] Y
Reload privilege tables now? [Y/n] Y
```

Allow remote login on MySQL

```
# Edit mysql configuration
sudo nano /etc/mysql/my.cnf

# Comment out "skip-networking"
# Add "bind-address = 192.168.0.10"
# Enter your own IP address
$ bind-address = 192.168.0.10
# Save file and exit. 

# Login to MySQL 
$ sudo mysql -u root -p 

# Grant privileges 
mysql> grant all privileges on *.* to 'root'@'%' identified by 'password' with grant option;
mysql> flush privileges;
mysql> exit;

# Restart MySQL
$ sudo /etc/init.d/mysql restart
# Test connection
$ telnet 192.168.0.10 3306
```

Download the latest MySQL ODBC Connector and install.

<http://dev.mysql.com/downloads/connector/odbc/>

Open Microsoft Access

1. Create “**new blank database**.”
2. Select “**External Data**” and click on “**ODBC Database**.”
3. Select “**Link to the data source by creating a link table**.”
4. Create a new DSN
5. Choose “**MySQL 5.2 ODBC Driver**.”
6. Enter IP, Port 3306, Username, Password, and Database.
7. Save DNS for later use.

You should have connected to the MySQL by now.