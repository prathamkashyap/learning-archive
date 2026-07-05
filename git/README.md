# Git

Git is a distributed version control system used to track changes, collaborate safely, and maintain a history of project work.

## Notes

1. [Installation and Configuration](01-installation-and-configuration.md)
2. [Repository Lifecycle](02-repository-lifecycle.md)
3. [Staging Area](03-staging-area.md)
4. [Commits](04-commits.md)
5. [Branches](05-branches.md)
6. [Merge vs Rebase](06-merge-vs-rebase.md)
7. [Remote Repositories](07-remote-repositories.md)
8. [Undoing Changes](08-undoing-changes.md)
9. [.gitignore](09-gitignore.md)
10. [Useful Commands](10-useful-commands.md)
11. [Best Practices](11-best-practices.md)

## Core Mental Model

Git mainly moves changes between four places:

```text
Working directory -> Staging area -> Local repository -> Remote repository
```

- Working directory: files currently visible in the project folder.
- Staging area: the next commit being prepared.
- Local repository: committed history on the computer.
- Remote repository: shared copy hosted on a service such as GitHub.
