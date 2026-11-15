---
title: 'wordpress posts revision'
author: ulysses

date: 2020-06-18
slug: wordpress-posts-revision
draft: false
---

How to turn on post revisions in WordPress. Edit wp-config.php.

```
/** WordPress Revisions */
define('WP_POST_REVISIONS', false);
```

Change to:

```
/** WordPress Revisions */
define('WP_POST_REVISIONS', 10);
```

10 is the number of revisions you want to keep.