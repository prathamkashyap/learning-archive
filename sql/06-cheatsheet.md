# SQL Cheatsheet

## Most Used

```sql
SELECT *
FROM table_name
WHERE condition
ORDER BY created_at DESC
LIMIT 10;
```

```sql
SELECT user_id, COUNT(*) AS count
FROM orders
GROUP BY user_id
HAVING COUNT(*) > 1;
```

## Query Reference

| Need | SQL |
| --- | --- |
| Read rows | `SELECT ... FROM ...` |
| Add row | `INSERT INTO ... VALUES ...` |
| Update rows | `UPDATE ... SET ... WHERE ...` |
| Delete rows | `DELETE FROM ... WHERE ...` |
| Join | `JOIN other ON other.id = table.other_id` |
| Group | `GROUP BY column` |
| Aggregate filter | `HAVING COUNT(*) > 1` |
| Transaction | `BEGIN; ... COMMIT;` |

## Things I Forget Often

- `WHERE` filters rows before grouping.
- `HAVING` filters groups after aggregation.
- `NULL` needs `IS NULL`.
- `COUNT(*)` counts rows; `COUNT(column)` skips nulls.
- Always check rows before destructive updates.

## Interview Questions

| Question | Short answer |
| --- | --- |
| Primary key vs foreign key? | Primary key identifies rows; foreign key references another table. |
| WHERE vs HAVING? | `WHERE` filters rows; `HAVING` filters grouped results. |
| Index trade-off? | Faster reads, slower writes, more storage. |
| ACID? | Atomicity, Consistency, Isolation, Durability. |
