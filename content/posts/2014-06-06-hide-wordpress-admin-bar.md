---
title: 'hide wordpress admin bar'
author: ulysses

date: 2014-06-06
slug: hide-wordpress-admin-bar
draft: false
---

There are reasons why you want to hide the Admin Bar from your users. If users don’t have edit rights, then there’s really no use for an Admin bar. Another reason is if the account is shared with others, you don’t want users to reset the password. There are ample reasons why you want to hide the Admin bar.

Here’s the code:

```
if (!current_user_can(‘edit_posts’)) {
  show_admin_bar(false);
}
```

Here’s another:

```
function my_function_admin_bar(){ return false; }
add_filter( 'show_admin_bar' , 'my_function_admin_bar');
```

Here’s another for users that can’t manage options:

```
if ( ! current_user_can( 'manage_options' ) ) {
  show_admin_bar( false );
}
```

And one more for good measure:

```
add_action('set_current_user', 'csstricks_hide_admin_bar');
function csstricks_hide_admin_bar() {
  if (current_user_can('edit_posts')) {
    show_admin_bar(false);
  }
}
```