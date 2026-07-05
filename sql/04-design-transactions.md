# SQL Design, Constraints, and Transactions

## Context

Schema design decides which bugs the database prevents for me. Constraints are not decoration; they protect data when application code is wrong.

## Keys and Constraints

```sql
CREATE TABLE users (
  id BIGSERIAL PRIMARY KEY,
  email TEXT NOT NULL UNIQUE,
  name TEXT NOT NULL,
  created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
);
```

Foreign key:

```sql
CREATE TABLE orders (
  id BIGSERIAL PRIMARY KEY,
  user_id BIGINT NOT NULL REFERENCES users(id),
  total NUMERIC(10, 2) NOT NULL CHECK (total >= 0)
);
```

## Normalization

| Form | Main idea |
| --- | --- |
| 1NF | Atomic values, no repeating groups |
| 2NF | Non-key columns depend on the whole key |
| 3NF | Non-key columns do not depend on other non-key columns |

## Transactions

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 100
WHERE id = 1;

UPDATE accounts
SET balance = balance + 100
WHERE id = 2;

COMMIT;
```

Rollback:

```sql
ROLLBACK;
```

## ACID

| Letter | Meaning |
| --- | --- |
| Atomicity | All steps succeed or none do |
| Consistency | Constraints stay valid |
| Isolation | Concurrent transactions do not corrupt each other |
| Durability | Committed data survives failure |

## Common Mistakes

- Letting application code enforce rules the database should enforce.
- Forgetting indexes on foreign keys used in joins.
- Using floating point types for money.
- Holding transactions open longer than needed.

## Quick Reference

| Need | SQL |
| --- | --- |
| Primary key | `PRIMARY KEY` |
| Unique value | `UNIQUE` |
| Required value | `NOT NULL` |
| Validate range | `CHECK (total >= 0)` |
| Link table | `REFERENCES users(id)` |
