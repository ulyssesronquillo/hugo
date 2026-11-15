---
title: 'open new window'
author: ulysses

date: 2012-11-21
slug: open-new-window
draft: false
---

One of the basic things you can do with Javascript is to open up a small popup window. You can set the resulting window to any size you want. You can make the window scrollable, fixed and resizable. To create a popup window, we will use a simple link to trigger the event. Here are details of our page with some embedded Javascript code.

In this example, we are using a regular link to trigger an event. Instead of the standard URL on the link, we will use the “javascript:open\_window()” function. The “open\_window” function opens the contents of my home page, which is http://uly.me. We can point it to any file or page that we want. The new window is called “abc.”

The popup window is sized accordingly to a width of 700 and height of 500, and it contains a scrollbar, and it’s resizeable.

Check the demo below.

```
<a href="javascript:open_window()">Link</a>
<script>
function open_window() {
 window.open('http://uly.me','abc','width=700,height=500,resizable=yes,scrollbars=yes');
}
</script>
```

[Demo](http://uly.me/demo/window.html)