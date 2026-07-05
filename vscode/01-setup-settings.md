# VS Code Setup and Settings

## Context

I want VS Code to stay predictable across projects. Workspace settings should be project-specific; user settings should be personal defaults.

## Useful Extensions

| Extension type | Use |
| --- | --- |
| GitLens | Git history and blame |
| ESLint | JavaScript/TypeScript linting |
| Prettier | Formatting |
| Docker | Dockerfile and Compose support |
| Markdown All in One | Markdown editing |
| SQLTools | Database exploration |

## Settings

Open settings JSON:

```text
Command Palette -> Preferences: Open User Settings (JSON)
```

Example:

```json
{
  "editor.formatOnSave": true,
  "editor.tabSize": 2,
  "files.trimTrailingWhitespace": true,
  "terminal.integrated.defaultProfile.osx": "zsh"
}
```

Workspace settings live in:

```text
.vscode/settings.json
```

## Profiles

Profiles are useful when I want different extension/settings sets for web, Python, docs, or interviews.

## Common Mistakes

- Putting personal settings into project workspace settings.
- Installing too many extensions and slowing the editor.
- Enabling formatters that fight each other.
- Forgetting workspace settings override user settings.

## Quick Reference

| Need | Where |
| --- | --- |
| User settings | Command Palette settings JSON |
| Project settings | `.vscode/settings.json` |
| Profiles | Manage menu -> Profiles |
| Extensions | Extensions sidebar |
