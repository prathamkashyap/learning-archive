# Walkthrough Guide

This guide explains how to use and grow the learning archive.

## 1. Start With the README

Open `README.md` first. It gives the purpose of the repository, the topic list, and the current progress status.

## 2. Study Git in Order

The Git section is the first complete section. Read it in this order:

1. Installation and Configuration
2. Repository Lifecycle
3. Staging Area
4. Commits
5. Branches
6. Merge vs Rebase
7. Remote Repositories
8. Undoing Changes
9. `.gitignore`
10. Useful Commands
11. Best Practices

Use `git/README.md` as the table of contents.

## 3. Practice Each Concept

For every command-based note:

1. Read the concept.
2. Run the safe commands in a test repository.
3. Write down anything confusing.
4. Update the note after understanding it better.

## 4. Add New Topic Notes

When adding a new topic:

1. Create a focused Markdown file.
2. Start with the concept.
3. Add common commands or examples.
4. Add mistakes to avoid.
5. Link the note from that topic's README or the root README.

## 5. Commit Changes Cleanly

Use meaningful commits:

```bash
git status
git add .
git commit -m "Add Linux terminal basics"
git push
```

Good commit examples:

```text
Add Git remote repository notes
Document Markdown table syntax
Add Docker container basics
Improve repository README
```

Avoid vague messages such as:

```text
update
final
changes
test
```

## 6. Keep the Archive Presentable

Before pushing:

```bash
git status
git diff --staged
```

Check that:

- The README progress table is accurate.
- New files are linked from the correct place.
- Notes are clear enough to revisit later.
- No secrets or temporary files are included.
