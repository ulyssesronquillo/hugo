---
title: 'getting to know bloginfo'
author: ulysses

date: 2015-07-08
slug: getting-to-know-bloginfo
draft: false
---

Bloginfo is a WordPress function that you can use on WordPress templates to display a number of things such as the home page, the blog description, the main feed, comments feed, admin email address, template directory, site url, pingback url, etc. You can display bloginfo via PHP just like this:

```
<?php bloginfo('url'); ??>
```

Assuming the blog’s home page is located at http://example.com/home, here’s a list of options.

```
admin_email          = admin@example.com
atom_url             = http://www.example.com/home/feed/atom
charset              = UTF-8
comments_atom_url    = http://www.example.com/home/comments/feed/atom
comments_rss2_url    = http://www.example.com/home/comments/feed
description          = Just another WordPress blog
home                 = http://www.example.com/home (DEPRECATED! use url option instead)
html_type            = text/html
language             = en-US
name                 = Testpilot
pingback_url         = http://www.example.com/home/wp/xmlrpc.php
rdf_url              = http://www.example.com/home/feed/rdf
rss2_url             = http://www.example.com/home/feed
rss_url              = http://www.example.com/home/feed/rss
siteurl              = http://www.example.com/home (DEPRECATED! use url option instead)
stylesheet_directory = http://www.example.com/home/wp/wp-content/themes/largo
stylesheet_url       = http://www.example.com/home/wp/wp-content/themes/largo/style.css
template_directory   = http://www.example.com/home/wp/wp-content/themes/largo
template_url         = http://www.example.com/home/wp/wp-content/themes/largo
text_direction       = ltr
url                  = http://www.example.com/home
version              = 3.5
wpurl                = http://www.example.com/home/wp
```

As mentioned previously, you can use the bloginfo function anywhere within your WordPress templates.