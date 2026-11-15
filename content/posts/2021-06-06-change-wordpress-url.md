---
title: 'change wordpress url'
author: ulysses

date: 2021-06-06
slug: change-wordpress-url
draft: false
---

There are multiple ways to change URL in WordPress.

Here’s one via wp-config.php.

```
define( 'WP_HOME', 'http://example.com' );
define( 'WP_SITEURL', 'http://example.com' );
```

If you have a redirect in Apache, comment it out.

```
#Redirect permanent / https://yourdomain.com/
```

This is by far the easiest way to change URL in WordPress.