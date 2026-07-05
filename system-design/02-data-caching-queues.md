# Data, Caching, and Queues

## Context

Most system design trade-offs show up around data: where it lives, how fast it is read, how consistent it must be, and what happens when traffic spikes.

## CAP Theorem

| Letter | Meaning |
| --- | --- |
| Consistency | Every read gets the latest write |
| Availability | Every request gets a non-error response |
| Partition tolerance | System continues despite network splits |

In a network partition, distributed systems usually trade consistency against availability.

## Replication and Sharding

| Pattern | Use |
| --- | --- |
| Replication | Copies data to improve reads and availability |
| Sharding | Splits data across nodes to scale writes/storage |

## Caching

Common cache locations:

- Browser cache.
- CDN.
- Application cache.
- Database query cache.
- Redis or Memcached.

Cache patterns:

| Pattern | Idea |
| --- | --- |
| Cache-aside | App reads/writes cache manually |
| Write-through | Write cache and database together |
| Write-behind | Write cache first, database later |

## Queues and Pub/Sub

| Tool | Use |
| --- | --- |
| Queue | Work processed by one consumer |
| Pub/Sub | Event broadcast to many subscribers |

Use queues for:

- Email sending.
- Image/video processing.
- Webhooks.
- Retryable background jobs.

## Common Mistakes

- Adding cache without an invalidation plan.
- Ignoring duplicate message handling.
- Assuming replicas have zero lag.
- Sharding before the data volume requires it.

## Quick Reference

| Need | Component |
| --- | --- |
| Fast repeated reads | Cache |
| Read scaling | Read replica |
| Write scaling | Sharding or queue |
| Async work | Queue |
| Event fanout | Pub/Sub |
