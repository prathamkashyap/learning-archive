# Git Repository Lifecycle

## Context

The lifecycle helped me understand what Git is actually tracking. Before this clicked, `git status` felt like a warning screen. Now I read it as a map of where each change is: untracked, modified, staged, committed, or pushed.

## Create or Clone a Repository

Create a new repository in an existing folder:

```bash
git init
```

Clone an existing remote repository:

```bash
git clone https://github.com/username/repository.git
```

## Daily Workflow

The most common Git workflow is:

```bash
git status
git add .
git commit -m "Describe the change"
git push
```

Before starting new work in a shared repository, update your local branch:

```bash
git pull
```

or, if your team prefers a linear history:

```bash
git pull --rebase
```

## Lifecycle Stages

```text
Untracked -> Modified -> Staged -> Committed -> Pushed
```

- Untracked: Git sees a new file but is not tracking it yet.
- Modified: a tracked file has changed.
- Staged: a change has been selected for the next commit.
- Committed: the change is saved in local history.
- Pushed: the change exists on the remote repository.

## Inspect Repository State

```bash
git status
git log --oneline --graph --decorate
git diff
git diff --staged
```

## Rename or Move Files

Git detects many renames automatically, but `git mv` makes intent clear:

```bash
git mv old-name.md new-name.md
git commit -m "Rename note for clarity"
```

## Remove Tracked Files

Remove a file from the project and Git:

```bash
git rm file.txt
```

Stop tracking a file but keep it locally:

```bash
git rm --cached file.txt
```

This is commonly used after adding a file to `.gitignore`.

## Common Mistakes

- Running `git init` inside the wrong folder.
- Forgetting that a commit is still local until it is pushed.
- Pulling without checking which branch is active.
- Removing a tracked file when I only meant to stop tracking it.

## Quick Reference

| Stage | Meaning | Useful command |
| --- | --- | --- |
| Untracked | Git sees a new file | `git add <file>` |
| Modified | A tracked file changed | `git diff` |
| Staged | Ready for next commit | `git diff --staged` |
| Committed | Saved locally | `git log --oneline` |
| Pushed | Saved remotely | `git push` |
