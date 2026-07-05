# Scalability and Reliability

## Context

System design answers should be practical: requirements, rough scale, bottlenecks, trade-offs, then components. I avoid naming technologies before explaining why they are needed.

## Scaling

| Type | Meaning | Example |
| --- | --- | --- |
| Vertical | Bigger machine | More CPU/RAM |
| Horizontal | More machines | More app servers |

## Load Balancing

```text
Client -> Load balancer -> App server pool -> Database
```

Load balancer jobs:

- Spread traffic.
- Health check servers.
- Remove unhealthy instances.
- Support rolling deployments.

## Reliability Terms

| Term | Meaning |
| --- | --- |
| Availability | System is usable when needed |
| Reliability | System works correctly over time |
| Redundancy | Extra capacity/components |
| Failover | Switch to backup after failure |
| SLO | Target level of service |

## Common Mistakes

- Jumping to microservices before estimating traffic.
- Ignoring single points of failure.
- Forgetting operational concerns: logs, metrics, alerts.
- Optimizing for scale that the problem does not need.

## Quick Reference

| Problem | Common tool |
| --- | --- |
| Too much app traffic | Horizontal scaling + load balancer |
| Slow reads | Cache or read replica |
| Slow writes | Queue, partitioning, batching |
| Regional outage | Multi-region failover |
