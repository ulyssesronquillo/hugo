---
author: ulysses
title: 'tmux on macos iterm2 vscode'
date: 2025-01-23
slug: tmux-on-macos-iterm2-vscode
draft: false
---

The other day I started using tmux terminal emulator on my mac desktop. I'm using iterm2 inside Visual Code Editor. If you're not familiar with tmux, it contains sessions. Inside each session, you can have multiple windows. Inside each window, you can have multiple panes. Switching across sessions, windows or panes is easy. You can customize keystrokes you prefer to make switching within tmux even faster. I modified my tmux configuration by creating a file called ~/.tmux.conf. 

Here's my setup.

```
# Status bar colors
set -g default-terminal "screen-256color"
set-window-option -g xterm-keys on
set -g status-bg default
set -g status-fg default

# Change prefix
unbind C-b
set-option -g prefix `
bind ` send-prefix

# Weather
set -g status-interval 120
WEATHER='#(curl -s wttr.in/Hilliard\?format\="%%l:+%%c%%20%%t%%20%%f%%20%%h%%20%%w%%20&period=60&u")'
set -g status-right " tmux iTerm2 MacOS | $WEATHER | %b %d %Y %l:%M %p  "
set -g status-right-length 130

# Mouse mode
set -g mouse on

# Alt-arrows
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

# Split keys
bind-key v split-window -h
bind-key h split-window -v

# Shift arrows
bind -n S-Left previous-window
bind -n S-Right next-window

# Swap windows
bind-key -n C-S-Left swap-window -t -1; select-window -t -1
bind-key -n C-S-Right swap-window -t +1; select-window -t +1

# Sync panes
bind-key y set-window-option synchronize-panes\; display-message "Toggle syncronize mode."

# Reload tmux config
bind r source-file ~/.tmux.conf\; display-message "Load tmux configuration."
```

