# Learning Archive

![Last commit](https://img.shields.io/github/last-commit/prathamkashyap/learning-archive)
![Repo size](https://img.shields.io/github/repo-size/prathamkashyap/learning-archive)
![License](https://img.shields.io/github/license/prathamkashyap/learning-archive)
![Topics covered](https://img.shields.io/badge/topics-10-blue)

My version-controlled notebook for Git, GitHub, Markdown, terminal work, and the engineering basics I keep needing to revisit.

I started this because loose notes disappear exactly when I need them. This repo is meant to be the place I check when I forget a command, want to revise before interviews, or need to explain a workflow without guessing.

## Table of Contents

- [Workflow Map](#workflow-map)
- [Progress](#progress)
- [How I Use This](#how-i-use-this)
- [Topic Index](#topic-index)
- [Quick Commands](#quick-commands)
- [Repository Standards](#repository-standards)

## Workflow Map

```mermaid
flowchart LR
    A["Working directory"] --> B["Staging area"]
    B --> C["Local commit history"]
    C --> D["GitHub remote"]
    D --> E["Pull or fetch updates"]
    E --> A
```

## Progress

| Topic | Folder | Status | Current focus |
| --- | --- | --- | --- |
| Git | [git/](git/) | Complete | Daily workflow, branching, remotes, undoing mistakes |
| GitHub | [github/](github/) | Started | Repositories, profile, pull requests, Pages |
| Markdown | [markdown/](markdown/) | Started | Cheatsheet and README formatting |
| Linux | [linux/](linux/) | Planned | Terminal basics and permissions |
| VS Code | [vscode/](vscode/) | Planned | Setup, extensions, shortcuts |
| Docker | [docker/](docker/) | Planned | Images, containers, Dockerfiles, Compose |
| SQL | [sql/](sql/) | Planned | Queries, joins, schema design |
| Networking | [networking/](networking/) | Planned | HTTP, DNS, TCP/IP, ports |
| System Design | [system-design/](system-design/) | Planned | Scaling, caching, reliability |
| Interview | [interview/](interview/) | Planned | Revision checklists and practice |

## How I Use This

- When I forget a Git command, I start with [Git Useful Commands](git/10-useful-commands.md).
- Before pushing work, I check [Git Best Practices](git/11-best-practices.md).
- When I am revising, I read one folder in order instead of jumping between random notes.
- When I learn something the hard way, I add the mistake and the fix so I do not repeat it later.

## Topic Index

### Git

The Git section is the most complete section right now. It covers setup, staging, commits, branches, merge vs rebase, remotes, undo commands, `.gitignore`, command references, and best practices.

Start here: [git/README.md](git/README.md)

### GitHub

The GitHub section tracks the hosted workflow around repositories, profiles, pull requests, and GitHub Pages.

Start here: [github/README.md](github/README.md)

### Markdown

The Markdown section is for writing clean notes and READMEs that render well on GitHub.

Start here: [markdown/README.md](markdown/README.md)

### Planned Sections

Linux, VS Code, Docker, SQL, Networking, System Design, and Interview folders are present so the archive can grow in a predictable shape.

## Quick Commands

<details>
<summary>Git commands I check most often</summary>

```bash
git status
git add .
git commit -m "Describe the change"
git pull --rebase
git push
git switch -c docs/topic-name
git log --oneline --graph --decorate --all
git diff --staged
```

</details>

## Repository Standards

- Keep notes practical and searchable.
- Use one file per focused topic.
- Put commands near the context where they are useful.
- Add common mistakes, not just ideal paths.
- Use meaningful commits such as `Document branching workflow`.
- Avoid vague commits such as `update`, `changes`, or `final`.
