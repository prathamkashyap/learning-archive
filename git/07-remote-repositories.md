# Remote Repositories

## Context

Remotes are what connect my local repository to GitHub. The main lesson for me was that local commits and GitHub commits can drift apart, which is why fetch, pull, rebase, and push exist.

## What a Remote Is

A remote is a version of the repository hosted somewhere else, usually on GitHub, GitLab, or Bitbucket.

The default remote name is usually `origin`.

## Check Remotes

```bash
git remote -v
```

## Add a Remote

```bash
git remote add origin https://github.com/username/repository.git
```

## Change a Remote URL

```bash
git remote set-url origin https://github.com/username/new-repository.git
```

## Fetch, Pull, and Push

Fetch remote updates without merging:

```bash
git fetch
```

Pull remote changes into the current branch:

```bash
git pull
```

Push local commits:

```bash
git push
```

Push a new branch and set upstream:

```bash
git push -u origin branch-name
```

## Tracking Branches

Check branch tracking information:

```bash
git branch -vv
```

Set upstream manually:

```bash
git branch --set-upstream-to=origin/main main
```

## Non-Fast-Forward Push

A non-fast-forward rejection means the remote branch contains commits you do not have locally.

Typical fix:

```bash
git pull --rebase
git push
```

This brings remote work into your local history before pushing your own commits.

## Common Mistakes

- Assuming `origin` is magic. It is just a remote name.
- Pushing to the wrong repository URL.
- Ignoring non-fast-forward errors instead of pulling first.
- Forgetting `-u` on the first push of a new branch.

## Quick Reference

| Task | Command |
| --- | --- |
| Show remotes | `git remote -v` |
| Add remote | `git remote add origin <url>` |
| Change remote | `git remote set-url origin <url>` |
| Fetch | `git fetch` |
| Pull with rebase | `git pull --rebase` |
| Push branch | `git push -u origin <branch>` |
