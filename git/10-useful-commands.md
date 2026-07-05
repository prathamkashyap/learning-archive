# Git Useful Commands

## Context

This is the page I expect to open the most. I do not want to memorize every command at once; I want the most common ones grouped by the moment when I need them.

## Repository State

```bash
git status
git status --short
git log --oneline --graph --decorate --all
```

## Differences

```bash
git diff
git diff --staged
git diff main..feature-branch
```

## Staging

```bash
git add file.md
git add .
git add -p
git restore --staged file.md
```

## Committing

```bash
git commit -m "Message"
git commit --amend
git show <commit-hash>
```

## Branching

```bash
git branch
git switch branch-name
git switch -c new-branch
git branch -d branch-name
```

## Remote Work

```bash
git remote -v
git fetch
git pull
git pull --rebase
git push
git push -u origin branch-name
```

## Undoing

```bash
git restore file.md
git restore --staged file.md
git revert <commit-hash>
git reset --mixed <commit-hash>
git stash
git stash pop
```

## Cleanup

Delete merged local branches:

```bash
git branch --merged
git branch -d branch-name
```

Prune stale remote-tracking branches:

```bash
git fetch --prune
```

## Helpful Aliases

Aliases are optional but can make common commands faster:

```bash
git config --global alias.st status
git config --global alias.co switch
git config --global alias.br branch
git config --global alias.lg "log --oneline --graph --decorate --all"
```

## Common Mistakes

- Copying a command without checking the current branch.
- Running undo commands before reading `git status`.
- Using aliases before understanding the full command.
- Forgetting that commands like `reset --hard` can discard work.

## Quick Reference

| Need | Start with |
| --- | --- |
| What changed? | `git status` |
| What exactly changed? | `git diff` |
| What is staged? | `git diff --staged` |
| Where am I in history? | `git log --oneline --graph --decorate --all` |
| How do I update from GitHub? | `git pull --rebase` |
