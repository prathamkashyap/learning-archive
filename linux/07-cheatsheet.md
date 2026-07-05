# Linux Cheatsheet

## Most Used

```bash
pwd
ls -la
cd ..
mkdir -p folder/subfolder
find . -name "*.md"
grep -R "text" .
chmod +x script.sh
ps aux
kill <pid>
curl -I https://example.com
ssh user@host
```

## Command Reference

| Area | Command |
| --- | --- |
| Navigation | `pwd`, `cd`, `ls -la` |
| Files | `touch`, `cp`, `mv`, `rm` |
| Search | `find`, `grep`, `locate` |
| Text | `awk`, `sed`, `sort`, `uniq` |
| Archives | `tar`, `zip`, `unzip` |
| Permissions | `chmod`, `chown` |
| Processes | `ps`, `top`, `htop`, `kill` |
| Network | `curl`, `wget`, `ss`, `dig` |
| Remote | `ssh`, `scp` |
| Services | `systemctl`, `journalctl` |

## Interview Questions

| Question | Short answer |
| --- | --- |
| What does `chmod 755` mean? | Owner can read/write/execute; group and others can read/execute. |
| `grep` vs `find`? | `grep` searches content; `find` searches paths and metadata. |
| What is a process? | A running instance of a program. |
| Why use SSH keys? | Safer authentication than reusable passwords. |
