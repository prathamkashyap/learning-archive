# Linux Networking and SSH

## Context

Networking commands help separate app bugs from connection, DNS, port, or server-access problems.

## HTTP Checks

```bash
curl http://localhost:3000
curl -I https://example.com
curl -v https://example.com
wget https://example.com/file.zip
```

## DNS and Ports

```bash
ping example.com
nslookup example.com
dig example.com
ss -tulpn
lsof -i :3000
```

## SSH

```bash
ssh user@server
ssh -i ~/.ssh/key.pem user@server
ssh -p 2222 user@server
```

Copy files:

```bash
scp file.txt user@server:/home/user/
scp -r folder user@server:/home/user/
```

## Common Mistakes

- Debugging app code before checking if the port is listening.
- Forgetting security group or firewall rules on remote servers.
- Using the wrong SSH key permissions.
- Copying files to the wrong remote path.

## Quick Reference

| Need | Command |
| --- | --- |
| Check HTTP headers | `curl -I <url>` |
| Verbose request | `curl -v <url>` |
| DNS lookup | `dig <domain>` |
| Listening ports | `ss -tulpn` |
| SSH with key | `ssh -i key.pem user@host` |
| Copy file | `scp file user@host:/path` |
