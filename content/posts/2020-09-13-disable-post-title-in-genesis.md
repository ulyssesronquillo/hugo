---
title: 'disable post title in genesis'
author: ulysses

date: 2020-09-13
slug: disable-post-title-in-genesis
draft: false
---

Here’s how to disable the post title in Genesis WordPress themes. Add code in themes.php.

```
add_filter( 'genesis_link_post_title', '__return_false' );
```