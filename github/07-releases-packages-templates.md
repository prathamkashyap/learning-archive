# Releases, Packages, and Templates

## Context

These features matter when a repository becomes reusable. Releases mark stable points, templates speed up new repos, and packages publish build artifacts.

## Releases

Create releases from tags:

```bash
git tag v1.0.0
git push origin v1.0.0
```

Release notes usually include:

- Added.
- Changed.
- Fixed.
- Known issues.

## Packages

GitHub Packages can host:

- npm packages.
- Docker images.
- Maven packages.
- NuGet packages.

For Docker images, package names often look like:

```text
ghcr.io/username/image-name
```

## Repository Templates

Templates are useful when a repo structure should be reused. Enable from repository settings:

```text
Settings -> Template repository
```

## Common Mistakes

- Creating releases without meaningful notes.
- Tagging unstable commits.
- Publishing packages without documenting install/use steps.
- Making a template before the structure is actually stable.

## Quick Reference

| Need | Feature |
| --- | --- |
| Mark version | Release + tag |
| Publish artifact | Packages |
| Reuse repo structure | Template repository |
| Version command | `git tag v1.0.0` |
