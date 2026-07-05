# Linux Permissions and Ownership

## Context

Permissions explain why a script refuses to run, why a server cannot read a file, or why a deploy user cannot write to a directory.

## Read Permission Bits

```text
-rwxr-xr--
```

| Position | Meaning |
| --- | --- |
| First char | File type |
| 1-3 | Owner permissions |
| 4-6 | Group permissions |
| 7-9 | Others permissions |

| Symbol | Meaning |
| --- | --- |
| `r` | Read |
| `w` | Write |
| `x` | Execute |

## chmod

```bash
chmod +x script.sh
chmod 644 file.txt
chmod 755 script.sh
chmod -R 755 folder
```

Numeric modes:

| Mode | Meaning | Common use |
| --- | --- | --- |
| `600` | Owner read/write | Private keys |
| `644` | Owner write, everyone read | Normal files |
| `755` | Owner write, everyone execute | Scripts/directories |
| `777` | Everyone everything | Avoid unless temporary debugging |

## chown

```bash
sudo chown user file.txt
sudo chown user:group file.txt
sudo chown -R user:group folder
```

## Common Mistakes

- Using `chmod 777` instead of understanding the real permission issue.
- Forgetting directories need execute permission to be entered.
- Changing ownership recursively on the wrong folder.
- Making SSH private keys too open.

## Quick Reference

| Need | Command |
| --- | --- |
| Make script executable | `chmod +x script.sh` |
| Normal file mode | `chmod 644 file` |
| Executable mode | `chmod 755 script.sh` |
| Change owner | `sudo chown user file` |
| Change owner and group | `sudo chown user:group file` |
