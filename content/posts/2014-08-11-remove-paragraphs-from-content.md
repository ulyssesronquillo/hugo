---
title: 'remove paragraphs from content'
author: ulysses

date: 2014-08-11
slug: remove-paragraphs-from-content
draft: false
---

Here’s a really easy way on how to remove paragraphs or &lt;p&gt;&lt;/p&gt; from the WordPress content.

In the WordPress loop, look for the code ‘the\_content().’ Add this command just before it:

```
remove_filter ('the_content', 'wpautop');
the_content();
```

That essentially removes all the paragraphs from the WordPress content.