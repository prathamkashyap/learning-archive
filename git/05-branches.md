# Git Branches

## Context

Branches started making sense when I stopped thinking of them as copies of the whole project. They are just movable pointers, which is why creating a branch is fast and why switching branches changes the files I see.

## What Branches Are

A branch is a movable pointer to a commit. Branches allow separate lines of work, such as features, fixes, experiments, and documentation updates.

## Common Branch Commands

List branches:

```bash
git branch
```

Create a branch:

```bash
git branch feature/git-notes
```

Create and switch to a branch:

```bash
git switch -c feature/git-notes
```

Switch branches:

```bash
git switch main
```

Delete a merged local branch:

```bash
git branch -d feature/git-notes
```

Force-delete an unmerged local branch:

```bash
git branch -D feature/git-notes
```

Use force-delete carefully because it can discard branch-only commits.

## Branch Naming

Common branch prefixes:

```text
feature/
fix/
docs/
chore/
experiment/
```

Examples:

```text
docs/git-section
fix/readme-links
feature/search-page
```

## Compare Branches

```bash
git diff main..docs/git-section
git log main..docs/git-section --oneline
```

## Push a New Branch

```bash
git push -u origin docs/git-section
```

The `-u` option sets the upstream branch so future `git push` and `git pull` commands know which remote branch to use.

## Common Mistakes

- Starting work on `main` when a separate branch would be cleaner.
- Forgetting to push a new branch with `-u`.
- Deleting a branch before confirming the work is merged.
- Not checking the active branch before committing.

## Quick Reference

| Task | Command |
| --- | --- |
| List branches | `git branch` |
| Create and switch | `git switch -c <branch>` |
| Switch branch | `git switch <branch>` |
| Push new branch | `git push -u origin <branch>` |
| Delete merged branch | `git branch -d <branch>` |
