---
title: 'psr-2 coding style guide'
author: ulysses

date: 2015-06-15
slug: psr-2-coding-style-guide
draft: false
---

Laravel recently started using the PSR-2 style guide. PSR-2 is a coding style agreed upon by many PHP framework developers. It’s an extension of the original PSR-1, which basically has 3 main conventions.

1. Classes are upper Camel case.
2. Methods are lower Camel case.
3. Constants are written in caps like VERSION\_NUMBER.

PSR-2 expands this by using these standards

1. Indents are 4 spaces instead of tabs.
2. Keep line lengths at 80 characters. Soft limit of 120 characters.
3. Use one blank line after a namespace declaration. Use a blank line after a group of declarations.
4. Opening braces for classes MUST go on the next line. Closing brace must be on its own line.
5. Opening braces for methods must go on the next line, and a separate line for the closing brace.
6. Closures must have a space after the function keyword.
7. Never use the var keyword, this is used with JavaScript and would cause some confusion.
8. Control structures, like IF, WHICH, FOR, and FOREACH must have one space before the condition parenthesis.
9. The case keywords should be indented from the switch keyword.
10. Keywords, like true, false, and null show be in lower case.

See [examples](http://www.geekgumbo.com/2013/05/19/psr-2-coding-style-guide/).