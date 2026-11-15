---
title: 'the in_category function'
author: ulysses

date: 2017-01-08
slug: the-in_category-function
draft: false
---

If you’re looking for a simple way to detect if a WordPress page belongs to a certain category, you can use a WordPress function called in\_category(). In this example code below, the script will detect if a post belongs to the “news” category. If it does, it will send an output to the WordPress header. If it isn’t, it will send an alternate output.

```
function urr_add_to_header() 
{
  if ( in_category( 'news' )) 
  {
    echo '<script>Add your news Javascript here</script>';
  } else {
    echo '<script>Add your alternate Javascript here</script>';
  }
}
add_action( 'wp_head', 'urr_add_to_header', 100 );
```

It’s a simple function that has many uses. You can accomplish quite a bit with the in_category() function along with a few WordPress hooks.