# SQL Subqueries and Views

## Context

Subqueries and CTEs help break a query into readable steps. I use CTEs when a query gets too nested to debug quickly.

## Subquery

```sql
SELECT name
FROM users
WHERE id IN (
  SELECT user_id
  FROM orders
  WHERE total > 1000
);
```

## CTE

```sql
WITH high_value_orders AS (
  SELECT user_id, SUM(total) AS total_spent
  FROM orders
  GROUP BY user_id
  HAVING SUM(total) > 1000
)
SELECT users.name, high_value_orders.total_spent
FROM users
JOIN high_value_orders ON high_value_orders.user_id = users.id;
```

## Views

```sql
CREATE VIEW active_users AS
SELECT id, name, email
FROM users
WHERE status = 'active';
```

Use it:

```sql
SELECT *
FROM active_users;
```

## Common Mistakes

- Making a view and forgetting it does not store data like a table unless it is materialized.
- Nesting queries until nobody can read them.
- Repeating the same subquery instead of using a CTE.
- Assuming every database supports the exact same view features.

## Quick Reference

| Tool | Use when |
| --- | --- |
| Subquery | Small nested filter or calculation |
| CTE | Query needs named steps |
| View | Reusable query abstraction |
| Materialized view | Precomputed view for expensive reads |
