# Markdown Cheatsheet

## Context

Markdown is easy to start, but I kept forgetting the exact syntax for tables, links, code blocks, and collapsible sections. This file is the quick lookup so I can write better notes without breaking flow.

## Commands / Steps

Headings:

```markdown
# H1
## H2
### H3
```

Lists:

```markdown
- Item
- Item

1. First
2. Second
```

Links and images:

```markdown
[GitHub](https://github.com)
![Alt text](image.png)
```

Code:

````markdown
```bash
git status
```
````

Tables:

```markdown
| Command | Purpose |
| --- | --- |
| `git status` | Show repository state |
```

Collapsible details:

```html
<details>
<summary>More commands</summary>

Content goes here.

</details>
```

## Common Mistakes

- Forgetting the blank line before or after lists and code blocks.
- Using inconsistent heading levels.
- Putting huge command lists directly in the README instead of using `<details>`.
- Writing link text like "click here" instead of naming the destination.

## Quick Reference

| Element | Syntax |
| --- | --- |
| Heading | `## Heading` |
| Bold | `**text**` |
| Inline code | `` `code` `` |
| Link | `[label](https://example.com)` |
| Image | `![alt](path)` |
| Table divider | `| --- | --- |` |
| Task list | `- [ ] Task` |
