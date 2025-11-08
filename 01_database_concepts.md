DATABASE CONCEPTS (Expanded Conceptual Guide)

# IFSCA Phase-II IT: Database Concepts

## 🧩 1️⃣ ENTITY–RELATIONSHIP (ER) MODEL

**Concept:**  
ER Model represents real-world entities and relationships — foundation for logical database design.

**Diagram (Textual):**
```
[Customer]──(places)──[Order]
   |                      |
 [CustID]               [OrderID]
```

| Element | Description | Example |
|----------|--------------|----------|
| Entity | Object or concept | Student, Course |
| Attribute | Property of entity | Name, RollNo |
| Relationship | Association between entities | Enrolls |
| Primary Key | Uniquely identifies record | RollNo |
| Cardinality | Number of links | 1:1, 1:N, M:N |

**Example:**  
One Customer places many Orders (1:N relationship).

**MCQs:**  
1️⃣ ER model used for → ✅ Conceptual design  
2️⃣ Attribute means → ✅ Property of entity  
3️⃣ 1:N example → ✅ Customer–Order  

---

## 🧠 2️⃣ RELATIONAL MODEL

**Concept:**  
Data stored in tables (relations) with rows (tuples) and columns (attributes).

**Diagram:**
```
STUDENT (RollNo, Name, Dept)
COURSE  (CourseID, Title)
```

| Term | Meaning |
|------|----------|
| Relation | Table |
| Tuple | Row |
| Attribute | Column |
| Domain | Allowed values |
| Schema | Table structure |

**Example Table:**
```
STUDENT
+--------+--------+---------+
| RollNo | Name   | Dept    |
+--------+--------+---------+
| 101    | Aditi  | CS      |
| 102    | Ravi   | IT      |
+--------+--------+---------+
```

**MCQs:**  
1️⃣ Relation in DB → ✅ Table  
2️⃣ Tuple → ✅ Row  
3️⃣ Schema defines → ✅ Structure  

---

## 🔣 3️⃣ RELATIONAL ALGEBRA

**Concept:**  
Procedural query language to retrieve data from relations.

| Operator | Symbol | Description | Example |
|-----------|---------|-------------|----------|
| Select | σ | Filter rows | σDept='CS'(STUDENT) |
| Project | π | Choose columns | πName,Dept(STUDENT) |
| Union | ∪ | Combine two relations | A ∪ B |
| Difference | − | Subtract sets | A − B |
| Join | ⋈ | Combine related tuples | STUDENT ⋈ COURSE |

**Mini Diagram:**
```
STUDENT ⋈ COURSE → Combined dataset
```

**MCQs:**  
1️⃣ σ operator → ✅ Selection  
2️⃣ π operator → ✅ Projection  
3️⃣ ⋈ operator → ✅ Join  

---

## 🔢 4️⃣ TUPLE RELATIONAL CALCULUS (TRC)

**Concept:**  
Non-procedural — defines what to retrieve, not how.

**Syntax:**
```
{ t | P(t) }
```
**Example:**
```
{ t | t ∈ Student ∧ t.Dept = 'CS' }
```
→ All CS students.

**MCQs:**  
1️⃣ TRC type → ✅ Non-procedural  
2️⃣ Expression format → ✅ {t | P(t)}  
3️⃣ Based on → ✅ Predicate logic  

---

## 🧭 5️⃣ INTEGRITY CONSTRAINTS

**Concept:**  
Ensure accuracy and consistency of data.

| Type | Description | Example |
|------|--------------|----------|
| Domain | Valid data range | Age > 0 |
| Entity Integrity | PK not NULL | RollNo NOT NULL |
| Referential | FK matches PK | Dept in DEPT table |
| Key Constraint | Unique keys | RollNo unique |

**SQL Example:**
```sql
CREATE TABLE STUDENT (
  RollNo INT PRIMARY KEY,
  Dept VARCHAR(20) REFERENCES DEPARTMENT(DeptName)
);
```

**MCQs:**  
1️⃣ PK cannot → ✅ Be NULL  
2️⃣ FK ensures → ✅ Referential integrity  
3️⃣ Entity integrity → ✅ Uniqueness of tuples  

---

## 🧱 6️⃣ NORMAL FORMS (Normalization)

**Concept:**  
Reorganize data to remove redundancy & anomalies.

**Progression:**  
Unnormalized → 1NF → 2NF → 3NF → BCNF → 4NF → 5NF

| Normal Form | Condition | Fixes |
|--------------|------------|--------|
| 1NF | Atomic values | Split repeating groups |
| 2NF | 1NF + no partial dependency | Remove subset dependency |
| 3NF | 2NF + no transitive dep. | Remove indirect dependency |
| BCNF | Every determinant is key | Strong 3NF |
| 4NF | No multi-valued dependencies | Separate into distinct relations |
| 5NF | No join dependencies | Simplify complex relationships |

**Example:**  
Separate Course and Instructor tables from STUDENT.

**MCQs:**  
1️⃣ 1NF removes → ✅ Repeating groups  
2️⃣ 3NF removes → ✅ Transitive dependency  
3️⃣ BCNF → ✅ Stronger 3NF  
4️⃣ 4NF → ✅ Removes multi-valued dependencies  
5️⃣ 5NF → ✅ Removes join dependencies  

---

## 📂 7️⃣ FILE ORGANIZATION

