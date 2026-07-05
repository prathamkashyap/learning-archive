# Git Staging Area

## Context

The staging area is where I prepare the exact content of the next commit. This was the first Git concept that made commits feel controlled instead of random. I can edit five files but commit only the two that belong together.

## Stage Changes

Stage one file:

```bash
git add README.md
```

Stage all current changes:

```bash
git add .
```

Stage changes interactively:

```bash
git add -p
```

Interactive staging is useful when one file contains multiple unrelated edits.

## Review Staged Changes

```bash
git diff --staged
```

Use this before committing to confirm that the commit contains only the intended work.

## Unstage Changes

Unstage a file without deleting the work:

```bash
git restore --staged README.md
```

Unstage everything:

```bash
git restore --staged .
```

## Good Staging Habits

- Stage related changes together.
- Avoid mixing formatting-only edits with behavior changes.
- Review staged changes before committing.
- Use `git add -p` for precise commits.

## Common Mistakes

- Using `git add .` without checking what changed.
- Committing temporary notes or debug files by accident.
- Forgetting that unstaged changes are not included in the commit.
- Skipping `git diff --staged` before important commits.

## Quick Reference

| Task | Command |
| --- | --- |
| Stage file | `git add <file>` |
| Stage all | `git add .` |
| Stage pieces | `git add -p` |
| Review staged changes | `git diff --staged` |
| Unstage file | `git restore --staged <file>` |
