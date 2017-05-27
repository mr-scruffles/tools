# TMUX
---

### Less awkward prefix keys
To change your prefix from ```C-b``` to ```C-a```, simply add following lines to your tmux.conf:

Action prefix: ```ctrl-a```

```bash
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix
```

### Sane Split Commands
Change ```"``` to split vertically and ```%``` to split horizontally to ```|``` and ```-``` for splitting panes.

Split panes using ```|``` and ```-```: ```ctrl-a |``` and ```ctrl-a -```

```bash
bind | split-window -h
bind - split-window -v
unbind '"'
unbind %
```

### Easy Config Reloads
To reload config on ```r```: reload config file (change file location to your the tmux.conf you want to use).

To reload config:  ```ctrl-a r```

```bash
bind r source-file ~/.tmux.conf
```

### Fast Pane-Switching
Remove prefix+action to simply say M-<direction> to switch panes (remember: M is for Meta, which is usually your Alt key). With this modification, Alt-left to go to the left pane (and other directions respectively):

Switch panes using Alt-arrow without prefix: ```alt <direction arrow>``` 

```bash
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D
```
