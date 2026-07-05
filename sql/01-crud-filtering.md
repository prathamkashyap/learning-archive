# SQL CRUD and Filtering

## Context

Most SQL work starts with reading data carefully. I prefer writing the `SELECT` version first, checking the rows, then turning it into an `UPDATE` or `DELETE`.

## SELECT

```sql
SELECT id, name, email
FROM users;
```

Filter and sort:

```sql
SELECT *
FROM users
WHERE status = 'active'
ORDER BY created_at DESC
LIMIT 10;
```

## INSERT

```sql
INSERT INTO users (name, email, status)
VALUES ('Pratham', 'pratham@example.com', 'active');
```

## UPDATE

```sql
UPDATE users
SET status = 'inactive'
WHERE id = 42;
```

## DELETE

```sql
DELETE FROM users
WHERE id = 42;
```

## Common Mistakes

- Running `UPDATE` or `DELETE` without `WHERE`.
- Using `SELECT *` in production queries without needing every column.
- Forgetting `NULL` needs `IS NULL`, not `= NULL`.
- Assuming `ORDER BY` is optional when result order matters.

## Quick Reference

| Need | SQL |
| --- | --- |
| Filter | `WHERE status = 'active'` |
| Null check | `WHERE deleted_at IS NULL` |
| Sort | `ORDER BY created_at DESC` |
| Limit rows | `LIMIT 10` |
| Pattern match | `WHERE name LIKE 'A%'` |
