# Networking Cheatsheet

## Common Ports

| Port | Service |
| --- | --- |
| 22 | SSH |
| 53 | DNS |
| 80 | HTTP |
| 443 | HTTPS |
| 5432 | PostgreSQL |
| 6379 | Redis |
| 27017 | MongoDB |
| 3306 | MySQL |

## Most Used Commands

```bash
curl -I https://example.com
curl -v https://example.com
dig example.com
ping example.com
ss -tulpn
lsof -i :3000
traceroute example.com
ssh user@host
```

## Interview Questions

| Question | Short answer |
| --- | --- |
| TCP vs UDP? | TCP is reliable and ordered; UDP is connectionless and lower overhead. |
| HTTP vs HTTPS? | HTTPS is HTTP protected by TLS. |
| DNS purpose? | Resolves domain names to IP addresses. |
| What is a port? | A service endpoint on a host. |
| What does CDN do? | Caches/serves content near users. |
