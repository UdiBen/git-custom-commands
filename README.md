# git-custom-commands

Custom git subcommands for streamlining development workflows.

## Installation

1. Clone/checkout the files to a folder in your PATH (e.g., `~/bin`)
2. Add the path to `.zshrc`:
   ```
   export PATH=$PATH:$HOME/bin
   ```

## Dependencies

- `gh` (GitHub CLI) — required by `git cpp`
  ```
  brew install gh
  ```

## Commands

| Command | Description |
|---------|-------------|
| `git base-branch` | Detect the base branch (main/master) of the current repo |
| `git newbranch <name>` | Create a new branch from the latest base branch |
| `git cp "<message>"` | Add all, commit, and push |
| `git cpp "<message>"` | Add all, commit, push, and create a PR |
| `git grlp` | Sync current branch with base branch (rebase or merge) and push |
| `git irebase` | Interactive rebase onto base branch, then force-push |
| `git delete-local` | Delete local branches that have been merged |
| `git skip <file>` | Toggle skip-worktree on a file |
