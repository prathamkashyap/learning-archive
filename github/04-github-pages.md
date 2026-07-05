# GitHub Pages

## Context

GitHub Pages can turn notes or project docs into a small website. For this archive, the raw Markdown files are still the source of truth, but a Pages site can make browsing easier with search and navigation.

## Commands / Steps

For a simple static site, GitHub Pages can publish from:

- The `main` branch.
- A `/docs` folder.
- A GitHub Actions workflow.

For this repository, `mkdocs.yml` is included so the notes can become a MkDocs Material site later:

```bash
mkdocs serve
mkdocs build
```

The source Markdown files stay in the same folders, so there is no duplicate copy to maintain.

## Common Mistakes

- Publishing generated files without knowing where they came from.
- Maintaining two separate versions of the same notes.
- Forgetting that GitHub Pages settings must be enabled in the repository.
- Using absolute local links that work on one computer but not on GitHub.

## Quick Reference

| Task | Command or place |
| --- | --- |
| Local preview | `mkdocs serve` |
| Build site | `mkdocs build` |
| Site config | `mkdocs.yml` |
| Enable Pages | GitHub repository settings |
