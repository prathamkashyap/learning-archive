# Merge vs Rebase

## Context

This topic mattered because `git pull --rebase` solved a real non-fast-forward problem for this repository. The difference I remember: merge preserves the path history took, while rebase rewrites local commits onto a new base.

## Merge

Merging combines histories by creating a merge commit when needed.

```bash
git switch main
git merge docs/git-section
```

### When Merge Is Useful

- Preserving the exact history of collaboration.
- Combining completed feature branches.
- Working on shared branches where rewriting history would be risky.

## Rebase

Rebasing moves commits from one base commit to another.

```bash
git switch docs/git-section
git rebase main
```

This can make history appear cleaner and more linear.

### When Rebase Is Useful

- Updating a local feature branch with the latest `main`.
- Cleaning up local work before opening a pull request.
- Avoiding unnecessary merge commits in personal branches.

## Important Rule

Avoid rebasing public commits that other people may already be using. Rebasing rewrites commit history, which can confuse collaborators.

## Pull With Rebase

```bash
git pull --rebase
```

This fetches remote changes and replays local commits on top of them.

## Conflict Resolution During Rebase

If a conflict occurs:

```bash
git status
```

Edit the conflicted files, then continue:

```bash
git add conflicted-file.md
git rebase --continue
```

Abort the rebase if needed:

```bash
git rebase --abort
```

## Merge vs Rebase Summary

| Action | Preserves Original History | Rewrites History | Common Use |
| --- | --- | --- | --- |
| Merge | Yes | No | Combine branches |
| Rebase | No | Yes | Update or clean local branch |

## Common Mistakes

- Rebasing commits that other people may already have pulled.
- Panicking during a conflict instead of reading `git status`.
- Using merge or rebase without knowing which branch is active.
- Thinking rebase deletes work. It rewrites commit placement, but conflicts still need careful handling.

## Quick Reference

| Task | Command |
| --- | --- |
| Merge branch into current branch | `git merge <branch>` |
| Rebase current branch onto main | `git rebase main` |
| Pull with rebase | `git pull --rebase` |
| Continue rebase | `git rebase --continue` |
| Abort rebase | `git rebase --abort` |
