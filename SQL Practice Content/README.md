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
## 4. Database normalization

Database normalization is useful because it minimizes duplicate data in any single table, and allows for data in the database to grow independently of each other.

## Multi-table queries with JOINs:

### INNER JOIN:

Returns only the rows that have matching values in both tables.Used when you need to retrieve records with matching values in both tables. Commonly used for combining data that is related through a foreign key.

Select query with INNER JOIN on multiple tables:

```sql
SELECT column, another_table_column, …
FROM mytable
INNER JOIN another_table 
    ON mytable.id = another_table.id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

### OUTER JOIN:

An OUTER JOIN in SQL combines rows from two or more tables and retains unmatched records by filling missing data with NULL values.

Select query with OUTER JOIN on multiple tables:

```sql
SELECT column, another_column, …
FROM mytable
INNER/LEFT/RIGHT/FULL JOIN another_table 
    ON mytable.id = another_table.matching_id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;
```
### LEFT JOIN:

Returns all rows from the left table and the matched rows from the right table. Rows in the left table with no match in the right table will contain NULL.	Useful for retrieving all records from the left table, with the matching data in the right table, if available. Often used when you need to find all entries in one table and see if they have corresponding entries in another.

### RIGHT JOIN:

Returns all rows from the right table and the matched rows from the left table. Rows in the right table with no match in the left table will contain NULL.	Similar to LEFT JOIN but focuses on the right table. Used when you need all records from the right table whether or not they have matches in the left table.

### Full JOIN:

Returns all rows when there is a match in either left or right table records. If there is no match, the result is NULL on the side that does not have a match.	Useful for combining data that exists in either of the tables and capturing unmatched data from both tables.

### SELF JOIN:

A join in which a table is joined with itself.	Employed when you need to compare rows within the same table, such as finding relationships in hierarchical data or comparing values in various rows.


## 5. NULL/ not NULL values:

Select query with constraints on NULL values:

```sql
SELECT column, another_column, …
FROM mytable
WHERE column IS/IS NOT NULL
AND/OR another_condition
AND/OR …;
```

## 6. Queries with aggregates:

Select query with aggregate functions over all rows:

```sql
SELECT AGG_FUNC(column_or_expression) AS aggregate_description, …
FROM mytable
WHERE constraint_expression;
```

### Numerical Operators

| Operator | Condition | SQL Example |
|---|---|---|
| `=`, `!=`, `<`, `<=`, `>`, `>=` | Standard numerical operators | `col_name != 4` |
| `BETWEEN ... AND ...` | Number is within a range of two values (inclusive) | `col_name BETWEEN 1.5 AND 10.5` |
| `NOT BETWEEN ... AND ...` | Number is not within a range of two values (inclusive) | `col_name NOT BETWEEN 1 AND 10` |
| `IN (...)` | Number exists in a list | `col_name IN (2, 4, 6)` |
| `NOT IN (...)` | Number does not exist in a list | `col_name NOT IN (1, 3, 5)` |
