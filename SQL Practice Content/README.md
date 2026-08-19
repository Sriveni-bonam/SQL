# SQL Practice

This repository contains my SQL syntax.

---

## 1. Select Queries

### Select Specific Columns

Query specific columns from a table.

```sql
SELECT column, another_column, ...
FROM mytable;
```


### Select All Columns

Query all columns from a table.

```sql
SELECT *
FROM mytable;
```
## 2. Queries with Constraints

Use the WHERE clause to filter rows based on one or more conditions.

```sql
SELECT column, another_column, ...
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR ...;
```
### Numerical Operators

| Operator | Condition | SQL Example |
|---|---|---|
| `=`, `!=`, `<`, `<=`, `>`, `>=` | Standard numerical operators | `col_name != 4` |
| `BETWEEN ... AND ...` | Number is within a range of two values (inclusive) | `col_name BETWEEN 1.5 AND 10.5` |
| `NOT BETWEEN ... AND ...` | Number is not within a range of two values (inclusive) | `col_name NOT BETWEEN 1 AND 10` |
| `IN (...)` | Number exists in a list | `col_name IN (2, 4, 6)` |
| `NOT IN (...)` | Number does not exist in a list | `col_name NOT IN (1, 3, 5)` |

### String Comparison and Pattern Matching

Use these operators to filter rows based on string values and patterns.

| Operator | Condition | SQL Example |
|----------|-----------|-------------|
| `=` | Exact string comparison | `col_name = 'abc'` |
| `!=` or `<>` | Exact string inequality comparison | `col_name != 'abcd'` |
| `LIKE` | Matches a specified pattern | `col_name LIKE 'ABC'` |
| `NOT LIKE` | Excludes a specified pattern | `col_name NOT LIKE 'ABCD'` |
| `%` | Matches zero or more characters | `col_name LIKE '%AT%'` |
| `_` | Matches exactly one character | `col_name LIKE 'AN_'` |
| `IN (...)` | String exists in a list | `col_name IN ('A', 'B', 'C')` |
| `NOT IN (...)` | String does not exist in a list | `col_name NOT IN ('D', 'E', 'F')` |

## 3. Filtering and sorting Query results

### DISTINCT:
DISTINCT removes duplicate columns.

Select query with unique results:

```sql
SELECT DISTINCT column, another_column, …
FROM mytable
WHERE condition(s);
```

### ORDER BY:
ORDER BY clause is specified, each row is sorted alpha-numerically based on the specified column's value.

Select query with ordered results:

```sql
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;
```

### LIMIT:
LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.

Select query with limited rows:

```sql
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```
