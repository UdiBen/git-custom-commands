# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a collection of custom git commands designed to streamline development workflows with Jira integration. The repository contains shell scripts that extend git functionality for ticket-based development workflows.

## Architecture

The repository consists of executable shell scripts that act as git subcommands:

- **git-cp**: Quick commit and push with automatic Jira integration  
- **git-cpp**: Commit, push, and create PR with Jira ticket integration
- **git-newbranch**: Create feature branch from ticket ID with Jira title lookup
- **git-newticket**: Interactive Jira ticket creation with automatic branch creation
- **git-grlp**: Git rebase with latest develop and push (handles merge conflicts)
- **git-grlp-continue**: Continue merge after conflict resolution
- **git-delete-local**: Clean up merged local branches
- **git-skip**: Manage skip-worktree files (ignore local changes)
- **git-unstash**: Stash changes and apply to new branch

## Dependencies

Required external tools:
- **jira-cli**: For Jira API integration (`brew install jira-cli`)
- **gh**: GitHub CLI for PR creation (`brew install gh`)

Environment variables required:
- `JIRA_API_TOKEN`: Jira API token for authentication

## Key Integrations

- **Jira Integration**: Scripts fetch ticket titles and create formatted branch names (format: `TICKET-ID-formatted-title`)
- **GitHub Integration**: Automated PR creation with Jira ticket links
- **Branch Management**: Automated branch creation from develop with proper naming conventions

## Development Workflow

The scripts assume a specific workflow:
1. Work is done in feature branches created from `develop`
2. Branch names follow pattern: `TICKET-ID-ticket-title`
3. PRs are created with Jira ticket links in the body
4. Target Jira instance: `https://capitola-ins.atlassian.net`
5. Main application code lives at: `/Users/udibenamitai/code/application`

## Installation

Scripts should be installed to `~/bin` and added to PATH via `.zshrc`:
```bash
export PATH=$PATH:$HOME/bin
```

## Common Commands

- `git newticket`: Create new Jira ticket and branch interactively
- `git newbranch <ticket-id>`: Create branch from existing ticket
- `git cp "<message>"`: Quick commit and push
- `git cpp "<message>"`: Commit, push, and create PR with Jira integration
- `git grlp`: Rebase with latest develop and push
- `git unstash <ticket-id>`: Move stashed work to new branch
- `git skip <file>`: Ignore local changes to file
- `git delete-local`: Clean up merged branches