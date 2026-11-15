---
title: wp_enqueue_scripts
author: ulysses

date: 2014-08-15
slug: wp_enqueue_scripts
draft: false
---

There’s a new way to load WordPress stylesheets from within your templates. In the older versions of WordPress, the stylesheets were hard coded on the theme’s header file. The proper way to load your stylesheets is via the functions.php file. Here are the differences.

The old way was:

```
<link href="<?php bloginfo('stylesheet_url'); ?>" media="screen" rel="stylesheet" type="text/css"></link>
```

The new way uses wp\_enqueue\_scripts and the code is placed in functions.php.

```
function sample_theme_scripts() {
	wp_enqueue_style( 'style', get_stylesheet_uri() );
}
add_action( 'wp_enqueue_scripts', 'sample_theme_scripts' );
```

Both codes work, but the latter will give you less headache.

If you use multiple stylesheets and JQuery at the same time, then you can use wp\_enqueue\_scripts to load them all at once. Using wp\_enqueue\_scripts will help you avoid conflicts from loading multiple copies of the same script. For example, you can deregister the standard WordPress JQuery and use your own JQuery version. This method is particularly helpful when you are writing your own plugins, much more so than using it on themes. Nevertheless, it’s good practice to use wp\_enqueue\_scripts to load stylesheets.