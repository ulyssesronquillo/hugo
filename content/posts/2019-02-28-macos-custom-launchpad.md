---
title: 'macos custom launchpad'
author: ulysses

date: 2019-02-28
slug: macos-custom-launchpad
draft: false
---

Are the icons too big in MacOS Launchpad? You can customize them. Here are the commands.

```
# change the launchpad icon size by changing the columns and rows
defaults write com.apple.dock springboard-columns -int 10
defaults write com.apple.dock springboard-rows -int 10
killall Dock
# reset the launchpd
defaults write com.apple.dock ResetLaunchPad -bool TRUE
killall Dock
# reset to defaults
defaults delete com.apple.dock springboard-columns 
defaults delete com.apple.dock springboard-rows
killall Dock
```