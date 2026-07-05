# Linux Processes, Services, and Packages

## Context

When an app is slow, stuck, or blocking a port, process commands are the fastest way to see what is happening.

## Processes

```bash
ps aux
ps aux | grep node
top
htop
kill <pid>
kill -9 <pid>
```

Use `kill -9` only when a normal signal does not work.

## Services

```bash
systemctl status nginx
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl enable nginx
journalctl -u nginx
journalctl -u nginx -f
```

## Package Managers

Debian/Ubuntu:

```bash
sudo apt update
sudo apt install package-name
sudo apt remove package-name
apt search package-name
```

Fedora:

```bash
sudo dnf install package-name
sudo dnf remove package-name
```

macOS Homebrew:

```bash
brew install package-name
brew uninstall package-name
brew update
brew upgrade
```

## Common Mistakes

- Killing the wrong process because the command was too broad.
- Restarting a service without checking logs.
- Forgetting `sudo` for system-level service changes.
- Installing packages without updating package metadata first.

## Quick Reference

| Need | Command |
| --- | --- |
| List processes | `ps aux` |
| Live process view | `top` or `htop` |
| Stop process | `kill <pid>` |
| Service logs | `journalctl -u <service> -f` |
| Install on Ubuntu | `sudo apt install <package>` |
