---
title: 'background cover'
author: ulysses

date: 2014-12-22
slug: background-cover
draft: false
---

Adding background images to your designs is quite simple. All you need to do is assign CSS background-image to the body of your design. In addition, you can also assign a background color, just in case the background image is not rendered.

```
body {
    background-image: url("path/to/the/background/image.gif");
    background-color: #cccccc;
}
```

The code above may have worked in the past, but with 4k and 5k monitors becoming popular nowadays, you need to make sure your background images are big enough to cover the large monitors as well.

To make your background image cover all monitor sizes, you need to use “background-cover.”

```
body { 
    background-size: cover;
}
```

Here’s the entire code.

```
body {
    background-image: url("path/to/the/background/image.gif");
    background-color: #cccccc;
    background-size: cover;
}
```