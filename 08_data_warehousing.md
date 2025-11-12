# 🧠 Data Extraction, Cleaning, Transformation & Loading (ETL) — Complete Notes

## 📘 Overview

The **ETL (Extract, Transform, Load)** process forms the **backbone of Data Warehousing and Analytics systems**.  
It ensures that **raw data from multiple sources** is collected, processed, cleaned, and loaded into a **central repository (like a Data Warehouse or Data Mart)** for analysis and decision-making.

---

## 🤩 1. Data Extraction

### 🔹 Concept
Data Extraction is the **process of retrieving data** from various sources — such as databases, APIs, flat files, web pages, IoT devices, or cloud platforms.

### 🔹 Objective
To **collect raw data** in a usable form for analysis and transformation.

### 🔹 Types of Data Extraction
1. **Full Extraction** – Extracts the entire dataset each time.  
2. **Incremental Extraction** – Extracts only new or modified data since the last extraction.  
3. **Real-time Extraction** – Continuously extracts data as it changes (used in streaming pipelines).

### 🔹 Common Data Sources
- Relational databases (MySQL, PostgreSQL, Oracle)
- APIs (REST, SOAP)
- Web scraping (HTML, JSON)
- Cloud storage (AWS S3, Google Cloud Storage)
- Flat files (CSV, Excel, XML, JSON)

### 🔹 Tools for Data Extraction
| Tool | Description |
|------|--------------|
| **Apache Nifi** | Automates data flow between systems |
| **Talend** | Open-source ETL tool |
| **Informatica PowerCenter** | Enterprise-grade data integration |
| **Microsoft SSIS** | SQL Server Integration Services |
| **Python (Pandas, BeautifulSoup, requests)** | For scripting data extraction |

---

## 🧼 2. Data Cleaning

### 🔹 Concept
Data Cleaning (Data Scrubbing) refers to the **process of detecting and correcting inaccurate, incomplete, or inconsistent data** to improve quality.

### 🔹 Objectives
- Ensure **accuracy, completeness, consistency, and validity**.
- Remove **duplicates, errors, and irrelevant information**.

### 🔹 Common Data Cleaning Tasks
| Task | Description |
|------|--------------|
| **Handling Missing Values** | Replace, remove, or impute missing data |
| **Removing Duplicates** | Identify and remove repeated rows |
| **Standardizing Formats** | Uniform date/time, currency, units |
| **Correcting Inconsistencies** | Resolve mismatched values |
| **Outlier Detection** | Identify and manage extreme values |

### 🔹 Techniques
- **Imputation** (mean/median/mode)
- **Normalization and standardization**
- **Regex-based cleaning**
- **Data validation rules**

### 🔹 Tools for Data Cleaning
| Tool | Functionality |
|------|----------------|
| **OpenRefine** | Cleans and transforms messy data |
| **Trifacta Wrangler** | Interactive data wrangling |
| **Pandas (Python)** | Cleaning with code |
| **Excel/Google Sheets** | Manual small-scale cleaning |
| **Dataprep.ai / Talend Data Quality** | Enterprise-grade data quality tools |

---

## 🔁 3. Data Transformation

### 🔹 Concept
Data Transformation is the **process of converting extracted data into a format suitable for analysis or storage**.

### 🔹 Common Transformations
| Transformation | Description |
|----------------|-------------|
| **Filtering** | Removing irrelevant data |
| **Aggregation** | Summarizing data (sum, avg, count) |
| **Joining/Merging** | Combining multiple datasets |
| **Normalization** | Scaling data to standard range |
| **Encoding** | Converting categorical to numerical data |
| **Pivoting/Unpivoting** | Changing data structure (rows ⇌ columns) |
| **Deriving new features** | Creating computed columns |

### 🔹 Tools for Data Transformation
| Tool | Description |
|------|-------------|
| **Apache Spark** | Distributed large-scale data processing |
| **AWS Glue** | Managed ETL and transformation |
| **dbt (Data Build Tool)** | SQL-based transformation within warehouse |
| **Talend** | GUI-based transformation tool |
| **Python (Pandas, NumPy)** | Custom data transformation scripting |

---

## 💿 4. Data Loading

### 🔹 Concept
Data Loading is the **final phase of ETL**, where transformed data is **loaded into a target system**, such as a **data warehouse**, **data mart**, or **database**.

### 🔹 Loading Types
1. **Full Load** – Load all data from scratch each time.  
2. **Incremental Load** – Load only new/updated data.  
3. **Batch Load** – Load in periodic intervals.  
4. **Real-time Load** – Continuous data streaming.

### 🔹 Tools for Data Loading
| Tool | Description |
|------|--------------|
| **Apache Kafka** | Real-time streaming |
| **Snowflake** | Cloud data warehouse |
| **Amazon Redshift** | Scalable data warehouse |
| **Google BigQuery** | Serverless data warehouse |
| **Airbyte / Fivetran** | Automated data ingestion pipelines |

---

## 🧱 5. Metadata

