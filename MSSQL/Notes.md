# SQL Server Built-in Functions (MSSQL)

This document covers major built-in SQL Server functions with explanations and examples.

---

## 1. Aggregate Functions

Used to perform calculations across a set of rows.

| Function | Description | Example |
|----------|-------------|---------|
| `COUNT()` | Returns the number of items in a group | `SELECT COUNT(*) FROM Employees;` |
| `SUM()`   | Adds values | `SELECT SUM(Salary) FROM Employees;` |
| `AVG()`   | Calculates average | `SELECT AVG(Salary) FROM Employees;` |
| `MIN()`   | Finds minimum value | `SELECT MIN(HireDate) FROM Employees;` |
| `MAX()`   | Finds maximum value | `SELECT MAX(Salary) FROM Employees;` |

---

## 2. String Functions

Manipulate string data.

| Function | Description | Example |
|----------|-------------|---------|
| `LEN()`        | Returns string length | `SELECT LEN('Hello')` → `5` |
| `UPPER()`      | Converts to uppercase | `SELECT UPPER('sql')` → `'SQL'` |
| `LOWER()`      | Converts to lowercase | `SELECT LOWER('SQL')` → `'sql'` |
| `LEFT()`       | Extracts left part | `SELECT LEFT('abcdef', 3)` → `'abc'` |
| `RIGHT()`      | Extracts right part | `SELECT RIGHT('abcdef', 3)` → `'def'` |
| `SUBSTRING()`  | Extracts substring | `SELECT SUBSTRING('abcdef', 2, 3)` → `'bcd'` |
| `REPLACE()`    | Replaces substring | `SELECT REPLACE('abcabc', 'a', 'x')` → `'xbcxbc'` |
| `TRIM()`       | Trims spaces | `SELECT TRIM('  Hello ')` → `'Hello'` |
| `CONCAT()`     | Joins strings | `SELECT CONCAT('First', ' ', 'Name')` → `'First Name'` |

---

## 3. Date and Time Functions

Work with date/time values.

| Function | Description | Example |
|----------|-------------|---------|
| `GETDATE()`     | Current date/time | `SELECT GETDATE()` |
| `CURRENT_TIMESTAMP` | Same as GETDATE() | `SELECT CURRENT_TIMESTAMP` |
| `DATEADD()`     | Adds interval | `SELECT DATEADD(DAY, 7, '2025-07-01')` → `'2025-07-08'` |
| `DATEDIFF()`    | Difference between dates | `SELECT DATEDIFF(DAY, '2025-07-01', '2025-07-08')` → `7` |
| `YEAR()`        | Extracts year | `SELECT YEAR('2025-07-01')` → `2025` |
| `MONTH()`       | Extracts month | `SELECT MONTH('2025-07-01')` → `7` |
| `DAY()`         | Extracts day | `SELECT DAY('2025-07-01')` → `1` |

---

## 4. Mathematical Functions

Perform numeric calculations.

| Function | Description | Example |
|----------|-------------|---------|
| `ABS()`     | Absolute value | `SELECT ABS(-10)` → `10` |
| `CEILING()` | Rounds up | `SELECT CEILING(4.2)` → `5` |
| `FLOOR()`   | Rounds down | `SELECT FLOOR(4.9)` → `4` |
| `ROUND()`   | Rounds to decimal | `SELECT ROUND(3.14159, 2)` → `3.14` |
| `POWER()`   | Exponentiation | `SELECT POWER(2, 3)` → `8` |
| `SQRT()`    | Square root | `SELECT SQRT(16)` → `4` |
| `RAND()`    | Random number | `SELECT RAND()` |

---

## 5. Conversion Functions

Convert between data types.

| Function | Description | Example |
|----------|-------------|---------|
| `CAST()`       | Converts type | `SELECT CAST(123 AS VARCHAR)` → `'123'` |
| `CONVERT()`    | Converts with format | `SELECT CONVERT(VARCHAR, GETDATE(), 103)` → `'08/07/2025'` |
| `TRY_CAST()`   | Returns NULL on error | `SELECT TRY_CAST('abc' AS INT)` → `NULL` |
| `TRY_CONVERT()`| Like TRY_CAST | `SELECT TRY_CONVERT(INT, '123')` → `123` |

---

## 6. Logical and Conditional Functions

| Function | Description | Example |
|----------|-------------|---------|
| `ISNULL()`     | Replaces NULL | `SELECT ISNULL(NULL, 'Default')` → `'Default'` |
| `COALESCE()`   | Returns first non-NULL | `SELECT COALESCE(NULL, NULL, 'X')` → `'X'` |
| `IIF()`        | Inline IF | `SELECT IIF(1=1, 'Yes', 'No')` → `'Yes'` |
| `NULLIF()`     | Returns NULL if equal | `SELECT NULLIF(5, 5)` → `NULL` |

---

## 7. Window Functions

Used with `OVER()` clause to rank, count, or track values across partitions.

| Function | Description | Example |
|----------|-------------|---------|
| `ROW_NUMBER()`  | Row index | `ROW_NUMBER() OVER(ORDER BY Salary)` |
| `RANK()`        | Rank with gaps | `RANK() OVER(ORDER BY Salary DESC)` |
| `DENSE_RANK()`  | Rank without gaps | `DENSE_RANK() OVER(ORDER BY Salary DESC)` |
| `NTILE(n)`      | Distribute rows into n groups | `NTILE(4) OVER(ORDER BY Salary)` |
| `LEAD()`        | Next row's value | `LEAD(Salary) OVER(ORDER BY ID)` |
| `LAG()`         | Previous row's value | `LAG(Salary) OVER(ORDER BY ID)` |

---

## 8. System Functions

Provide server info or system metadata.

| Function | Description | Example |
|----------|-------------|---------|
| `@@VERSION`       | SQL Server version | `SELECT @@VERSION` |
| `SYSTEM_USER`     | Logged-in user | `SELECT SYSTEM_USER` |
| `NEWID()`         | Uniqueidentifier | `SELECT NEWID()` |
| `HOST_NAME()`     | Client machine name | `SELECT HOST_NAME()` |

---

## 9. JSON Functions (SQL Server 2016+)

| Function | Description | Example |
|----------|-------------|---------|
| `JSON_VALUE()` | Extract value | `SELECT JSON_VALUE('{"name":"Nandu"}', '$.name')` → `'Nandu'` |
| `ISJSON()`     | Valid JSON | `SELECT ISJSON('{"a":1}')` → `1` |
| `JSON_QUERY()` | Extract object or array | `SELECT JSON_QUERY('{"a":{"b":2}}', '$.a')` → `'{"b":2}'` |

---

## ✅ Notes

- Function availability may depend on SQL Server version.
- Always test `TRY_*()` functions to safely handle conversion errors.
- Use window functions with `OVER()` clause only.

---
