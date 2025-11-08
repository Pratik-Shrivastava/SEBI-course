# SQL QUERIES (Expanded Conceptual Guide)

**IFSCA Phase-II IT: SQL Commands & Query Logic**

---

### 🧱 1️⃣ SELECT STATEMENT

**Concept:**  
SELECT retrieves data from one or more tables.

**Syntax:**
```sql
SELECT column1, column2
FROM table_name
WHERE condition
ORDER BY column;
```

**Mini Diagram:**  
Table → Filter (WHERE) → Sort (ORDER BY) → Result

**Example:**
```sql
SELECT Name, Dept
FROM Employee
WHERE Salary > 50000
ORDER BY Dept;
```
**Explanation:**  
Retrieves all employees with salary > 50k, sorted by department.

**MCQs:**  
1️⃣ Retrieve columns → ✅ SELECT  
2️⃣ Filter rows → ✅ WHERE  
3️⃣ Sort results → ✅ ORDER BY

---

### 🧩 2️⃣ VIEW

**Concept:**  
A View is a virtual table created from a query result.

**Syntax:**
```sql
CREATE VIEW view_name AS
SELECT columns FROM table WHERE condition;
```

**Example:**
```sql
CREATE VIEW HighSalary AS
SELECT Name, Salary FROM Employee WHERE Salary > 60000;
```

**Mini Diagram:**  
Base Table → Query → View (Virtual Table)

**Explanation:**  
A view simplifies complex queries and enhances security by exposing only selected columns.

**MCQs:**  
1️⃣ View stores data physically → ❌ False  
2️⃣ To create view → ✅ CREATE VIEW  
3️⃣ View is based on → ✅ Query result

---

### 🗑 3️⃣ TRUNCATE

**Concept:**  
Removes all rows from a table without logging individual deletions.

**Syntax:**
```sql
TRUNCATE TABLE table_name;
```

**Example:**
```sql
TRUNCATE TABLE Orders;
```

**Explanation:**  
Quickly empties a table but cannot be rolled back in many systems.

**Mini Diagram:**  
Table → Remove all data → Keep structure

**MCQs:**  
1️⃣ Deletes all rows → ✅ TRUNCATE  
2️⃣ Rollback possible → ❌ No  
3️⃣ Table structure remains → ✅ Yes

---

### ❌ 4️⃣ DELETE

**Concept:**  
Removes selected rows using a condition.

**Syntax:**
```sql
DELETE FROM table_name WHERE condition;
```

**Example:**
```sql
DELETE FROM Employee WHERE Dept='HR';
```

**Mini Diagram:**  
Table → Match condition → Remove only those rows

**MCQs:**  
1️⃣ Conditional deletion → ✅ DELETE  
2️⃣ Can rollback → ✅ Yes  
3️⃣ Without WHERE → ✅ Deletes all rows

---

### 🧰 5️⃣ UPDATE

**Concept:**  
Modifies existing records.

**Syntax:**
```sql
UPDATE table_name
SET column=value
WHERE condition;
```

**Example:**
```sql
UPDATE Employee
SET Salary=Salary*1.10
WHERE Dept='Finance';
```

**Explanation:**  
Increases Finance department salaries by 10%.

**MCQs:**  
1️⃣ Modify values → ✅ UPDATE  
2️⃣ Without WHERE → ✅ All rows affected  
3️⃣ Keyword to set new values → ✅ SET

---

### 🧱 6️⃣ ALTER

**Concept:**  
Changes table structure — add, modify, or drop columns.

**Syntax:**
```sql
ALTER TABLE table_name
ADD column_name datatype;

ALTER TABLE table_name
DROP COLUMN column_name;
```

**Example:**
```sql
ALTER TABLE Employee ADD Email VARCHAR(50);
```

**MCQs:**  
1️⃣ Add new column → ✅ ALTER + ADD  
2️⃣ Remove column → ✅ DROP COLUMN  
3️⃣ Used for structure change → ✅ Yes

---

### 🔗 7️⃣ INNER JOIN

**Concept:**  
Returns rows with matching values in both tables.

**Syntax:**
```sql
SELECT A.col, B.col
FROM A INNER JOIN B
ON A.id = B.id;
```

**Mini Diagram:**  
A(id) ⋈ B(id) → Only common ids

**Example:**
```sql
SELECT E.Name, D.DeptName
FROM Employee E INNER JOIN Department D
ON E.DeptID = D.DeptID;
```

**MCQs:**  
1️⃣ Returns → ✅ Matching rows only  
2️⃣ Join condition uses → ✅ ON  
3️⃣ Common in both → ✅ INNER JOIN

---

### 🔄 8️⃣ OUTER JOINS

**Concept:**  
Includes non-matching rows too (depends on join type).

🔹 **LEFT JOIN**
```sql
SELECT * FROM A LEFT JOIN B ON A.id = B.id;
```
🔹 **RIGHT JOIN**
```sql
SELECT * FROM A RIGHT JOIN B ON A.id = B.id;
```
🔹 **FULL OUTER JOIN**
```sql
SELECT * FROM A FULL OUTER JOIN B ON A.id = B.id;
```

