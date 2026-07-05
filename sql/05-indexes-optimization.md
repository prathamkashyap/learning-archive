# SQL Indexes and Optimization

## Context

Indexes speed up reads but slow down writes and take storage. I add them for real query patterns, not just because a column looks important.

## Create Indexes

```sql
CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_orders_user_id ON orders(user_id);
CREATE INDEX idx_orders_created_at ON orders(created_at);
```

Composite index:

```sql
CREATE INDEX idx_orders_user_status ON orders(user_id, status);
```

## Explain Plans

PostgreSQL:

```sql
EXPLAIN ANALYZE
SELECT *
FROM orders
WHERE user_id = 42;
```

## Optimization Checklist

- Select only needed columns.
- Filter early with useful indexes.
- Check join keys.
- Avoid functions on indexed columns in filters when possible.
- Use pagination carefully for large offsets.
- Measure with `EXPLAIN`, not guesses.

## Common Mistakes

- Adding too many indexes.
- Expecting an index to help a query that does not filter or join on that column.
- Ignoring write cost.
- Optimizing tiny tables where a scan is already cheap.

## Quick Reference

| Need | Command |
| --- | --- |
| Create index | `CREATE INDEX name ON table(column);` |
| Composite index | `CREATE INDEX name ON table(a, b);` |
| Inspect plan | `EXPLAIN ANALYZE SELECT ...` |
| Remove index | `DROP INDEX index_name;` |
