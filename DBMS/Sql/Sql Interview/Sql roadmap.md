
# SQL Roadmap

## 1. Introduction to SQL ⭐⭐⭐⭐

- What is SQL?
- DBMS vs RDBMS
- Database, Table, Row, Column
- Primary Key
- Foreign Key
- Candidate Key
- Composite Key
- Unique Key
- Super Key
- Alternate Key
- Constraints

---

## 2. SQL Commands ⭐⭐⭐⭐⭐

### DDL (Data Definition Language)

- CREATE
- ALTER
- DROP
- TRUNCATE
- RENAME

### DML (Data Manipulation Language)

- INSERT
- UPDATE
- DELETE

### DQL (Data Query Language)

- SELECT

### DCL (Data Control Language)

- GRANT
- REVOKE

### TCL (Transaction Control Language)

- COMMIT
- ROLLBACK
- SAVEPOINT

---

## 3. SELECT Statement ⭐⭐⭐⭐⭐

- SELECT
- DISTINCT
- WHERE
- ORDER BY
- LIMIT
- ALIAS
- BETWEEN
- IN
- LIKE
- IS NULL
- IS NOT NULL

---

## 4. Operators ⭐⭐⭐⭐

- Arithmetic
- Comparison
- Logical
- IN
- EXISTS
- ANY
- ALL

---

## 5. Aggregate Functions ⭐⭐⭐⭐⭐

- COUNT()
- SUM()
- AVG()
- MIN()
- MAX()

---

## 6. GROUP BY & HAVING ⭐⭐⭐⭐⭐

- GROUP BY
- HAVING
- WHERE vs HAVING

---

## 7. Joins ⭐⭐⭐⭐⭐ (Most Important)

- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- FULL OUTER JOIN
- CROSS JOIN
- SELF JOIN

---

## 8. Subqueries ⭐⭐⭐⭐⭐

- Single Row
- Multiple Row
- Correlated Subquery
- Nested Subquery
- EXISTS
- NOT EXISTS

---

## 9. Set Operators ⭐⭐⭐⭐

- UNION
- UNION ALL
- INTERSECT
- EXCEPT (MINUS)

---

## 10. String Functions ⭐⭐⭐⭐

- CONCAT()
- LENGTH()
- UPPER()
- LOWER()
- SUBSTRING()
- REPLACE()
- TRIM()

---

## 11. Date Functions ⭐⭐⭐⭐

- NOW()
- CURDATE()
- DATE_ADD()
- DATE_SUB()
- DATEDIFF()

---

## 12. Numeric Functions ⭐⭐⭐

- ROUND()
- CEIL()
- FLOOR()
- ABS()

---

## 13. Constraints ⭐⭐⭐⭐⭐

- PRIMARY KEY
- FOREIGN KEY
- UNIQUE
- CHECK
- DEFAULT
- NOT NULL

---

## 14. Views ⭐⭐⭐⭐

- CREATE VIEW
- UPDATE VIEW
- DROP VIEW

---

## 15. Indexes ⭐⭐⭐⭐

- Clustered Index
- Non-Clustered Index
- Composite Index

---

## 16. Normalization ⭐⭐⭐⭐⭐

- 1NF
- 2NF
- 3NF
- BCNF

---

## 17. Transactions ⭐⭐⭐⭐⭐

- ACID Properties
- COMMIT
- ROLLBACK
- SAVEPOINT

---

## 18. Stored Procedures ⭐⭐⭐⭐

- CREATE PROCEDURE
- Parameters
- CALL

---

## 19. Triggers ⭐⭐⭐⭐

- BEFORE INSERT
- AFTER INSERT
- BEFORE UPDATE
- AFTER DELETE

---

## 20. Window Functions ⭐⭐⭐⭐⭐ (Product Companies)

- ROW_NUMBER()
- RANK()
- DENSE_RANK()
- LEAD()
- LAG()
- NTILE()

---

