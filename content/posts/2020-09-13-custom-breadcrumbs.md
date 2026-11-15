---
title: 'custom breadcrumbs'
author: ulysses

date: 2020-09-13
slug: custom-breadcrumbs
draft: false
---

I’ve customized my breadcrumbs. Add code to functions.php.

```
add_filter('genesis_breadcrumb_args', 'customize_breadcrumbs');
function customize_breadcrumbs($args) {
    $args['labels']['prefix'] = 'Home';
    $args['home'] = '';
    $args['sep'] = '/';
    return $args;
}
```

Now it doesn’t say Home/Home on the front page.