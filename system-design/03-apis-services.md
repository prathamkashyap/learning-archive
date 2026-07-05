# APIs and Services

## Context

APIs are contracts. The design should make the client workflow clear and keep server-side changes from breaking users unexpectedly.

## REST

```http
GET /users/42
POST /users
PATCH /users/42
DELETE /users/42
```

REST tips:

- Use nouns for resources.
- Use HTTP methods for actions.
- Return useful status codes.
- Version APIs when breaking changes are likely.

## GraphQL

GraphQL lets clients request specific fields:

```graphql
query {
  user(id: "42") {
    id
    name
    orders {
      id
      total
    }
  }
}
```

## Monolith vs Microservices

| Architecture | Strength | Risk |
| --- | --- | --- |
| Monolith | Simple deployment and debugging | Can grow tightly coupled |
| Microservices | Independent scaling and ownership | Distributed complexity |

## API Reliability

- Rate limits.
- Idempotency keys for retries.
- Pagination for large lists.
- Request IDs for tracing.
- Backward-compatible response changes.

## Common Mistakes

- Using microservices without team or scale reasons.
- Returning inconsistent error shapes.
- Forgetting pagination.
- Making retries unsafe for payment or order APIs.

## Quick Reference

| Need | Pattern |
| --- | --- |
| Stable external API | Versioning |
| Large list | Pagination |
| Retry safely | Idempotency key |
| Debug request path | Correlation/request ID |
| Different clients need different fields | GraphQL |
