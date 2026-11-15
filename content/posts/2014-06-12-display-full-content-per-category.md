---
title: 'display full content per category'
author: ulysses

date: 2014-06-12
slug: display-full-content-per-category
draft: false
---

By the default, the Genesis child theme called Outreach Pro displays categories posts as excerpts. If you want to display the full content on just one category, [Sridhar Katakam](http://sridharkatakam.com/author/sridhar/) talks about it in his blog post. I changed the function names to fit my own, so here’s my own version of the code:

```
// display full content on blog category
add_action( 'genesis_before_loop', 'urr_full_content_specific_category' );
 
function urr_full_content_specific_category() {
  if (is_category('blog')) {
		remove_action( 'genesis_entry_content', 'genesis_do_post_content' );
		add_action( 'genesis_entry_content', 'urr_do_post_content' );
	}
}
function urr_do_post_content() {
	the_content();
}
```