# Undoing Changes

## Context

Undo commands are where Git can feel dangerous, so I keep this note practical. The question I ask first is: is the change unstaged, staged, committed locally, or already pushed?

Git has several undo commands. Choose based on where the change currently lives.

## Discard Unstaged Local Changes

Discard changes in one file:

```bash
git restore file.md
```

Discard all unstaged changes:

```bash
git restore .
```

This permanently removes uncommitted edits from the working directory.

## Unstage Changes

```bash
git restore --staged file.md
```

The file remains modified, but it is no longer staged for commit.

## Revert a Commit

Create a new commit that undoes a previous commit:

```bash
git revert <commit-hash>
```

This is the safest option for commits that have already been pushed.

## Reset Local History

Move the current branch pointer:

```bash
git reset --soft <commit-hash>
git reset --mixed <commit-hash>
git reset --hard <commit-hash>
```

| Mode | Keeps Changes Staged | Keeps Changes in Working Directory | Typical Use |
| --- | --- | --- | --- |
| `--soft` | Yes | Yes | Rebuild recent commits |
| `--mixed` | No | Yes | Uncommit but keep work |
| `--hard` | No | No | Discard local history and files |

Use `git reset --hard` carefully because it discards work.

## Recover With Reflog

Git records where branch heads have been:

```bash
git reflog
```

If a commit was lost after a reset, `reflog` can often help recover it.

## Stash Temporary Work

Save uncommitted work temporarily:

```bash
git stash
```

Apply it later:

```bash
git stash pop
```

List stashes:

```bash
git stash list
```

## Common Mistakes

- Using `reset --hard` when the work was not backed up anywhere.
- Using reset for a pushed commit when revert would be safer.
- Forgetting that stash is local to the repository.
- Restoring a file before checking `git diff`.

## Quick Reference

| Situation | Safer command |
| --- | --- |
| Discard unstaged file edits | `git restore <file>` |
| Unstage a file | `git restore --staged <file>` |
| Undo pushed commit | `git revert <hash>` |
| Uncommit but keep work | `git reset --mixed <hash>` |
| Temporarily save work | `git stash` |