## 21. Common Table Expressions (CTE) ⭐⭐⭐⭐

- WITH Clause
- Recursive CTE

---

## 22. Advanced SQL ⭐⭐⭐⭐

- CASE WHEN
- COALESCE()
- NULLIF()
- Pivot/Unpivot (Basics)

---

# Important Comparisons

|Comparison|Importance|
|---|---|
|DELETE vs TRUNCATE vs DROP|⭐⭐⭐⭐⭐|
|WHERE vs HAVING|⭐⭐⭐⭐⭐|
|UNION vs UNION ALL|⭐⭐⭐⭐⭐|
|INNER JOIN vs OUTER JOIN|⭐⭐⭐⭐⭐|
|CHAR vs VARCHAR|⭐⭐⭐⭐|
|Primary Key vs Unique Key|⭐⭐⭐⭐⭐|
|Clustered vs Non-Clustered Index|⭐⭐⭐⭐|
|RANK vs DENSE_RANK|⭐⭐⭐⭐⭐|
|Correlated vs Non-Correlated Subquery|⭐⭐⭐⭐|

---

# Most Asked Interview Questions

1. What is SQL?
2. DBMS vs RDBMS.
3. Types of SQL Commands.
4. Primary Key vs Foreign Key.
5. DELETE vs TRUNCATE vs DROP.
6. WHERE vs HAVING.
7. Explain all JOINs.
8. What is a Self Join?
9. What is a Cross Join?
10. What are Aggregate Functions?
11. GROUP BY vs ORDER BY.
12. UNION vs UNION ALL.
13. What is a Subquery?
14. What is a Correlated Subquery?
15. What is Normalization?
16. Explain ACID Properties.
17. What is an Index?
18. Clustered vs Non-Clustered Index.
19. What is a View?
20. What is a Stored Procedure?
21. What is a Trigger?
22. Explain Window Functions.
23. What is a CTE?
24. What is the difference between CHAR and VARCHAR?
25. What is the difference between EXISTS and IN?

---

# Practice Query Patterns

Practice writing queries for:

- Retrieve data (`SELECT`, `WHERE`)
- Sorting (`ORDER BY`)
- Filtering (`LIKE`, `BETWEEN`, `IN`)
- Aggregation (`COUNT`, `SUM`, `AVG`)
- Grouping (`GROUP BY`, `HAVING`)
- All types of `JOIN`
- Nested and correlated subqueries
- Window functions (`ROW_NUMBER`, `RANK`, `LAG`, `LEAD`)
- CTEs
- Transactions (`COMMIT`, `ROLLBACK`)
- Constraints and indexes

---

# Recommended Study Order

1. Introduction to SQL & RDBMS
2. SQL Commands (DDL, DML, DQL, DCL, TCL)
3. SELECT, WHERE, ORDER BY, LIMIT
4. Operators
5. Aggregate Functions
6. GROUP BY & HAVING
7. Joins
8. Subqueries
9. Set Operators
10. String, Date, and Numeric Functions
11. Constraints
12. Views
13. Indexes
14. Transactions & ACID
15. Normalization
16. Stored Procedures
17. Triggers
18. Window Functions
19. CTEs
20. Advanced SQL (`CASE`, `COALESCE`, etc.)

## For Your Interview Preparation

Since you're preparing for **Java Developer** and **Spring Boot** roles, I recommend mastering these first because they're asked most often:

- ⭐ SQL Commands (DDL, DML, DQL, TCL, DCL)
- ⭐ SELECT, WHERE, ORDER BY, LIMIT
- ⭐ Aggregate Functions
- ⭐ GROUP BY & HAVING
- ⭐ All JOINs
- ⭐ Subqueries
- ⭐ Constraints
- ⭐ Transactions & ACID
- ⭐ Indexes
- ⭐ Normalization
- ⭐ Window Functions

These topics alone cover the vast majority of SQL interview questions for placements and backend development roles.