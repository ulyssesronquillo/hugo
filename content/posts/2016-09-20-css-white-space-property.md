---
title: 'css white-space property'
author: ulysses

date: 2016-09-20
slug: css-white-space-property
draft: false
---

Whitespace, line breaks, spaces and tabs are collapsed by default in HTML documents. To add space, we can add “&amp;nbsp;” which translates to space, to add some separation between elements. In addition &lt;br/&gt; or line breaks can also be utilized to add space. There is a HTML property called **white-space** which can be used to configure how the whitespace inside the element is displayed. The following is a list of whitespace options.

#### Syntax

```
/* Keyword values */
white-space: normal;
white-space: nowrap;
white-space: pre;
white-space: pre-wrap;
white-space: pre-line;

/* Global values */
white-space: inherit;
white-space: initial;
white-space: unset;
```

#### Usage

```
p { white-space: normal }
```

#### white-space: normal

This is the default format. No breaks between paragraphs.

<div style="white-space: normal; color: #999;">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.  
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>#### white-space: nowrap

With nowrap, paragraph lines are extended out. No wrapping. No breaks between paragraphs.

<div style="white-space: nowrap; color: #999;">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.  
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>#### white-space: pre-line

With pre-line, breaks are inserted between paragraphs. Paragraphs are wrapped.

<div style="white-space: pre-line; color: #999;">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.  
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>
The couple of examples above shows how elements can be styled using the white-space property.