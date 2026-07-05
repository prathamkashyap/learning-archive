# GitHub Actions and Security

## Context

Actions show basic engineering discipline: run checks automatically instead of trusting memory. Security settings keep accidental mistakes from becoming public problems.

## Basic Workflow Shape

```yaml
name: Docs check

on:
  push:
  pull_request:

jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: echo "Run checks here"
```

## Secrets

Store tokens in:

```text
Repository -> Settings -> Secrets and variables -> Actions
```

Use a secret:

```yaml
env:
  API_TOKEN: ${{ secrets.API_TOKEN }}
```

Never commit `.env` files or tokens.

## Dependabot

Dependabot can open dependency update pull requests. Config usually lives at:

```text
.github/dependabot.yml
```

## Branch Protection

Useful rules:

- Require pull request before merge.
- Require status checks.
- Require branches to be up to date.
- Restrict force pushes.

## Common Mistakes

- Printing secrets in logs.
- Giving workflows unnecessary permissions.
- Adding branch protection before required checks exist.
- Ignoring failing checks and merging anyway.

## Quick Reference

| Need | Feature |
| --- | --- |
| Run checks | GitHub Actions |
| Store tokens | Actions secrets |
| Dependency updates | Dependabot |
| Protect `main` | Branch protection |
| Security alerts | Dependabot alerts |
