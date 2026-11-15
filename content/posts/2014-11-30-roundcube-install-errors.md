---
title: 'roundcube install errors'
author: ulysses

date: 2014-11-30
slug: roundcube-install-errors
draft: false
---

I ran into several issues with the Roundcube installation on Ubuntu. Roundcube is a browser-based IMAP client that you can install on your server. It’s available from the Ubuntu repository to install. You run this command from the Terminal to install.

Roundcube Install

```
sudo apt-get install roundcube roundcube-mysql
```

However, I ran into some issues. The two Roundcube configuration files are main.inc.php and debian.db.php. Both are located in the /etc/roundcube directory. If you have problems receiving or sending mails, it’s worth to take a look at your IMAP and SMTP settings on your /etc/roundcube/main.inc.php file.

Edit the /etc/roundcube/main.inc.php file. Use your own server settings.

```
sudo nano /etc/roundcube/main.inc.php
```

IMAP and SMTP Settings

```
// IMAP server
$rcmail_config['default_host'] = array("ssl://imap.yourmailserver.com");

// TCP port used for IMAP connections
$rcmail_config['default_port'] = 993;

// SMTP server
$rcmail_config['smtp_server'] = 'ssl://smtp.yourmailserver.com';

// SMTP port
$rcmail_config['smtp_port'] = 465;

// SMTP username (if required) use %u as the username
$rcmail_config['smtp_user'] = '%u';

// SMTP password (if required) use %p as the password
$rcmail_config['smtp_pass'] = '%p';
```

Use %u and %p if you have multiple accounts.

Database Settings

Make sure your database credentials are correct.

```
$dbuser='your_username';
$dbpass='your_password';
$basepath='';
$dbname='roundcube';
$dbserver='';
$dbport='';
$dbtype='mysql';
```

Finally, reboot the Apache server for good measure.

```
sudo service apache2 restart
```