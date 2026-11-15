---
title: 'viewable by admin only'
author: ulysses

date: 2016-08-08
slug: viewable-by-admin-only
draft: false
---

This article will show you how to make a WordPress Page viewable by the admin only. This is really quite handy if you’re creating a custom WordPress Template. You can make certain parts or the entire page viewable by the admin only by placing the code below in your WordPress Page Template.

```
if ( current_user_can( 'manage_options' ) ) {
    // display text here for user with admin privilege
} else {
    // display text here for user without admin privilege
}
```

There has been some confusion whether to use [is_admin()](https://codex.wordpress.org/Function_Reference/is_admin) instead of [current_user_can(‘manage_options’)](https://codex.wordpress.org/Function_Reference/current_user_can). is_admin() is a conditional to check if the user is in the Dashboard or in the Administration Panel. It’s just a boolean conditional that will return true if the URL being accessed is in the admin section.

```
if ( is_admin() ) {
    // returns true that user is in the admin panel
} else {
    // returns false if otherwise
}
```

It’s best to use current\_user\_can(‘manage\_options’) when checking if user is an admin.