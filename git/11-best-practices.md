# Git Best Practices

## Context

These are the habits I want to build while the repository is still small. If I practice clean commits and clear docs here, the same workflow will feel natural in larger projects.

## Commit Practices

- Make each commit one logical unit of work.
- Write clear commit messages.
- Review staged changes before committing.
- Avoid committing secrets, tokens, passwords, or private keys.
- Do not commit generated dependency folders such as `node_modules/`.

## Branch Practices

- Create branches for features, fixes, documentation, and experiments.
- Keep branch names short and descriptive.
- Update your branch regularly when working with others.
- Delete branches after they are merged.

## Collaboration Practices

- Pull before starting work on an active shared branch.
- Prefer pull requests for reviewable changes.
- Resolve conflicts carefully and test after resolving them.
- Avoid force-pushing shared branches unless the team has agreed.

## History Practices

- Use merge when preserving collaboration history matters.
- Use rebase for cleaning up local feature branches.
- Use revert for pushed commits that need to be undone.
- Use reset mostly for local, unpublished work.

## Documentation Practices

- Document commands with context, not just raw command lists.
- Include examples that explain when a command should be used.
- Keep notes concise enough to revisit quickly.
- Update old notes when your understanding improves.

## Safety Checklist Before Pushing

```bash
git status
git diff --staged
git log --oneline --max-count=5
```

Ask:

- Does this commit contain only related changes?
- Is the message clear?
- Are there secrets or generated files included by mistake?
- Does the project still run or read correctly?

## Common Mistakes

- Treating Git as a backup button instead of a history tool.
- Mixing unrelated edits because they happened at the same time.
- Force-pushing without understanding who else might be affected.
- Letting documentation fall behind the actual folder structure.

## Quick Reference

| Habit | Why it helps |
| --- | --- |
| Small logical commits | Easier review and rollback |
| Clear messages | Better history |
| Branches for work | Keeps `main` stable |
| Pull before push | Reduces remote conflicts |
| Review staged diff | Catches accidental files |
