---
title: 'wordpress numeric pagination'
author: ulysses

date: 2019-09-08
slug: wordpress-numeric-pagination
draft: false
---

Here’s how to add numeric pagination on your WordPress pages.

Add this code to functions.php.

 ```
function pagination($pages = '', $range = 4) {
  $showitems = ($range * 2)+1;
  global $paged;
  if(empty($paged)) $paged = 1;
  if($pages == '') {
    global $wp_query;
    $pages = $wp_query->max_num_pages;
    if(!$pages) {
      $pages = 1;
    }
  }
  if(1 != $pages) {
    echo '<p></p><div class="pagination"><span>Page' . $paged . ' of  ' . $pages . '</span>   ';
    if($paged > 2 && $paged > $range+1 && $showitems ';
    if($paged > 1 && $showitems ';
    for ($i=1; $i = $paged+$range+1 || $i ' . $i . '' : '<a class="inactive" href="' . get_pagenum_link($i) . '">' . $i . '</a>';
      }
    }
    if ($paged Next >';
    if ($paged Last >>';
    echo '</div>';
  }
}
```

To display, comment out ‘the\_post\_navigation’ function and add the ‘pagination’ function instead in your template files.

 ```
//the_posts_navigation();
pagination();
```

Code courtesy of [webdesignsun](https://www.webdesignsun.com/tech-blog/wordpress-numeric-pagination-without-plugin).