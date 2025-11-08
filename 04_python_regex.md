# 🐍 DATA ANALYTICS WITH PYTHON

### 📘 Detailed & Conceptual Notes

---

## 1. **REGEX (Regular Expressions)**

**Definition:**  
Regular Expressions are powerful text patterns used to find, extract, or replace specific strings using the `re` module in Python.

**Concept:**  
Think of regex as “smart search”. Instead of manually checking text, you describe what you want using symbols (like wildcards, digits, words).

**Key Methods:**

| Function | Description |
|-----------|-------------|
| `re.search(pattern, string)` | Finds the first match anywhere in the string |
| `re.findall(pattern, string)` | Returns all matches as a list |
| `re.match(pattern, string)` | Matches pattern only at the start of the string |
| `re.sub(pattern, repl, string)` | Replaces occurrences of a pattern |
| `re.split(pattern, string)` | Splits string wherever pattern occurs |
| `re.compile(pattern)` | Compiles a regex for repeated use |

**Example:**
```python
import re
text = "Emails: test@mail.com, info@abc.org"
emails = re.findall(r'\b[\w\.-]+@[\w\.-]+\.\w{2,4}\b', text)
print(emails)  # ['test@mail.com', 'info@abc.org']
```
👉 `re.findall()` scans the string for all substrings that look like an email.

---

## 2. **SLICING**

**Definition:**  
Slicing extracts parts of a sequence (like a list, string, or tuple) using index ranges.

**Concept:**  
Think of slicing like taking “subsets” — e.g., a segment of a list, a substring of text, etc.  
In Python, indices start from `0`.

**Syntax:**  
`seq[start:end:step]` → extracts from `start` to `end-1`, moving by `step`.

**Example:**
```python
nums = [10, 20, 30, 40, 50]
nums[1:4]   # [20, 30, 40]
nums[::-1]  # [50, 40, 30, 20, 10]
```
👉 Negative step (`-1`) reverses the sequence.

---

## 3. **DATA RESHAPING**

**Definition:**  
Reshaping means changing the layout of a dataset — converting rows to columns or columns to rows — to make it easier to analyze.

**Concept:**  
When you load data into Python using **pandas**, it becomes a **DataFrame (df)** — a 2D table like Excel.

- **Wide → Long:** combining multiple column values into a single column (tidy format).  
- **Long → Wide:** spreading rows into separate columns.

**Key Methods:**

| Function | Description |
|-----------|-------------|
| `pd.melt(df, id_vars=['id'])` | Converts columns into rows — gathers many columns into two: variable & value |
| `df.pivot(index, columns, values)` | Opposite of melt — spreads rows into multiple columns |
| `df.stack()` / `df.unstack()` | Stack/unstack hierarchical columns or indexes |
| `df.transpose()` | Flip rows ↔ columns (like Excel transpose) |

**Example:**
```python
import pandas as pd
df = pd.DataFrame({'Year':[2023,2024],'Sales_A':[100,120],'Sales_B':[90,110]})
print(df)

# Convert from wide to long
df_long = pd.melt(df, id_vars='Year', var_name='Product', value_name='Sales')
```
👉 `pd.melt()` helps when you have repeated columns (Sales_A, Sales_B) and want them in one “Product” column.

---

## 4. **DATAFRAMES**

**Definition:**  
A **DataFrame** is a tabular data structure with labeled rows and columns, provided by the **pandas** library.

**Concept:**  
It’s like an Excel sheet or SQL table inside Python — you can filter, sort, and analyze data easily.

**Common Functions:**

| Method | Usage |
|---------|-------|
| `pd.DataFrame()` | Create a DataFrame |
| `df.head()` / `df.tail()` | View top/bottom rows |
| `df.info()` / `df.describe()` | Get structure & stats |
| `df.loc[]` / `df.iloc[]` | Access rows/cols by label or index |
| `df.sort_values()` | Sort rows |
| `df.drop()` / `df.rename()` | Modify structure |
| `df.merge()` / `pd.concat()` | Combine multiple DataFrames |

**Example:**
```python
import pandas as pd
df = pd.DataFrame({'Name':['A','B'], 'Age':[23,24]})
print(df.head())
df[df.Age > 23]  # Filter rows
```
👉 `df` is just a variable name; it stores your dataset in memory.

---

## 5. **DICTIONARIES & SETS**

**Definition:**  
- **Dictionary (dict):** stores key–value pairs.  
- **Set:** stores unique unordered elements.

**Concept:**  
Think of a dictionary as a “mini database” (key = field name, value = data).  
A set is like a “bag of unique items”.