**Mini Diagram:**  
Left Join  → All A + matches  
Right Join → All B + matches  
Full Join  → All A + All B

**MCQs:**  
1️⃣ Left join → ✅ All left, matched right  
2️⃣ Full join → ✅ All from both  
3️⃣ Missing data filled as → ✅ NULL

---

### ➕ 9️⃣ AGGREGATE FUNCTIONS

**Concept:**  
Perform calculations on data groups.

| Function | Purpose | Example |
|-----------|----------|----------|
| COUNT() | No. of rows | COUNT(*) |
| SUM() | Total | SUM(Salary) |
| AVG() | Average | AVG(Salary) |
| MIN()/MAX() | Lowest / Highest | MAX(Salary) |

**Example:**
```sql
SELECT Dept, AVG(Salary)
FROM Employee
GROUP BY Dept;
```

**Mini Diagram:**  
Dept groups → Avg salary → Result

**MCQs:**  
1️⃣ COUNT counts → ✅ Rows  
2️⃣ AVG gives → ✅ Mean  
3️⃣ Grouped aggregation → ✅ GROUP BY

---

### 🔣 🔟 UNION, INTERSECT, EXCEPT

**Concept:**  
Set operators combine results of multiple queries.

| Operator | Description | Example |
|-----------|--------------|----------|
| UNION | Combine all (remove duplicates) | SELECT City FROM C1 UNION SELECT City FROM C2; |
| INTERSECT | Common rows | SELECT City FROM C1 INTERSECT SELECT City FROM C2; |
| EXCEPT | Rows in first not in second | SELECT City FROM C1 EXCEPT SELECT City FROM C2; |

**Mini Diagram:**  
UNION → Merge  
INTERSECT → Overlap  
EXCEPT → Difference

**MCQs:**  
1️⃣ UNION removes duplicates → ✅ Yes  
2️⃣ INTERSECT returns → ✅ Common rows  
3️⃣ EXCEPT → ✅ Difference (A–B)

---

### 🧮 11️⃣ IN & EXISTS CLAUSES

**Concept:**  
Filter rows based on multiple values or subquery results.

| Clause | Description | Example |
|---------|--------------|----------|
| IN | Matches any value in list | WHERE Dept IN ('CS','IT') |
| EXISTS | True if subquery returns rows | WHERE EXISTS (SELECT * FROM Dept WHERE Manager='Aditi') |

**Mini Diagram:**  
IN → Matches fixed list  
EXISTS → Dependent subquery

**MCQs:**  
1️⃣ IN compares with → ✅ List of values  
2️⃣ EXISTS checks → ✅ Subquery existence  
3️⃣ IN('A','B') same as → ✅ OR conditions

---

### 🌀 12️⃣ NESTED QUERIES

**Concept:**  
A query inside another query, evaluated first (inner query result → outer query).

**Syntax:**
```sql
SELECT Name
FROM Employee
WHERE DeptID IN (
    SELECT DeptID FROM Department WHERE Location='Mumbai');
```

**Mini Diagram:**  
Inner: Dept by location  
→ Outer: Employees in those Depts

**Explanation:**  
Retrieves all employees working in Mumbai-based departments.

**MCQs:**  
1️⃣ Query inside query → ✅ Nested query  
2️⃣ Evaluated order → ✅ Inner first  
3️⃣ Used for → ✅ Conditional filtering

---

### ✅ FINAL REVISION TABLE

| Concept | Purpose | Example |
|----------|----------|----------|
| SELECT | Retrieve data | SELECT * FROM emp |
| VIEW | Virtual table | CREATE VIEW v AS ... |
| TRUNCATE | Remove all rows | TRUNCATE TABLE t |
| DELETE | Remove some rows | DELETE WHERE ... |
| UPDATE | Modify data | UPDATE SET ... |
| ALTER | Change structure | ALTER TABLE ADD ... |
| INNER JOIN | Common rows | A ⋈ B |
| OUTER JOIN | Include NULLs | LEFT/RIGHT/FULL |
| AGGREGATE | Summaries | SUM(), AVG() |
| UNION | Combine results | A ∪ B |
| INTERSECT | Common | A ∩ B |
| EXCEPT | Difference | A – B |
| IN | Match list | IN ('X','Y') |
| EXISTS | Subquery check | EXISTS(subquery) |
| NESTED | Query inside query | Subselects |

---

### 🧠 IFSCA EXAM TIPS

✅ SELECT is the most common SQL MCQ area.  
✅ INNER JOIN = intersection; LEFT JOIN = A + intersection.  
✅ **TRUNCATE vs DELETE**

| TRUNCATE | DELETE |
|-----------|---------|
| Removes all | Conditional |
| Faster | Slower |
| Cannot rollback | Can rollback |

