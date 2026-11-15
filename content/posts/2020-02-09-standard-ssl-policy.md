---
title: 'standard ssl policy'
author: ulysses

date: 2020-02-09
slug: standard-ssl-policy
draft: false
---

Here’s a standard template for SSL Apache found in /etc/apache2/sites-available/default-ssl.conf.

```
<ifmodule mod_ssl.c="">
<virtualhost _default_:443="">
   ServerAdmin your-email@your-domain.com
   ServerName www.yourdomain.com
   ServerName yourdomain.com
   DocumentRoot /var/www/your-domain.com
   ErrorLog /var/www/your-domain.com/log/error.log
   CustomLog /var/www/your-domain.com/log/access.log combined
   <directory>
      Options Indexes FollowSymLinks MultiViews
      AllowOverride All
      Require all granted
   </directory>
   SSLCertificateFile /etc/letsencrypt/live/your-domain.com/fullchain.pem
   SSLCertificateKeyFile /etc/letsencrypt/live/your-domain.com/privkey.pem
   Include /etc/letsencrypt/options-ssl-apache.conf
</virtualhost>
</ifmodule>
```

Enable SSL.

```
# Enable SSL Module
a2enmod ssl
systemctl restart apache2.service
# Enable SSL Apache Config
a2ensite default-ssl
systemctl restart apache2.service
# Alternate way to restart.
service apache2 restart
```