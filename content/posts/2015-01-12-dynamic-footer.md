---
title: 'dynamic footer'
author: ulysses

date: 2015-01-12
slug: dynamic-footer
draft: false
---

Many web designers use Copyright followed by the current year on the bottom of their websites. It’s usually placed in the footer section of the page. If your site has been around for a while, spanning over several years, you’ll have to update your footer every time a new year comes along. If your site runs on PHP, you can make your footer a little bit more dynamic by using the PHP date function.

For example, you have a footer similar to this.

```
Copyright © 2010 - 2014. All rights reserved. yourdomain.com.
```

The result is:

Copyright © 2010 – 2014. All rights reserved. yourdomain.com.

You can make the current year dynamic by using the PHP date function as displayed below.

```
Copyright © 2010 - <?php echo date('Y'); ??>. All rights reserved. yourdomain.com.
```

Most web hosting services have PHP turned on by default. Even if your website runs only in HTML, you can probably use the PHP date function. If you decide to do it, just make sure to change the file extension from .html to .php. And you’re good to go.