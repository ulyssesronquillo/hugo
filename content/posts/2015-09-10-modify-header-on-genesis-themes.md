---
title: 'modify header on genesis themes'
author: ulysses

date: 2015-09-10
slug: modify-header-on-genesis-themes
draft: false
---

The Genesis theme is a WordPress theme from StudioPress. I recently worked on a project where there was a need to redirect the URL title to another URL. Essentially, there are two separate WordPress installs on the server, one install had WordPress on the root directory, the other on a sub-directory. The URL title of the WordPress on a sub-directory needed to point to the root directory. So, here’s the fix that you need to add in the functions.php for Genesis themes.

```
//* Modify the header URL - HTML5 Version
add_filter( 'genesis_seo_title', 'child_header_title', 10, 3 );
function child_header_title( $title, $inside, $wrap ) {
    $inside = sprintf( '<a href="http://example.com/" title="%s">%s</a>', esc_attr( get_bloginfo( 'name' ) ), get_bloginfo( 'name' ) );
    return sprintf( '%2$s%1$s>', $wrap, $inside );
}
```

Just add this piece of code to the functions.php file of your Genesis child theme.