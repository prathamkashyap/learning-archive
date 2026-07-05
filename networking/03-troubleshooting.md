# Networking Troubleshooting

## Context

The goal is to narrow the failure quickly: DNS, routing, port, TLS, HTTP, authentication, or app behavior.

## Debug Flow

```bash
ping example.com
dig example.com
curl -I https://example.com
curl -v https://example.com
ss -tulpn
traceroute example.com
```

On macOS, `traceroute` is available by default. On Linux, it may need installation.

## Port Checks

```bash
ss -tulpn
lsof -i :3000
nc -vz localhost 3000
```

## curl Examples

```bash
curl -X GET https://api.example.com/users
curl -X POST https://api.example.com/users \
  -H "Content-Type: application/json" \
  -d '{"name":"Pratham"}'
curl -H "Authorization: Bearer TOKEN" https://api.example.com/me
```

## Wireshark Basics

Useful filters:

```text
http
dns
tcp.port == 443
ip.addr == 8.8.8.8
```

## Common Mistakes

- Skipping DNS checks.
- Forgetting a local firewall or cloud security group.
- Testing the wrong port.
- Sending JSON without `Content-Type: application/json`.

## Quick Reference

| Symptom | First checks |
| --- | --- |
| Domain fails | `dig`, `nslookup` |
| Port blocked | `ss`, `lsof`, `nc` |
| TLS issue | `curl -v` |
| API 401 | Token/header |
| API 500 | Server logs |
