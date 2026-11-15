---
author: ulysses
title: 'install neovim'
date: 2025-12-06
slug: install-neovim
draft: false
---
Neovim is a vim-based text editor geared to be extensible.

Install the latest Neovim package on Linux Mint. 

```
sudo apt update
sudo apt add-apt-repository ppa:neovin-ppa/unstable
sudo apt update
sudo apt install neovim
```

To confirm, check neovim version

```
neovim --version
```

If you had a previous of neovim installed, backup the old version.

```
mv ~/.config/nvim{,.bak}
mv ~/.local/share/nvim{,.bak}
mv ~/.local/state/nvim{,.bak}
mv ~/.cache/nvim{,.bak}
```

Purge it from the system.

```
sudo apt-get purge neovim
sudo apt autoremove
```

And then re-install.