**Concept:**  
Determines how records are physically arranged on storage.

| Type | Description | Example |
|------|--------------|----------|
| Sequential | Sorted by key | Payroll file |
| Indexed | Index pointer to record | Index on EmpID |
| Hashed | Hash function for location | Hash(EmpID) |

**Diagram:**
```
Index File → Pointer → Data Block
```

**MCQs:**  
1️⃣ Sequential file sorted by → ✅ Key field  
2️⃣ Indexed access → ✅ Faster  
3️⃣ Hash uses → ✅ Hash function  

---

## 🌳 8️⃣ INDEXING (B & B+ TREES)

**Concept:**  
Improves retrieval speed by using a hierarchical index structure.

**Diagram (B+ Tree):**
```
       [40]
      /    \
 [10,20]  [50,60]
Leaf nodes linked sequentially
```

| Feature | B-Tree | B+ Tree |
|----------|---------|----------|
| Data in | All nodes | Leaf only |
| Traversal | Key-by-key | Sequential |
| Best for | Searches | Range queries |

**MCQs:**  
1️⃣ B+ Tree stores data in → ✅ Leaf nodes  
2️⃣ Used for → ✅ Range queries  
3️⃣ Improves → ✅ Retrieval speed  

---

## 💳 9️⃣ TRANSACTIONS

**Concept:**  
Sequence of DB operations forming one logical unit of work.

**ACID Properties:**

| Property | Description |
|-----------|-------------|
| Atomicity | All or none |
| Consistency | Preserves rules |
| Isolation | No interference |
| Durability | Permanent results |

**Example:**
```sql
BEGIN TRANSACTION;
UPDATE ACCOUNTS SET BAL=BAL-500 WHERE ID=1;
UPDATE ACCOUNTS SET BAL=BAL+500 WHERE ID=2;
COMMIT;
```

**MCQs:**  
1️⃣ Atomicity → ✅ All or none  
2️⃣ Durability → ✅ Results persist  
3️⃣ Isolation → ✅ No interference  

---

## 🔄 🔟 CONCURRENCY CONTROL

**Concept:**  
Ensures correct results when multiple transactions execute simultaneously.

**Problems prevented:**
- Lost update  
- Dirty read  
- Uncommitted dependency  

**Techniques:**
| Method | Description |
|---------|--------------|
| Locking | Controls access to data |
| Two-Phase Locking (2PL) | Growing + shrinking phase |
| Timestamp ordering | Based on transaction timestamps |
| Deadlock prevention | Avoid circular waits |

**Diagram (2PL):**
```
T1: Lock → Write → Unlock
T2: Wait → Lock → Write → Unlock
```

**MCQs:**  
1️⃣ Goal → ✅ Consistency in concurrency  
2️⃣ 2PL phases → ✅ Growing & Shrinking  
3️⃣ Avoid lost updates → ✅ Locking  

---

## 🧮 QUICK SQL & SYMBOL SHEET

| Symbol / Keyword | Meaning / Command |
|------------------|--------------------|
| σ | Selection (rows) |
| π | Projection (columns) |
| ⋈ | Join |
| ∪ | Union |
| − | Set Difference |
| PK | Primary Key |
| FK | Foreign Key |
| COMMIT | Save transaction |
| ROLLBACK | Undo transaction |
| 2PL | Two-Phase Locking |
| BCNF | Boyce–Codd Normal Form |

---

## 🧾 ER → RELATIONAL → NORMALIZATION FLOW
```
ER Diagram
  ↓
Convert entities → Tables
  ↓
Define PK/FK relationships
  ↓
Apply Normalization (1NF–5NF)
  ↓
Implement in RDBMS
```

---

## ✅ FINAL REVISION TABLE

| Concept | Key Idea | Example |
|----------|-----------|----------|
| ER Model | Entity–Relation diagram | Customer–Order |
| Relational Model | Tables structure | STUDENT table |
| Algebra | Procedural ops | σ, π, ⋈ |
| Calculus | Non-procedural | {t | P(t)} |
| Constraints | Data validity | PK, FK |
| Normal Forms | Remove redundancy | 1NF–5NF |
| File Org. | Storage pattern | Sequential, Hashed |
| Indexing | Speeds up retrieval | B+ Tree |
| Transactions | ACID properties | COMMIT |
| Concurrency | Safe multi-access | Locking, 2PL |

---

## 🧠 IFSCA EXAM TIPS

✅ **ER Model:** Know symbols & 1:N vs M:N.  
✅ **Relational Algebra:** σ = selection, π = projection, ⋈ = join.  
✅ **Constraints:**  
  - PK → Unique, non-null  
  - FK → References PK  
✅ **Normalization:**  
  - 1NF – atomic  
  - 2NF – no partial dependency  
  - 3NF – no transitive dependency  
  - 4NF – remove multi-valued dep.  
  - 5NF – remove join dep.  
✅ **Indexing:** B+ Tree stores data in leaf nodes → faster range queries.  
✅ **Transactions:** Memorize ACID.  
✅ **Concurrency:** 2PL ensures serializability; timestamp ordering avoids conflicts.  
✅ **SQL:** COMMIT, ROLLBACK, SAVEPOINT, PRIMARY KEY, FOREIGN KEY.  
✅ **Practice:** 2-mark ER diagram → relational schema conversion and normalization.

