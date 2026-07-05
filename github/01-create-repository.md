# Create a GitHub Repository

## Context

This mattered to me because Git only becomes really useful when the project has a remote backup. The first confusing part was realizing that `git init` creates the local history, while GitHub creates the hosted copy. They are related, but they are not the same thing until I connect them with a remote.

## Commands / Steps

Create a repository on GitHub first, then connect it from the local project:

```bash
git remote add origin https://github.com/username/repository.git
git branch -M main
git push -u origin main
```

Check the connection:

```bash
git remote -v
```

If the remote URL is wrong:

```bash
git remote set-url origin https://github.com/username/correct-repository.git
```

## Common Mistakes

- Creating a repo on GitHub and forgetting to push local commits.
- Adding the wrong remote URL.
- Pushing before pulling when the GitHub repo already has commits.
- Confusing the repository name with the local folder name. They can match, but Git does not require it.

## Quick Reference

| Task | Command |
| --- | --- |
| Add remote | `git remote add origin <url>` |
| Check remote | `git remote -v` |
| Rename branch to main | `git branch -M main` |
| First push | `git push -u origin main` |
| Change remote URL | `git remote set-url origin <url>` |
