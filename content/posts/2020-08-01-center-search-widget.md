---
title: 'center search widget'
author: ulysses

date: 2020-08-01
slug: center-search-widget
draft: false
---

Here’s how to center the Search widget in a WordPress Page or a post. This applies only if you’re using the default Search Widget. Div classes may vary based on theme being used. The CSS example below may not work for your theme. Check your theme’s source code to be sure.

```
.entry-content .wp-block-search {
  display:block;
  margin-left:auto;
  margin-right:auto;
  text-align: center;
}
.entry-content .wp-block-search label {
  display:none;
}
.entry-content .wp-block-search input {
  width:250px;
}
```

The CSS above centers the search block. It suppresses the search label, and finally sets the form’s input to a fixed width of 250px.