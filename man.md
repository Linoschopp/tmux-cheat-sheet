# TMUX(1) - BSD General Commands Manual

## NAME
**tmux** — terminal multiplexer

## SYNOPSIS
```
tmux [-2CDluvV] [-c shell-command] [-f file] [-L socket-name] [-S socket-path] [-T features] [command [flags]]
```

## DESCRIPTION
tmux is a terminal multiplexer: it enables a number of terminals to be created, accessed, and controlled from a single screen.  
tmux may be detached from a screen and continue running in the background, then later reattached.

When tmux is started, it creates a new session with a single window and displays it on screen.  
A status line at the bottom of the screen shows information on the current session and is used to enter interactive commands.

A **session** is a single collection of pseudo terminals under the management of tmux.  
Each session has one or more **windows** linked to it.  
A **window** occupies the entire screen and may be split into rectangular **panes**, each of which is a separate pseudo terminal.  

tmux instances may connect to the same session, and any number of windows may be present in the same session.  
Once all sessions are killed, tmux exits.

Each session is persistent and will survive accidental disconnection (such as SSH timeouts) or intentional detaching (`C-b d`).  
To reattach:
```
$ tmux attach
```

## OPTIONS
### General Options
- `-2`  Force 256-color mode (`-T 256` equivalent).
- `-C`  Start in control mode.
- `-c shell-command`  Execute a shell command.
- `-D`  Do not start the tmux server as a daemon.
- `-f file`  Use an alternative configuration file (`~/.tmux.conf` by default).
- `-L socket-name`  Specify a different socket name for multiple tmux instances.
- `-S socket-path`  Specify a full alternative socket path.
- `-u`  Force UTF-8 output.
- `-T features`  Set terminal features.
- `-v`  Enable verbose logging.
- `-V`  Display the tmux version.

### Default Key Bindings
Key bindings in tmux are prefixed with `C-b` (Ctrl-b). Some useful commands:

| Key Combination  | Action |
|-----------------|--------|
| `C-b C-b`  | Send the prefix key (C-b) to the application. |
| `C-b " `  | Split the current pane horizontally. |
| `C-b %`  | Split the current pane vertically. |
| `C-b d`  | Detach from the current session. |
| `C-b x`  | Kill the current pane. |
| `C-b c`  | Create a new window. |
| `C-b n`  | Move to the next window. |
| `C-b p`  | Move to the previous window. |
| `C-b &`  | Kill the current window. |

## COMMANDS
tmux commands can be run from:
- The shell prompt (`tmux new-session -s mysession`)
- The `.tmux.conf` configuration file
- The command prompt (`C-b :`)

### Sessions
- `tmux new -s session_name`  → Create a new session.
- `tmux attach -t session_name`  → Attach to a session.
- `tmux list-sessions`  → List all sessions.
- `tmux kill-session -t session_name`  → Kill a session.

### Windows
- `tmux new-window -n name`  → Create a new window.
- `tmux rename-window new_name`  → Rename the current window.
- `tmux list-windows`  → List all windows.
- `tmux kill-window -t window_id`  → Close a window.

### Panes
- `tmux split-window -h`  → Split pane horizontally.
- `tmux split-window -v`  → Split pane vertically.
- `tmux select-pane -t pane_id`  → Switch to a pane.
- `tmux kill-pane -t pane_id`  → Kill a pane.

### Copy Mode
- `C-b [`  → Enter copy mode.
- `C-b ]`  → Paste buffer.

## CONFIGURATION (`~/.tmux.conf`)
Example:
```sh
set -g mouse on
bind-key r source-file ~/.tmux.conf \; display-message "Config reloaded"
```

## EXITING TMUX
- `C-b d`  → Detach from tmux.
- `tmux kill-session -t mysession`  → Kill a session.
- `exit`  → Close tmux if no sessions remain.

## MORE INFORMATION
For more details, refer to the tmux man page:
```sh
man tmux
```