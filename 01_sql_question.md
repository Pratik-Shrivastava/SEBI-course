# 📘 SQL Study Material — 50 Questions & Answers

> A curated list of SQL theory questions and answers for quick study and revision.

---

### 1. Which command permanently removes all rows from a table but keeps its structure?
**A)** DELETE  
**B)** DROP  
**C)** TRUNCATE  
**D)** REMOVE  
✅ **Answer:** C — TRUNCATE removes all data but preserves the table schema.

---

### 2. What is the main difference between DELETE and TRUNCATE?
**A)** DELETE is DDL; TRUNCATE is DML  
**B)** DELETE removes structure; TRUNCATE removes schema  
**C)** DELETE can have WHERE; TRUNCATE cannot  
**D)** Both are identical  
✅ **Answer:** C — TRUNCATE cannot have WHERE; DELETE can.

---

### 3. Which keyword is used to rename a column in a table?
**A)** CHANGE COLUMN  
**B)** RENAME TO  
**C)** MODIFY  
**D)** ALTER TABLE … RENAME COLUMN  
✅ **Answer:** D — Standard syntax to rename columns.

---

### 4. Which SQL clause combines rows from two or more tables based on a related column?
**A)** JOIN  
**B)** UNION  
**C)** MERGE  
**D)** LINK  
✅ **Answer:** A — JOIN combines rows using common fields.

---

### 5. The INNER JOIN returns:
**A)** All rows from both tables  
**B)** Only matching rows  
**C)** Unmatched rows only  
**D)** Cross combination of rows  
✅ **Answer:** B — INNER JOIN filters unmatched pairs.

---

### 6. Which join returns all rows from the left table and matching rows from the right table?
**A)** INNER JOIN  
**B)** LEFT OUTER JOIN  
**C)** RIGHT OUTER JOIN  
**D)** FULL OUTER JOIN  
✅ **Answer:** B — LEFT OUTER JOIN includes unmatched left rows.

---

### 7. In SQL, the FULL OUTER JOIN returns:
**A)** Only matches  
**B)** All rows when there is a match in one of the tables  
**C)** Only right table records  
**D)** Duplicates only  
✅ **Answer:** B — Combines matched and unmatched from both sides.

---

### 8. The aggregate function COUNT(*) returns:
**A)** Number of columns  
**B)** Number of rows  
**C)** Number of NULLs  
**D)** Sum of numeric columns  
✅ **Answer:** B — Counts all rows including NULL values.

---

### 9. Which SQL statement creates a virtual table?
**A)** CREATE TABLE  
**B)** CREATE VIEW  
**C)** SELECT INTO  
**D)** CREATE INDEX  
✅ **Answer:** B — A VIEW is a virtual table.

---

### 10. A VIEW can be based on:
**A)** One table only  
**B)** Multiple tables using joins  
**C)** Temporary tables only  
**D)** Data dictionary only  
✅ **Answer:** B — Views can combine multiple tables.

---

### 11. Which keyword removes a view from the database?
**A)** DELETE VIEW  
**B)** TRUNCATE VIEW  
**C)** DROP VIEW  
**D)** REMOVE VIEW  
✅ **Answer:** C — DROP VIEW removes a view definition.

---

### 12. The UPDATE statement modifies:
**A)** Table structure  
**B)** Existing records  
**C)** Database  
**D)** View definition  
✅ **Answer:** B — It updates data in existing rows.

---

### 13. Which clause is mandatory in an UPDATE query to avoid modifying all rows?
**A)** HAVING  
**B)** WHERE  
**C)** ORDER BY  
**D)** LIMIT  
✅ **Answer:** B — WHERE filters which rows are updated.

---

### 14. To delete specific rows from a table:
**A)** DELETE FROM table WHERE condition;  
**B)** TRUNCATE table WHERE condition;  
**C)** REMOVE table;  
**D)** DROP ROW;  
✅ **Answer:** A — DELETE allows conditions.

---

### 15. Which operator merges results from two queries, removing duplicates?
**A)** UNION  
**B)** UNION ALL  
**C)** INTERSECT  
**D)** EXCEPT  
✅ **Answer:** A — UNION removes duplicates.

---

### 16. UNION ALL differs from UNION in that it:
**A)** Removes duplicates  
**B)** Keeps duplicates  
**C)** Returns intersection  
**D)** Returns only null rows  
✅ **Answer:** B — UNION ALL keeps duplicates.

---

### 17. The INTERSECT operator returns:
**A)** Rows in both queries  
**B)** Rows in first only  
**C)** Rows in second only  
**D)** All unique rows  
✅ **Answer:** A — Returns common records.

---

### 18. EXCEPT in SQL returns:
**A)** Common rows  
**B)** Rows present in first query but not in second  
**C)** Rows from both  
**D)** None of these  
✅ **Answer:** B — EXCEPT removes second query matches.

---

