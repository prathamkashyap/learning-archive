# Shell Scripting and Aliases

## Context

Small shell scripts save repeated typing. I keep them boring and readable because future me has to debug them.

## Script Basics

```bash
#!/usr/bin/env bash
set -euo pipefail

echo "Running checks..."
git status --short
```

Run it:

```bash
chmod +x script.sh
./script.sh
```

## Variables and Arguments

```bash
name="archive"
echo "$name"
echo "First argument: $1"
```

## Loops

```bash
for file in *.md; do
  echo "$file"
done
```

## Aliases

```bash
alias gs='git status --short'
alias gl='git log --oneline --graph --decorate --all'
alias ll='ls -la'
```

Add aliases to shell config:

```bash
~/.zshrc
~/.bashrc
```

Reload:

```bash
source ~/.zshrc
```

## Common Mistakes

- Forgetting quotes around variables.
- Writing long scripts without `set -euo pipefail`.
- Adding aliases and forgetting to reload the shell.
- Making aliases too cryptic to remember.

## Quick Reference

| Need | Command |
| --- | --- |
| Make executable | `chmod +x script.sh` |
| Run script | `./script.sh` |
| Print variable | `echo "$name"` |
| Add alias | `alias gs='git status --short'` |
| Reload zsh config | `source ~/.zshrc` |
