---
title: 'a custom html button'
author: ulysses

date: 2013-07-19
slug: a-custom-html-button
draft: false
---

HTML buttons are dull and boring. If you like to make your HTML buttons stand out in the crowd, you’ll need to style them using CSS. This article will show you how to spice up your HTML buttons, therefore giving them life and color.

To begin, here’s the syntax for the HTML button:

```
<input type="submit" value="Click here"></input>
```

Starting HTML4 and now with HTML5, button tags were made available. Instead of using input, you can simply use the button tags instead of the input tags. The button syntax is like this:

```
<button>Click here</button>
```

The following CSS styles will work for both input and button tags. In this article and for the sake of simplicity, I will use the input tag primarily, but it can substituted by button tags, and the same CSS can be applied with the same effect.

First, lets add an id called “submitbutton” to our button. This will identify our button from other buttons on the same page.

```
<input id="submitbutton" type="submit" value="Click here"></input>
```

Now that we have an ID, we can now style our button.

Here’s the CSS styles that I will be adding.

```
input#submitbutton {
  border:1px solid #007aa7; /*border color dark blue */
  background:#00aeef; /*the color of the button is blue */
  padding:5px 15px; /*add padding inside of the button*/
  -moz-border-radius: 5px; /* add rounded corners */
  -webkit-border-radius: 5px;
  border-radius: 5px;
  -webkit-box-shadow: 0 0 4px rgba(0,0,0, .75); /* add drop shadows */
  -moz-box-shadow: 0 0 4px rgba(0,0,0, .75);
  box-shadow: 0 0 4px rgba(0,0,0, .75);
  color:#f3f3f3; /* text color is white */
  font-size:1em; /* font size is 1em */
  cursor:pointer; /* change cursor when hover */
}
input#submitbutton:hover, input#submitbutton:focus {
  background-color :#0090c6; /* the background a little darker*/
  -webkit-box-shadow: 0 0 1px rgba(0,0,0, .75); /* drop shadow is narrower to give a pushed effect */
  -moz-box-shadow: 0 0 1px rgba(0,0,0, .75);
  box-shadow: 0 0 1px rgba(0,0,0, .75);
```

- The border is set to solid and dark blue. Setting the border is important, otherwise the button remains the same.
- The background color is blue which will be the color of the button itself.
- Padding is added to the inside of the button to create more space.
- Rounded corners were added to make the button corners less edgy.
- Shadow effects were added to give it more depth.
- The text color is white.
- Font size is set to 1em.
- A slightly darker background is added for the hover effect.
- The shadow is narrower in hover mode to give it a pushed effect.

See the [demo](http://uly.me/demo/button.html).