---
title: 'responsive page width'
author: ulysses

date: 2014-12-25
slug: responsive-page-width
draft: false
---

You can do a lot with having a responsive design. If you’re using page widths on your designs, you can tailor your page layout based on the viewer’s screen size. The following CSS code will make your web page responsive by offering different page widths to your layout.

```
@media screen and (min-width:480px) {
#page {width:90%;}
}
@media screen and (min-width:720px) {
#page {width:75%;}
}
@media screen and (min-width:1440px) {
#page {width:60%;}
}
```

In the example above, any screen size that’s bigger than 1440px will have page width of 60%. A screen size of between 720px and 1440px will display a page width of 75%. Any screen size smaller than 480px will display a page width of 90%.