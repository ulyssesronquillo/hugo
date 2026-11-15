---
title: 'display last 50 posts in archive page'
author: ulysses

date: 2019-09-08
slug: display-last-50-posts-in-archive-page
draft: false
---

Here’s the code to add to your archive template, e.g. archives.php.

Last 50 Posts:

```
wp_get_archives( array( 
	'type' =?>
 'postbypost', 'limit' =&gt; 50, 'format' =&gt; '', 'before' =&gt; '- ', 'after' =&gt; '
' )); ?>
```