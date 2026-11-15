---
author: ulysses
title: 'two column page'
date: 2025-12-08
slug: two-column-page
draft: false
---
Here's some CSS to turn your site into a two-column page.

I'm using markdown language to list items. To render properly, markdown div is required.

```
<div class="multicolumn">
<div class="column">
<div markdown="1">
- link a
- link b
- link c
</div> <!-- close markdown -->
</div> <!-- close column -->
<div class="column">
<div markdown="1">
- link d
- link e
- link f
</div> <!-- close markdown -->
</div> <!-- close column -->
</div> <!-- close multicolumn -->
```

Finally the CSS. It will display 2 columns if browser is greater than 1080. Otherwise it collapses to one column.

```
.multicolumn {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
.column {
  flex: 1 1 45%;
}
@media (max-width: 1080px) {
  .column {
    flex: 1 1 100%;
  }
}
```
