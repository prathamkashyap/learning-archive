# Pull Requests

## Context

A pull request is a review space for changes before they merge into the main branch. At first I thought it was only for teams, but it is useful even solo because it forces me to describe what changed and check the diff.

## Commands / Steps

Create a branch:

```bash
git switch -c docs/git-notes
```

Make commits, then push the branch:

```bash
git push -u origin docs/git-notes
```

Open a pull request on GitHub and include:

- What changed.
- Why it changed.
- How it was checked.
- Any follow-up work.

After merge, update local `main`:

```bash
git switch main
git pull
```

## Common Mistakes

- Opening a pull request with unrelated changes mixed together.
- Forgetting to pull the updated `main` after merging.
- Writing a PR description that only says "update".
- Not checking the Files changed tab before merge.

## Quick Reference

| Task | Command or place |
| --- | --- |
| Create branch | `git switch -c <branch>` |
| Push branch | `git push -u origin <branch>` |
| Review diff | Pull request Files changed tab |
| Update main | `git switch main` then `git pull` |
