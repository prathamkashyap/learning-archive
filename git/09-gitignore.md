# .gitignore

## Context

`.gitignore` keeps the repository from filling up with files that do not belong in history. The catch I had to learn is that it does not apply retroactively to files Git already tracks.

## Example

```gitignore
# Dependencies
node_modules/

# Environment variables
.env
.env.local

# Build output
dist/
build/

# Logs
*.log

# macOS
.DS_Store
```

## Important Behavior

`.gitignore` only affects untracked files. If a file is already tracked, adding it to `.gitignore` will not stop Git from tracking it.

Stop tracking a file but keep it locally:

```bash
git rm --cached file.txt
```

Stop tracking a folder but keep it locally:

```bash
git rm -r --cached folder-name/
```

Then commit the change:

```bash
git commit -m "Stop tracking generated files"
```

## Check Ignore Rules

```bash
git check-ignore -v file.txt
```

This shows which ignore rule is affecting a file.

## Good Ignore Targets

- Dependency directories.
- Build artifacts.
- Local environment files.
- Operating system metadata.
- Editor caches.
- Temporary logs.

Do not ignore source files, documentation, or configuration required to run the project unless there is a specific reason.

## Common Mistakes

- Adding `.env` after it has already been committed and assuming the secret is gone.
- Ignoring files the project actually needs.
- Forgetting that `.gitignore` patterns are relative to where the file lives.
- Not checking ignore behavior with `git check-ignore -v`.

## Quick Reference

| Task | Command or pattern |
| --- | --- |
| Ignore environment files | `.env` |
| Ignore build output | `dist/` |
| Stop tracking file | `git rm --cached <file>` |
| Stop tracking folder | `git rm -r --cached <folder>/` |
| Debug ignore rule | `git check-ignore -v <file>` |
