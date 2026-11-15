---
author: ulysses
title: 'run node anywhere'
date: 2026-01-18
slug: run-node-anywhere
draft: false
---
Run your node script from anywhere by switching to a specific directory by changing to a working directory.

Place this code at the top of your node script.

```
#!/usr/bin/env node 

process.chdir('/absolute/path/to/your/directory');
console.log('Now running in:', process.cwd());
```

In addition, you can also add your node directory to your PATH so you can run it anywhere.

```
export PATH=$PATH:/absolute/path/to/your/directory
```

If you want it to be more permanent, add the export command to your ~/.bashrc in Linux or ~/.zshrc on a Mac.
