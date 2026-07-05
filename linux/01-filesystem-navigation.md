# Linux Filesystem and Navigation

## Context

Most command-line mistakes start with being in the wrong directory or targeting the wrong file. I check location first, then act.

## Navigation

```bash
pwd
ls
ls -la
cd /path/to/folder
cd ..
cd ~
cd -
```

## Files and Directories

```bash
mkdir notes
mkdir -p projects/app/src
touch README.md
cp file.txt copy.txt
cp -r folder folder-copy
mv old-name.md new-name.md
rm file.txt
rmdir empty-folder
```

Use `rm -r` only when the target is confirmed.

## Find Files

```bash
find . -name "*.md"
find . -type f -name "*.log"
find . -type d -name "node_modules"
```

If `locate` is installed:

```bash
locate filename
updatedb
```

## Common Mistakes

- Running a command from the wrong directory.
- Using relative paths without checking `pwd`.
- Deleting with a broad pattern.
- Forgetting hidden files exist until `ls -la`.

## Quick Reference

| Need | Command |
| --- | --- |
| Current folder | `pwd` |
| Detailed list | `ls -la` |
| Previous folder | `cd -` |
| Create nested folders | `mkdir -p a/b/c` |
| Find by name | `find . -name "file"` |
