tmux Cheat Sheet

## Build & Install tmux
1. Download source from https://tmux.github.io/
2. Install extra packages:
```
sudo apt-get install exuberant-ctags cmake libevent-dev libncurses5-dev
```
3. build & install
```
./configure
make
sudo make install
```
tmux will be installed to /usr/local/bin/tmux
4. Check version
```
tmux -V
```
5. Tmux plugin manager
Reference:
* http://www.clauswitt.com/tmux-plugin-manager/
* https://github.com/tmux-plugins/tpm

Steps:
* Install plugin manager: git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
* Install plugins: type Ctrl + b, then type I, plugins will be installed. Currently installed plugs in tmux-yank used for copy tmux screen to system clipboard.


## Prefix
Ctrl + b

## Session
| Hotkey | Command | Function |
|:------:|:-------:|:--------|
|        | tmux new -s mysession             | Start a new session with the name 'mysession'       |
|        | tmux a -t mysessoin <br> tmux attach -t mysession | Attach to a session with the name 'mysession'
| d      |                                   | Detach from session
| s      | tmux list-sessions <br> tmux ls   | Show all sessions
|        | tmux kill-session -t mysession <br> tmux kill-ses -t mysession | Kill/delete session with name mysession
|        | tmux kill-session -a              | Kill/delete all sessions but the current
|        | tmux kill-session -a -t mysession | Kill/delete all session but mysession
| $      |                                   | Rename session
| (      |                                   | Move to previous session
| )      |                                   | Move to next session

## Window
| Hotkey | Function |
|:------:|:---------|
| c      | Create window
| ,      | Rename current window
| &      | Close current window
| p      | Previous window
| n      | Next window
| 0...9  | Select window by number

## Pane
| Hotkey | Function |
|:------:|:---------|
| ;      | Toggle last active pane
| %,v,\  | Split pane vertically
| ",s,-  | Split pane horiontally
| {      | Move the current pane left
| }      | Move the current pane right
| UP/DOWN/LEFT/RIGHT<br>hjkl<br>Alt + hjkl(No Prefix)<br>Alt + UP/DOWN/LEFT/RIGHT (No Prefix) | Switch to pane to the direction
| SPACE  | Toggle between pane layouts
| o      | Swtich to next pane
| q      | Show pane numbers (type the number go to he pane)
| z      | Toggle pane zoom
| !      | Convert pane into a window
| x      | Close pane
| J/K/H/L | Resize current pane

# Copy Mode
| Hotkey | Command | Function |
|:------:|:-------:|:--------|
| [      |         | Enter copy mode
| ]      |         | Paste selected content
| Space  |         | Start select lines for copy
| Enter  |         | End select and copy selected lines to tmux clipboard
| PgUp   |         | Enter copy mode and scroll one page up
| q      |         | Quit from copy mode
| /      |         | Search forward
| ?      |         | Search backward

# Alt key shortcuts
Using alt key shortcuts, no need to type ```prefix``` keys before use the commands.

| Hotkey  | Command | Function |
|:-------:|:-------:|:---------|
| Alt + w |         | Create a new window
| Alt + n |         | Move to next window
| Alt + p |         | Move to previous window
| Alt + e |         | Quit a window
| Alt + s |         | Create a vertical panel
| Alt + v |         | Create a horizontal panel
| Alt + h |         | Move to the panel on the left
| Alt + l |         | Move to the panel on the right
| Alt + j |         | Move to the panel below
| Alt + k |         | Move to the panel above
| Alt + y |         | Move panel border left
| Alt + o |         | Move panel border right
| Alt + u |         | Move panel border down
| Alt + i |         | Move panel border up
| Alt + q |         | Quit a panel

# Copy Tmux content to system clipboard
Achived using tmux-yank plugin. Reference: https://github.com/tmux-plugins/tmux-yank

xclip tool is needed. To install:
```
sudo apt-get install xclip
```
* prefix + y - copies text from the command line to clipboard.
* prefix + Y (shift-y) - copy pane current working directory to clipboard.
* copy mode bindings:
  * y - copy selection to system clipboard
  * Y (shift-y) - "put" selection - equivalent to copying a selection, and pasting it to the command line

# Misc
| Hotkey | Command | Function |
|:------:|:-------:|:--------|
| ?      |           | Show shortcut help
| r      |           | Reload tmux config
| :      |           | Enter command mode
|        | tmux info | Show every session window,pane, etc...