✅ Aggregate + GROUP BY — always used together.  
✅ UNION removes duplicates; UNION ALL keeps them.  
✅ Nested Queries: “IN” is static; “EXISTS” is dynamic and checks presence.  
✅ Practice writing small outputs — e.g., “What will this query return?” type MCQs appear often.  
✅ Exam tip: 1 SQL output question + 2 command

# 🧾 SQL COMMAND QUICK REFERENCE CHART

### (IFSCA Phase-II IT: SQL Queries — One-Page Summary)

---

## 🗂 DATA RETRIEVAL
| Command | Syntax | Description / Notes |
|----------|---------|----------------------|
| **SELECT** | `SELECT col1, col2 FROM table WHERE cond;` | Fetch rows and columns. |
| **DISTINCT** | `SELECT DISTINCT col FROM table;` | Remove duplicates. |
| **ORDER BY** | `ORDER BY col [ASC/DESC];` | Sort results. |
| **LIMIT / TOP** | `LIMIT N` / `SELECT TOP N` | Restrict row count. |

---

## 🧱 DATA DEFINITION (DDL)
| Command | Syntax | Purpose |
|----------|---------|----------|
| **CREATE TABLE** | `CREATE TABLE t (col datatype);` | Make new table. |
| **ALTER TABLE** | `ALTER TABLE t ADD col datatype;` | Change structure. |
| **DROP TABLE** | `DROP TABLE t;` | Remove table permanently. |
| **TRUNCATE** | `TRUNCATE TABLE t;` | Delete all rows, keep structure. |

---

## 🧰 DATA MANIPULATION (DML)
| Command | Syntax | Function |
|----------|---------|-----------|
| **INSERT** | `INSERT INTO t VALUES (...);` | Add record. |
| **UPDATE** | `UPDATE t SET col=val WHERE cond;` | Modify data. |
| **DELETE** | `DELETE FROM t WHERE cond;` | Remove data conditionally. |

---

## 🔗 JOINS
| Type | Example | Result |
|------|----------|---------|
| **INNER** | `A INNER JOIN B ON A.id=B.id` | Only matching rows. |
| **LEFT** | `A LEFT JOIN B ON A.id=B.id` | All A + matches. |
| **RIGHT** | `A RIGHT JOIN B ON A.id=B.id` | All B + matches. |
| **FULL** | `A FULL JOIN B ON A.id=B.id` | All A + all B (NULLs). |

---

## 🧮 AGGREGATE FUNCTIONS
| Function | Use | Example |
|-----------|-----|----------|
| **COUNT()** | Row count | `COUNT(*)` |
| **SUM()** | Total | `SUM(Salary)` |
| **AVG()** | Mean | `AVG(Salary)` |
| **MIN()/MAX()** | Extremes | `MAX(Salary)` |
| **GROUP BY** | Aggregation grouping | `GROUP BY Dept` |
| **HAVING** | Filter after grouping | `HAVING AVG(Salary) > 60000` |

---

## 🧾 SET OPERATIONS
| Operator | Meaning | Example |
|-----------|----------|----------|
| **UNION** | Combine, remove duplicates | `A UNION B` |
| **UNION ALL** | Combine, keep duplicates | `A UNION ALL B` |
| **INTERSECT** | Common rows | `A INTERSECT B` |
| **EXCEPT / MINUS** | Rows in A not in B | `A EXCEPT B` |

---

## 🧩 SUBQUERIES & CLAUSES
| Clause | Syntax | Purpose |
|---------|---------|----------|
| **IN** | `WHERE Dept IN ('CS','IT')` | Match list. |
| **EXISTS** | `WHERE EXISTS (subquery)` | True if subquery returns row(s). |
| **ANY / ALL** | `> ANY(subq)` / `< ALL(subq)` | Compare with subquery results. |
| **NESTED QUERY** | Inner inside outer | Used for dependent filtering. |

---

## 🧱 VIEWS
| Command | Syntax | Note |
|----------|---------|-------|
| **CREATE VIEW** | `CREATE VIEW v AS SELECT ...;` | Virtual table. |
| **DROP VIEW** | `DROP VIEW v;` | Remove view. |

---

## ⚙️ TRANSACTION CONTROL
| Command | Function |
|----------|-----------|
| **COMMIT** | Save changes. |
| **ROLLBACK** | Undo since last commit. |
| **SAVEPOINT** | Partial rollback marker. |

---

## 💡 COMMON SYMBOLS
| Symbol | Meaning |
|---------|----------|
| **σ** | Selection (rows) |
| **π** | Projection (columns) |
| **⋈** | Join |
| **∪** | Union |
| **−** | Difference |
| **∩** | Intersection |

---

## 🧠 IFSCA QUICK FACTS
- **DELETE vs TRUNCATE:** DELETE logs each row and allows rollback; TRUNCATE is faster and cannot be rolled back.
- **INNER JOIN = INTERSECT**, **UNION = set merge**, **EXCEPT = A − B.**
- **HAVING** filters *after* aggregation; **WHERE** filters *before* aggregation.
- **IN** is for static lists; **EXISTS** for correlated subqueries.
- **GROUP BY** + aggregate queries are *frequent exam topics.*

