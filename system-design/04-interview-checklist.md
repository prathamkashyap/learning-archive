# System Design Interview Checklist

## Context

This is the structure I want to follow under time pressure. The goal is not to draw a perfect system immediately. The goal is to ask the right questions and make trade-offs visible.

## Flow

1. Clarify requirements.
2. Define non-functional requirements.
3. Estimate scale.
4. Design APIs.
5. Sketch high-level architecture.
6. Choose data model and storage.
7. Add caching, queues, and scaling points.
8. Discuss failure modes.
9. Summarize trade-offs.

## Questions to Ask

| Area | Questions |
| --- | --- |
| Users | How many DAU/MAU? |
| Traffic | Reads vs writes? Peak QPS? |
| Data | Size, retention, consistency needs? |
| Latency | Real-time or eventually consistent? |
| Availability | What downtime is acceptable? |
| Security | Auth, privacy, rate limits? |

## Common Components

```text
Client -> CDN -> Load Balancer -> App Servers -> Cache -> Database
                                      |
                                      v
                                    Queue -> Workers
```

## Common Mistakes

- Designing before clarifying requirements.
- Forgetting reads vs writes.
- Drawing boxes without explaining trade-offs.
- Ignoring observability and failure recovery.

## Quick Reference

| Problem | Mention |
| --- | --- |
| Hot reads | CDN/cache |
| Heavy writes | Queue, partitioning |
| Database bottleneck | Indexes, replicas, sharding |
| Failure handling | Retries, timeouts, circuit breakers |
| Monitoring | Logs, metrics, traces, alerts |
