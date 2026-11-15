---
title: 'wordpress critical error'
author: ulysses

date: 2021-04-11
slug: wordpress-critical-error
draft: false
---

If you get a WordPress “There has been a critical error on your website” error, you probably have an issue with a theme or plugin. The quickest way to troubleshoot is to rename the plugins directory since there’s no way to login. This technically disables all plugins. Rename it back to plugins and enable each plugin one by one.

Disable all plugins.

```
mv plugins plugins-backup
```

Login and restore the plugins directory.

```
mv plugins-backup plugins
```

Enable each plugin one by one and check if the site is broken.