**Useful Methods:**

| Dictionary | Description |
|-------------|-------------|
| `get(key, default)` | Fetch value safely |
| `keys()`, `values()`, `items()` | View keys/values |
| `update()`, `pop()`, `clear()` | Modify |
| `fromkeys()` | Create dict with given keys |

| Set | Description |
|-----|-------------|
| `add()`, `remove()`, `discard()` | Add/remove elements |
| `union()`, `intersection()` | Combine |
| `difference()`, `symmetric_difference()` | Compare sets |

**Example:**
```python
d = {'a':1, 'b':2}
s = {1,2,3}
print(d.get('a'))        # 1
print(s.union({3,4}))    # {1,2,3,4}
```

---

## 6. **FILE MANAGEMENT**

**Definition:**  
Reading, writing, or updating files for data storage.

**Concept:**  
Python uses `open()` to handle files. You can read or write plain text, CSV, or even binary files.

**Common Modes:**
- `'r'` = read  
- `'w'` = write (overwrite)  
- `'a'` = append  
- `'rb'` / `'wb'` = binary mode

**Example:**
```python
with open('test.txt','w') as f:
    f.write("Hello IFSCA")
```
👉 `with open()` auto-closes the file safely.

**pandas File Ops:**
```python
pd.read_csv("file.csv")   # Read CSV file
df.to_csv("out.csv")       # Save data
```

---

## 7. **CLASSES & FUNCTIONS**

**Definition:**  
Functions organize code; classes define reusable blueprints for objects.

**Concept:**  
A function performs a single job.  
A class can bundle multiple functions (methods) and variables (attributes) together.

**Example:**
```python
class Car:
    def __init__(self, brand, year):
        self.brand = brand
        self.year = year
    def drive(self):
        print(f"{self.brand} is driving")

mycar = Car("Tesla", 2024)
mycar.drive()
```
👉 `__init__` automatically runs when an object is created.

---

## 8. **DATA MINING**

**Definition:**  
Extracting useful patterns, insights, or predictions from large datasets.

**Concept:**  
It’s part of Machine Learning — using algorithms to find patterns.

**Common Tools:**

| Task | Package / Function |
|-------|--------------------|
| Preprocessing | `pandas`, `sklearn.preprocessing` |
| Splitting data | `train_test_split()` |
| Model training | `.fit()` |
| Prediction | `.predict()` |
| Evaluation | `accuracy_score()`, `r2_score()` |

**Example:**
```python
from sklearn.cluster import KMeans
kmeans = KMeans(n_clusters=3).fit(X)
print(kmeans.labels_)
```

---

## 9. **LISTS**

**Definition:**  
Ordered, mutable collection of items — most used Python data type.

**Concept:**  
Lists hold multiple values (numbers, strings, objects) and can be modified.

**Key Methods:**

| Method | Description |
|---------|-------------|
| `append()`, `extend()` | Add items |
| `insert(index, value)` | Insert item |
| `remove()`, `pop()` | Delete item |
| `sort()`, `reverse()` | Reorder |
| `count()`, `index()` | Info about elements |

**Example:**
```python
nums = [3,1,4,1,5]
nums.sort()
nums.append(9)
print(nums)
```

---

## 10. **IMPORT / EXPORT DATA**

**Definition:**  
Bringing data into Python or saving it back after analysis.

**Concept:**  
Pandas makes this super easy — supports Excel, CSV, JSON, SQL, HTML.

**Functions:**

| Format | Import | Export |
|---------|---------|---------|
| CSV | `pd.read_csv()` | `to_csv()` |
| Excel | `pd.read_excel()` | `to_excel()` |
| JSON | `pd.read_json()` | `to_json()` |
| SQL | `pd.read_sql()` | `to_sql()` |

**Example:**
```python
df = pd.read_csv("sales.csv")
df.to_excel("sales.xlsx", index=False)
```

---

## 11. **CHARTS & GRAPHS**

**Definition:**  
Visual representation of data for quick insight.

**Concept:**  
Plots make patterns easier to spot — trends, comparisons, relationships.

**Main Libraries:**

| Library | Example Function | Purpose |
|----------|------------------|----------|
| matplotlib | `plt.plot()`, `plt.bar()` | Basic plots |
| seaborn | `sns.heatmap()`, `sns.boxplot()` | Stylish, statistical plots |
| plotly | `px.bar()`, `px.scatter()` | Interactive charts |

**Example:**
```python
import matplotlib.pyplot as plt
x = [1,2,3]; y = [2,4,6]
plt.plot(x, y, mar