### 19. Which of these is a valid aggregate function?
**A)** TOTAL()  
**B)** AVG()  
**C)** COUNTROWS()  
**D)** MINIMUM()  
✅ **Answer:** B — AVG() returns average value.

---

### 20. What is the output of `SELECT COUNT(DISTINCT dept_id)`?
**A)** Total number of rows  
**B)** Number of unique departments  
**C)** Total employees  
**D)** None  
✅ **Answer:** B — DISTINCT removes duplicates before counting.

---

### 21. Which clause filters records after aggregation?
**A)** WHERE  
**B)** HAVING  
**C)** GROUP BY  
**D)** ORDER BY  
✅ **Answer:** B — HAVING filters aggregated results.

---

### 22. What is the result of `SELECT dept, SUM(salary) FROM employees GROUP BY dept;`  
**A)** Total salary per department  
**B)** Highest salary overall  
**C)** Employee count  
**D)** Error  
✅ **Answer:** A — Aggregates salaries by department.

---

### 23. A nested query is:
**A)** Two queries in one file  
**B)** A query inside another query  
**C)** Recursive stored procedure  
**D)** None  
✅ **Answer:** B — Also called a subquery.

---

### 24. Which clause allows comparing a value with a list of values?
**A)** ANY  
**B)** ALL  
**C)** IN  
**D)** EXISTS  
✅ **Answer:** C — IN compares to a list.

---

### 25. The EXISTS operator checks:
**A)** If a subquery returns any rows  
**B)** If a column exists  
**C)** If a table exists  
**D)** If a user exists  
✅ **Answer:** A — TRUE if the subquery returns results.

---

### 26. The keyword ALL used with a subquery means:
**A)** Compare to all returned values  
**B)** Compare to one value  
**C)** Ignore duplicates  
**D)** None  
✅ **Answer:** A — Must satisfy comparison for all results.

---

### 27. Which of the following cannot be used in a subquery?
**A)** SELECT  
**B)** DELETE  
**C)** CREATE  
**D)** INSERT  
✅ **Answer:** C — DDL statements like CREATE are not allowed.

---

### 28. What happens if you omit WHERE in DELETE?
**A)** Deletes all rows  
**B)** Deletes none  
**C)** Error  
**D)** Deletes random rows  
✅ **Answer:** A — Deletes all records in the table.

---

### 29. To add a new column to an existing table:
✅ **Answer:** `ALTER TABLE table_name ADD COLUMN column_name datatype;`

---

### 30. To change datatype of a column:
✅ **Answer:** `ALTER TABLE table_name MODIFY COLUMN column_name new_datatype;`

---

### 31. The result of a CROSS JOIN is:
✅ **Answer:** Cartesian product of both tables.

---

### 32. Which join shows unmatched records from the right table?
✅ **Answer:** RIGHT OUTER JOIN.

---

### 33. To find common records using joins:
✅ **Answer:** INNER JOIN.

---

### 34. Which function ignores NULL values?
✅ **Answer:** SUM() — all aggregate functions ignore NULLs.

---

### 35. `SELECT salary FROM emp WHERE dept_id IN (10,20);` retrieves:
✅ **Answer:** Salaries in departments 10 and 20.

---

### 36. What will this return?  
`SELECT * FROM emp WHERE EXISTS (SELECT * FROM dept WHERE emp.dept_id=dept.id);`  
✅ **Answer:** Employees with valid departments.

---

### 37. Which set operator returns duplicates?
✅ **Answer:** UNION ALL.

---

### 38. The HAVING clause is used with:
✅ **Answer:** Aggregate functions.

---

### 39. A view does NOT store:
✅ **Answer:** Actual data — it stores only query definition.

---

### 40. A table alias is used for:
✅ **Answer:** Simplifying table reference names.

---

### 41. What is returned by `SELECT NULL=NULL;`  
✅ **Answer:** UNKNOWN — NULL comparison yields UNKNOWN.

---

### 42. Which keyword combines results including duplicates?
✅ **Answer:** UNION ALL.

---

### 43. Which command deletes table definition?
✅ **Answer:** DROP TABLE.

---

### 44. Which operator can test membership in a subquery list?
✅ **Answer:** IN.

---

### 45. What is `ALTER TABLE emp DROP COLUMN age;` used for?
✅ **Answer:** Remove a column from the table.

---

### 46. Which of these can be used to rename a table?
✅ **Answer:** RENAME TABLE old_name TO new_name;

---

### 47. To find employees not in department 20:
✅ **Answer:** `SELECT * FROM emp WHERE dept_id NOT IN (20);`

---

### 48. The EXISTS keyword in SQL returns TRUE when:
✅ **Answer:** A subquery returns at least one record.

---

### 49. The HAVING clause differs from WHERE because:
✅ **Answer:** HAVING filters after GROUP BY; WHERE filters before aggregation.

---

### 50. The DROP command in SQL:
✅ **Answer:** Permanently removes the table structure and data.

---

**© 2025 — SQL Study Notes by Pratik**
