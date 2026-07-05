# SQL Joins and Aggregation

## Context

Joins are where database queries start feeling real. I write the relationship first, then add filters after confirming the joined rows make sense.

## Joins

```sql
SELECT users.name, orders.id, orders.total
FROM users
INNER JOIN orders ON orders.user_id = users.id;
```

Join types:

| Join | Keeps |
| --- | --- |
| `INNER JOIN` | Matching rows only |
| `LEFT JOIN` | All left rows, matching right rows |
| `RIGHT JOIN` | All right rows, matching left rows |
| `FULL OUTER JOIN` | Rows from both sides |

Find users without orders:

```sql
SELECT users.id, users.name
FROM users
LEFT JOIN orders ON orders.user_id = users.id
WHERE orders.id IS NULL;
```

## Aggregation

```sql
SELECT user_id, COUNT(*) AS order_count, SUM(total) AS total_spent
FROM orders
GROUP BY user_id
HAVING COUNT(*) > 3;
```

## Common Mistakes

- Filtering a `LEFT JOIN` table in `WHERE` and accidentally turning it into an inner join.
- Selecting non-aggregated columns without grouping them.
- Using `WHERE` for aggregate filters instead of `HAVING`.
- Joining on the wrong key because column names look similar.

## Quick Reference

| Need | SQL |
| --- | --- |
| Count rows | `COUNT(*)` |
| Sum values | `SUM(amount)` |
| Average | `AVG(score)` |
| Group | `GROUP BY user_id` |
| Aggregate filter | `HAVING COUNT(*) > 1` |
