---
title: 'multisite to single site'
author: ulysses

date: 2017-05-10
slug: multisite-to-single-site
draft: false
---

I have a couple of WordPress blogs that are running multisite. I decided I don’t need the other blogs. So, I converted both sites to the standard or single WordPress site. The good news is that there’s no need to reinstall WordPress. It requires just a simple edit of a couple of WordPress files. The conversion was not as bad as I initially thought. Just follow the steps below.

5 Easy Steps

1. Back up your database — just in case.
2. Delete the blogs you don’t want.
3. Edit wp-config.php.
4. Edit .htaccess.
5. Clean up your database.

1. Backing up your database — just in case. You can use several tools for backing up your blogs. You can use PHPMyAdmin or a WordPress backup plugin. You can also use the WordPress Export feature to save the blog in XML format in case you want to restore it in the future.

2. Delete the blogs you don’t want – Go to All blogs in the WordPress Dashboard. If you have multiple blogs, it will be listed here. Delete the ones you don’t want.

3. Edit wp-config.php. Remove the Multisite entries in wp-config.php.

```
define( 'MULTISITE', true );
define( 'SUBDOMAIN_INSTALL', false );
$base = '/wordpress/';
define( 'DOMAIN_CURRENT_SITE', 'localhost' );
define( 'PATH_CURRENT_SITE', '/wordpress/' );
define( 'SITE_ID_CURRENT_SITE', 1 );
define( 'BLOG_ID_CURRENT_SITE', 1 );
```

4. Change your .htaccess to the standard WordPress configuration.

```
# BEGIN WordPress
<ifmodule mod_rewrite.c="">
RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
</ifmodule>
# END WordPress
```

5. Finally, remove the database tables that are no longer needed.

```
wp_blogs
wp_blog_versions
wp_registration_log
wp_signups
wp_site
wp_sitemeta
```