### 🔹 Concept
Metadata means **“data about data.”**  
It provides **context, meaning, and structure** to data stored in systems.

### 🔹 Types of Metadata
| Type | Description |
|------|--------------|
| **Technical Metadata** | Schema, data types, size, source, lineage |
| **Business Metadata** | Business definitions and ownership |
| **Operational Metadata** | ETL logs, timestamps, execution details |

### 🔹 Applications
- Improves **data discoverability**  
- Aids in **data governance and lineage tracking**  
- Enhances **data quality management**

### 🔹 Tools for Metadata Management
| Tool | Description |
|------|--------------|
| **Apache Atlas** | Open-source metadata management |
| **Alation** | Data catalog and governance |
| **Collibra** | Enterprise metadata governance |
| **Google Data Catalog** | Cloud-based metadata service |

---

## 🦊 6. Data Cube

### 🔹 Concept
A **Data Cube** is a **multidimensional array of data**, used in **OLAP (Online Analytical Processing)** for fast analysis and querying.

### 🔹 Components
- **Dimensions**: Perspectives (e.g., Time, Region, Product)
- **Facts**: Quantitative data (e.g., Sales, Revenue)
- **Measures**: Aggregated values (e.g., SUM, AVG)

### 🔹 Operations on Data Cubes
| Operation | Description |
|------------|-------------|
| **Roll-up** | Aggregating data along a dimension |
| **Drill-down** | Breaking down data into finer granularity |
| **Slice** | Selecting one dimension subset |
| **Dice** | Selecting sub-cube with multiple dimensions |
| **Pivot** | Rotating the cube for different views |

### 🔹 Tools
| Tool | Description |
|------|--------------|
| **Microsoft SSAS (SQL Server Analysis Services)** | OLAP and data cube creation |
| **Pentaho Mondrian** | Open-source OLAP engine |
| **SAP BW** | Business warehouse for multidimensional analysis |

---

## 🏬 7. Data Mart

### 🔹 Concept
A **Data Mart** is a **subset of a Data Warehouse**, focused on a **specific business area** (e.g., Sales, Finance, Marketing).

### 🔹 Types of Data Marts
| Type | Description |
|------|--------------|
| **Dependent** | Derived from central Data Warehouse |
| **Independent** | Directly collected from operational sources |
| **Hybrid** | Combination of both |

### 🔹 Advantages
- Faster access to relevant data  
- Improved departmental decision-making  
- Reduced data complexity  

### 🔹 Tools for Data Mart Implementation
| Tool | Description |
|------|--------------|
| **Oracle Data Mart** | Enterprise-level data mart |
| **Amazon Redshift** | Cloud-based data mart |
| **Snowflake** | Scalable analytical store |
| **Informatica** | ETL + data mart integration |

---

## 🧮 8. Data Models

### 🔹 Concept
A **Data Model** defines **how data is structured, stored, and related** within a system.

### 🔹 Types of Data Models
| Model | Description | Example |
|--------|--------------|---------|
| **Conceptual Model** | High-level view; defines entities and relationships | ER Diagram |
| **Logical Model** | Specifies attributes, keys, and relationships | Relational schema |
| **Physical Model** | Implementation in database | Tables, columns, indexes |

### 🔹 Data Modeling Techniques
- **Entity-Relationship (ER) Modeling**
- **Dimensional Modeling** (Star and Snowflake schemas)
- **Hierarchical and Network Models**

### 🔹 Tools for Data Modeling
| Tool | Description |
|------|--------------|
| **ER/Studio** | Conceptual and logical modeling |
| **Lucidchart / Draw.io** | Visual diagramming |
| **MySQL Workbench** | Database-specific modeling |
| **PowerDesigner** | Enterprise data architecture tool |

---

## ⚙️ Summary — ETL Workflow Steps

| Step | Description |
|------|--------------|
| **1. Extraction** | Collect data from multiple sources |
| **2. Cleaning** | Fix inconsistencies and errors |
| **3. Transformation** | Convert to analysis-ready format |
| **4. Loading** | Store in warehouse/data mart |
| **5. Metadata Management** | Track data origin and structure |
| **6. Cube Creation** | Enable multidimensional analysis |
| **7. Modeling** | Structure for optimal querying |

---

## 💡 Applications

- **Business Intelligence Dashboards (Power BI, Tableau)**
- **Predictive Analytics and Machine Learning**
- **Customer Segmentation**
- **Sales Forecasting**
- **Fraud Detection**
- **Data Warehousing and Reporting**

---

## 📚 Key Terminologies

| Term | Meaning |
|------|----------|
| **ETL** | Extract, Transform, Load |
| **ELT** | Extract, Load, Transform (modern cloud approach) |
| **Data Pipeline** | Automated flow of data from source to target |
| **Data Lake** | Raw data repository for unstructured data |
| **Data Warehouse** | Central repository for structured, processed data |
| **Schema** | Logical structure defining data organization |
| **OLAP** | Online Analytical Processing for multidimensional analysis |
| **Data Governance** | Managing availability, usability, and integrity of data |

