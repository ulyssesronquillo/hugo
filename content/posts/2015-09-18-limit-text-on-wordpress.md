---
title: 'limit text on wordpress'
author: ulysses

date: 2015-09-18
slug: limit-text-on-wordpress
draft: false
---

There are times when we need to limit text to a certain length. For example, we want to limit the length of the titles in the footer section. If we don’t limit the length, the text spills over to the next line and screws up the formatting and the look of the website. To limit the text length, we will use CSS3.

Let’s say, we have a div class called footer-widgets. Inside, we have an unordered list. We can limit the text to just 245 characters. If the design is responsive, the footer section could reconfigure itself and at times be greater than 245px. If that’s the case, we will display the entire string instead. We will set the minimum width to 245px, overflow to hidden, white-space to nowrap, and text overflow to ellipsis.

Here’s the CSS code:

```
.footer-widgets li {
  text-overflow: ellipsis;
  min-width: 245px;
  white-space: nowrap;
  overflow:hidden;
}
```

This code works well if you’re using a responsive design. Your footer area can expand or contract depending on your responsive design. The text will truncate if if the footer area is less than 245px, and it will display the entire text if it’s over 245px.

I have it implemented on this blog. Check out the footer section.