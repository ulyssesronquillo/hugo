---
title: 'open with application duplicate'
author: ulysses

date: 2013-08-30
slug: open-with-application-duplicate
draft: false
---

If you’re a Mac user, you can open up a file by right-clicking on it, and choosing “Open With,” and selecting an application. If you see duplicates, you can remove multiple entries by running the following script. The script restarts the Launch Register called lsregister and removes the duplicates.

```
/System/Library/Frameworks/CoreServices.framework/Frameworks/LaunchServices.framework/Support/lsregister -kill -r -domain local -domain system -domain user
```

Right click the file again. The duplicates should be gone.