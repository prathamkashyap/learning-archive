# Git Commits

## Context

Commits are the part of Git that make the learning history visible. I want each commit in this archive to explain one useful step, not just say that files changed.

## What a Commit Is

A commit is a saved snapshot of staged changes. It includes:

- A unique identifier.
- The author.
- The date.
- A commit message.
- A pointer to the previous commit.

## Create a Commit

```bash
git add README.md
git commit -m "Improve repository README"
```

## Commit Message Style

Good commit messages describe the reason or result of the change:

```text
Add Git installation notes
Document branching workflow
Improve repository README
```

Weak commit messages are vague:

```text
update
changes
final
test
```

## View Commit History

```bash
git log
git log --oneline
git log --oneline --graph --decorate --all
```

## Inspect a Commit

```bash
git show <commit-hash>
```

## Amend the Latest Commit

Use amend when the latest commit needs a small correction and has not been shared yet:

```bash
git add README.md
git commit --amend
```

To only change the message:

```bash
git commit --amend -m "Better commit message"
```

Avoid amending commits that other people may already have pulled unless the team agrees.

## Commit Size

A good commit should be one logical unit of work. It does not need to be tiny, but it should be easy to explain.

## Common Mistakes

- Writing vague messages like `update`.
- Making one giant commit that mixes unrelated topics.
- Amending a commit after it has already been shared.
- Forgetting to inspect the staged diff before committing.

## Quick Reference

| Task | Command |
| --- | --- |
| Commit staged changes | `git commit -m "Message"` |
| View history | `git log --oneline` |
| Inspect commit | `git show <hash>` |
| Amend latest commit | `git commit --amend` |
| Review before commit | `git diff --staged` |
