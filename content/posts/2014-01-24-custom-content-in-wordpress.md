---
title: 'custom content in wordpress'
author: ulysses

date: 2014-01-24
slug: custom-content-in-wordpress
draft: false
---

There are some instances where you might need to alter or customize the content of a WordPress post. You could be working on a custom post type with a few extra meta box fields, and you simply want to display them on a template. So, instead of editing the WordPress theme files, you can simply customize the WordPress content if it’s a certain post type. Otherwise, the content remains the same if it’s a regular post or page.

Show me! In this example, we will filter the WordPress content called the\_content by passing a custom function to it. The custom function will pass the content and checks to see if the post type is equal to ‘books.’ If the post type is equal to ‘books’, it will prepend a paragraph saying, ‘Hello Bookworms!!!’ before the content. If the post type is not equal to ‘books’, it will simply return the original content.

Here’s the Code

```
function urr_filter_content($content) {
  $format = get_post_type( get_the_ID() );
  if ( $format == 'books' ) : // your custom post-type
    $new_content  = '<p>Hello Bookworms!!!</p>';
    // add your custom post type meta 
    $new_content  .= '<p>Writer: ' . get_post_meta( get_the_ID(), 'books_writer', true) . '</p>';
  endif;
  $content = $new_content . $content;
  return $content;
}
add_filter('the_content', 'urr_filter_content');
```

There could be numerous reasons why you want to filter the content. Here’s just a few.

- Custom format based on ‘post type’ or ‘post format’
- Adding image, audio and video embeds to your content
- Adding special divs to your content
- Drop Caps
- An author byline
- Adding a widget area

In most cases, content remains undisturbed. But, there might be some crazy instance where you may have to alter it. The function above shows you how you can filter and alter your WordPress content. If you have questions, just leave me a comment!