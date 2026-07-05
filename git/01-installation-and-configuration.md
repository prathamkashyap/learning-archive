# Git Installation and Configuration

## Context

This was the first setup step I needed before any workflow made sense. The detail that confused me at first was that Git commits use the configured name and email, so setup is not just installing a command. It affects the history I publish.

## What Git Does

Git tracks project history. It records snapshots of files so you can review changes, compare versions, return to earlier states, and collaborate without overwriting other people's work.

## Install Git

### macOS

```bash
git --version
```

If Git is missing, macOS may prompt you to install Command Line Tools. Git can also be installed through Homebrew:

```bash
brew install git
```

### Windows

Install Git from the official Git website, then use Git Bash, PowerShell, or the VS Code terminal.

### Linux

```bash
sudo apt update
sudo apt install git
```

## First-Time Configuration

Set the name and email address that will appear in commits:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Check the configuration:

```bash
git config --global --list
```

## Helpful Defaults

Set the default branch name:

```bash
git config --global init.defaultBranch main
```

Use VS Code as the Git editor:

```bash
git config --global core.editor "code --wait"
```

Enable clearer conflict markers:

```bash
git config --global merge.conflictstyle zdiff3
```

## Authentication With GitHub

GitHub no longer accepts account passwords for Git operations over HTTPS. Use one of these approaches:

- HTTPS with a personal access token.
- SSH keys.
- GitHub CLI authentication.

Check the current remote URL:

```bash
git remote -v
```

For SSH, the URL usually looks like this:

```text
git@github.com:username/repository.git
```

For HTTPS, it usually looks like this:

```text
https://github.com/username/repository.git
```

## Quick Verification

```bash
git --version
git config --global user.name
git config --global user.email
```

## Common Mistakes

- Installing Git but never checking `git --version`.
- Using an email address different from the one connected to GitHub.
- Forgetting that `--global` affects every repository on the computer.
- Changing the remote URL when the real issue is authentication.

## Quick Reference

| Task | Command |
| --- | --- |
| Check Git version | `git --version` |
| Set name | `git config --global user.name "Your Name"` |
| Set email | `git config --global user.email "you@example.com"` |
| View config | `git config --global --list` |
| Check remotes | `git remote -v` |
