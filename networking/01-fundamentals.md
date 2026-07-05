# Network Fundamentals

## Context

Networking gets easier when I separate the layers: addressing, transport, application protocol, and security. Most debugging starts by asking which layer failed.

## OSI Model

| Layer | Name | Example |
| --- | --- | --- |
| 7 | Application | HTTP, DNS, SSH |
| 6 | Presentation | TLS, encoding |
| 5 | Session | Session management |
| 4 | Transport | TCP, UDP |
| 3 | Network | IP, routing |
| 2 | Data link | Ethernet, Wi-Fi |
| 1 | Physical | Cables, radio |

## TCP/IP Model

| Layer | Examples |
| --- | --- |
| Application | HTTP, DNS, SSH |
| Transport | TCP, UDP |
| Internet | IP, ICMP |
| Link | Ethernet, Wi-Fi |

## IP, Ports, Routing

```text
IP address = machine/location
Port = application/service on that machine
Protocol = rules for communication
```

Common checks:

```bash
ip addr
ip route
ss -tulpn
```

## NAT and VPN

- NAT maps private addresses to public addresses.
- VPN creates an encrypted tunnel to another network.
- CDN serves content from locations closer to users.

## Common Mistakes

- Saying "the internet is down" before checking DNS, route, and port separately.
- Confusing IP address with port.
- Assuming TCP and UDP behave the same.
- Forgetting NAT can hide private network addresses.

## Quick Reference

| Concept | Meaning |
| --- | --- |
| TCP | Reliable connection-oriented transport |
| UDP | Faster connectionless transport |
| IP | Addressing and routing |
| Port | Service endpoint on a host |
| NAT | Private-to-public address translation |
