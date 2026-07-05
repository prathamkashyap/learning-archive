# VS Code Debugging, Tasks, and Snippets

## Context

Debug config is worth writing when I run the same command repeatedly. It also makes projects easier to explain because the run/debug path is documented.

## launch.json

Example Node debug config:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Run app",
      "program": "${workspaceFolder}/src/index.js"
    }
  ]
}
```

## tasks.json

Example task:

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Run tests",
      "type": "shell",
      "command": "npm test",
      "group": "test"
    }
  ]
}
```

## Snippets

Open:

```text
Command Palette -> Snippets: Configure User Snippets
```

Example:

```json
{
  "Markdown Note": {
    "prefix": "note",
    "body": [
      "## Context",
      "",
      "## Commands",
      "",
      "## Common Mistakes"
    ]
  }
}
```

## Common Mistakes

- Hardcoding absolute local paths.
- Committing personal debug configs that do not work for others.
- Creating tasks that duplicate package scripts without a reason.
- Forgetting to name configs clearly.

## Quick Reference

| File | Purpose |
| --- | --- |
| `.vscode/settings.json` | Workspace editor settings |
| `.vscode/launch.json` | Debug configurations |
| `.vscode/tasks.json` | Repeatable commands |
| User snippets | Reusable text templates |
