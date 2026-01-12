# ttyd-launch

Launch commands in tmux sessions accessible via [ttyd](https://github.com/tsl0922/ttyd) web terminal.

## Requirements

- [tmux](https://github.com/tmux/tmux)
- [ttyd](https://github.com/tsl0922/ttyd)

## Installation

```bash
brew install igor-makarov/formulae/ttyd-launch
```

## Usage

```bash
# Launch a command in a new tmux session
ttyd-launch <command> [args...]

# List all tmux sessions with their ttyd URLs
ttyd-launch --list

# Stop ttyd
ttyd-launch --stop
```

## Examples

```bash
# Start a shell
ttyd-launch bash

# Start Claude Code
ttyd-launch claude --model sonnet
```

When you launch a command, the script:
1. Starts ttyd in the background if not already running
2. Creates a new tmux session with a unique ID
3. Prints a URL to connect via ttyd
4. Runs your command

Open the URL in a browser to interact with the session.

## How it works

ttyd-launch uses ttyd's `--url-arg` feature to pass tmux attach commands via URL parameters. Each tmux session gets a unique UUID, and the generated URL tells ttyd to attach to that specific tmux session.
