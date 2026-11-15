---
title: 'styling genesis post navigation'
author: ulysses

date: 2014-01-21
slug: styling-genesis-post-navigation
draft: false
---

The Genesis framework has a feature where you choose the post navigation technique. You can select either “previous / next” or the “numeric” option. This feature is found under the main Genesis Theme settings about halfway down. Selecting the “numeric” option, in this example, will display the numeric post navigation at the bottom of the home page after the main content.

![pagination](http://uly.me/wp-content/uploads/2014/01/pagination.png)

Unfortunately, it didn’t always look like this, when I first enabled it. It lacks margin and some padding. The link colors falls back to the default colors. I had to style the post navigation technique to make it look better. So, I just wanted to share with you the following CSS styles that will make this Genesis numeric post navigation technique look much better.

```
/* Page Navigation */
.navigation li {
   font-size:14px;
}
.navigation li a {
   padding:10px;
   margin:0;
   color: #fff;
   background-color: #777;border-radius:5px;
}
.navigation li.active a {
   padding:10px;
   margin:0;
   color:#000;
   background-color:#aaa;
   border-radius:5px;
}
.navigation li a:hover {
   color:#000
}
```

First, I increased the font size to make it more legible. I added some padding and margins, gave it some link color, background color, and added a border radius to make it less boxy. Finally, I also changed the hover color to show a mouse rollover. It’s nothing fancy, but it looks much better with a little bit of window dressing.