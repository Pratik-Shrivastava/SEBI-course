# Data Warehousing Concepts (Expanded Conceptual Guide)

## 🧩 1️⃣ DATA EXTRACTION

**Concept:** Retrieve data from multiple heterogeneous sources as the first step of ETL.

**Flow:**
```
Source DB / APIs → Extraction Tool → Staging Area
```

**Extraction Types:** Full • Incremental • Real-time  
**Example (SQL):**
```sql
SELECT * FROM sales WHERE updated_at > '2025-11-01';
```

**MCQs:**
- First ETL step → ✅ Extraction
- Incremental fetch → ✅ Only changes
- Sources → ✅ Multiple systems

---

## 🧹 2️⃣ DATA CLEANING

**Concept:** Detect & correct errors, fill gaps, remove duplicates.

**Flow:**
```
Raw Data → Error Check → Clean Data
```

**Main Tasks:** Handle missing → imputation • remove duplicates • detect outliers • standardize units  
**Example (Python):**
```python
df.drop_duplicates()
df['Salary'].fillna(df['Salary'].mean())
```

**MCQs:**
- Remove duplicates → ✅ Cleaning
- Handle missing → ✅ Imputation
- Outlier check → ✅ Stats test

---

## 🔄 3️⃣ DATA TRANSFORMATION

**Concept:** Convert data into uniform format before loading.

**Flow:**
```
Raw → Transform (Rules) → Target Schema
```

**Operations:** Aggregation • Normalization • Encoding • Join • Split  
**Example (SQL):**
```sql
SELECT region, SUM(sales) FROM trans GROUP BY region;
```

**MCQs:**
- Occurs → ✅ Before Loading
- Normalization → ✅ Scaling
- Aggregation → ✅ Summarization

---

## 📤 4️⃣ DATA LOADING

**Concept:** Move transformed data into the warehouse.

**Flow:**
```
Staging → DW (batch / real-time)
```

**Load Types:** Initial • Incremental • Full Refresh  
**Example:**
```sql
INSERT INTO dw.sales SELECT * FROM staging.sales_clean;
```

**MCQs:**
- Last ETL step → ✅ Loading
- Incremental load → ✅ New data only
- Full refresh → ✅ Overwrite

---

## 🧠 5️⃣ METADATA

**Concept:** Data about data — describes structure & origin.

**Example Table:**
| Table | Columns | Type | Source | Updated |
|--------|----------|------|---------|----------|
| Customer | Customer_ID | INT | CRM_DB | 22:00 |

**Types:** Technical • Business • Operational  
**Example:** “Customer_ID from CRM_DB updated at 22:00.”

**MCQs:**
- Meaning → ✅ Data about data
- ETL logs → ✅ Operational metadata
- Column details → ✅ Technical metadata

---

## 🧮 6️⃣ DATA CUBE

**Concept:** Multidimensional view for OLAP analysis.

**Structure:**
```
Dimensions → Product × Region × Time
```

**OLAP Ops:** Roll-up (aggregate) • Drill-down (detail) • Slice • Dice  
**Example:** Sales by Product and Region over Time.

**MCQs:**
- Used in → ✅ OLAP
- Roll-up → ✅ Aggregate
- Drill-down → ✅ Detail

---

## 🗂 7️⃣ DATA MART

**Concept:** Subset of data warehouse for department analysis.

```
DW
 ├ Sales Mart
 ├ HR Mart
 └ Finance Mart
```

**Types:** Dependent (from DW) • Independent (from sources)

**MCQs:**
- Subset of → ✅ Warehouse
- HR mart = ✅ Departmental
- Dependent mart → ✅ From DW

---

## 🧱 8️⃣ DATA MODELS

**Concept:** Logical structure of warehouse data.

```
       +--Fact(Sales)--+
      /      |      \
 Product   Time   Region (Dimensions)
```

**Schemas:** Star (simple) • Snowflake (normalized) • Galaxy (multi-fact)

**MCQs:**
- Center table → ✅ Fact
- Normalized form → ✅ Snowflake
- Model defines → ✅ Relationships

---

## 📘 FINAL REVISION TABLE

| Concept | Core Idea | Example / Tool |
|----------|------------|----------------|
| Extraction | Collect source data | SQL, APIs |
| Cleaning | Correct errors | Pandas |
| Transformation | Format & aggregate | SQL GROUP BY |
| Loading | Move to DW | ETL, Airflow |
| Metadata | Describe data | Schema info |
| Data Cube | Multi-dimensional OLAP | Slice / Dice |
| Data Mart | Dept subset of DW | HR Mart |
| Data Models | Logical schema | Star, Snowflake |

---

## 🧾 SUMMARY SHEET (Quick Reference)

**ETL Flow:**
```
Extract → Clean → Transform → Load → Analyze
```

**One-line Definitions:**
1️⃣ Extraction – Gather data from sources  
2️⃣ Cleaning – Fix errors & duplicates  
3️⃣ Transformation – Re-format for warehouse  
4️⃣ Loading – Store in DW or Mart  
5️⃣ Metadata – Data about data  
6️⃣ Data Cube – OLAP multi-dimension  
7️⃣ Data Mart – Subset for business unit  
8️⃣ Data Model – Logical design schema

**Comparison Table:**

| Feature | Data Warehouse | Data Mart | Data Cube |
|----------|----------------|------------|------------|
| Scope | Enterprise | Department | Analytical view |
| Size | TB–PB | GB–TB | In-memory array |
| Use | Historical storage | Quick reports | OLAP analysis |

---

## 🧠 IFSCA EXAM TIPS

✅ ETL order = Extract → Transform → Load.  
✅ Metadata = “data about data.”  
✅ Data Mart = Subset of DW; Data Cube = OLAP representation.  
✅ Star Schema = Simple and fast; Snowflake = Normalized.  
✅ Cleaning = remove duplicates, fix missing values.  
✅ Transformation = join & aggregate.  
✅ Common MCQ keywords: ETL, Metadata types, OLAP ops, Star vs Snowflake.

