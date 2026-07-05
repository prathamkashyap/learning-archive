# Contribution Workflow

## Context

Even for a personal repo, a clean contribution workflow makes the project easier to review. For team projects, it prevents surprise changes on `main`.

## Fork Flow

```bash
git clone https://github.com/username/repository.git
git remote -v
git switch -c docs/improve-notes
git add .
git commit -m "Improve Docker notes"
git push -u origin docs/improve-notes
```

Open a pull request from the branch.

## Code Owners

`CODEOWNERS` can request reviewers automatically:

```text
*.md @username
/docker/ @username
```

Common location:

```text
.github/CODEOWNERS
```

## Review Checklist

- Does the change match the issue or goal?
- Are files named clearly?
- Are links valid?
- Are commands correct?
- Is the commit message meaningful?

## Common Mistakes

- Pushing directly to `main` on shared projects.
- Mixing unrelated changes in one PR.
- Leaving review comments unresolved.
- Forgetting to update docs after changing behavior.

## Quick Reference

| Need | Action |
| --- | --- |
| External contribution | Fork + PR |
| Internal contribution | Branch + PR |
| Auto reviewers | CODEOWNERS |
| Safe main branch | Branch protection |
