---
title: 'add a widget area in wordpress'
author: ulysses

date: 2014-01-20
slug: add-a-widget-area-in-wordpress
draft: false
---

Customizing your WordPress theme gives you total control of the look and feel of your website. One of the ways of customizing your theme is to add a “widget area” that you can place anywhere on your theme’s template. The first step in adding a widget area is to edit your theme’s functions.php file. In this example, we are going to add a widget area just underneath the header and before the main post loop.

Open your theme’s functions.php and add the following lines.

```
if (function_exists('register_sidebar')) {
  register_sidebar(array(
  'name' => 'Below Header Widgets',
  'id' => 'below-header-widgets',
  'description' => 'The below the header widgets of your website.',
  'before_widget' => '<div class="widget %2$s" id="%1$s">',
  'after_widget' => '</div>',
  'before_title' => '<h2>',
  'after_title' => '</h2>'
));
}
```

Save the file. Now that we added a new widget area to the functions.php file, we can now add this bit of code to our template. In this example, we will add the new widget area to our template’s header.php file. Notice the name ‘Below Header Widgets’ matches the ‘name’ in the code above.

```
<div class="below-header">
 <ul>
  <?php if (!function_exists('dynamic_sidebar') || !dynamic_sidebar('Below Header Widgets')) : endif; ??>
 </ul>
</div>
```

Now go to your Admin Dashboard > Appearance > Widgets menu. You should now see the new widget area in your theme. The last thing you’ll need to do is style your new widget area. If you want the text to display in inline, we can add the following CSS styles.

```
.below-header ul li { float:left; display:inline; padding-right:10px; }
```

The CSS above floats and displays each widget and its content inline, as well as add a 10px right padding.