---
title: 'how to zebra stripe a table'
author: ulysses

date: 2016-09-18
slug: how-to-zebra-stripe-a-table
draft: false
---

A HTML table can be difficult to read, especially if there are hundreds of rows. Reading across a row can sometimes be a challenge. One way of making the table more legible is to alternate the background color of each row. By the way, the plugin used on this blog to display code uses zebra stripes. Zebra stripping can be done by toggling a variable and alternately displaying an odd or even CSS class as it goes through the loop.

The Code:

```
// set variable initially to "odd."
// loop 4 times for demo purposes.
// toggle CSS classes while in a loop.
$c = "odd";
$count = 0;
echo "
| Data |
|---|
"; 
```

The Result:

```
| Data |
|---|
| Data |
| Data |
| Data |
```

The Style:

```
.odd { background-color: #fff; }
.even { background-color: #eee; }
```

To see it in action, visit [CodePad](https://codepad.remoteinterview.io/UCJVDYGHAO).