---
title: 'wp_query reverse sort'
author: ulysses

date: 2019-03-25
slug: wp_query-reverse-sort
draft: false
---

Here’s how to reverse sort WP\_Query. Order by ID. Reverse sort by ASC intead of DESC.

```
  $args = array (
    'cat' => 8, 
    'year' => $year, 
    'orderby' => 'ID',
    'order' => 'ASC', 
    'posts_per_page' => -1, 
    'paged' => $paged, 
    's' => $searchterm 
  );
  $category_posts = new WP_Query($args);
```