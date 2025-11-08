## 🐍 DATA ANALYTICS WITH PYTHON

### 📘 Detailed & Conceptual Notes
*(IFSCA Phase-II IT — Paper II: Python Analytics Section)*

---

### 1️⃣ REGEX (Regular Expressions)

**Definition:**
Regular Expressions are smart patterns used to match, extract, or replace strings using the `re` module.

**Concept:**
Instead of searching text manually, regex lets you describe what you want — e.g., digits, words, email IDs.

#### Common Functions
| Function | Description |
|-----------|-------------|
| re.search(pattern, string) | Finds the first match |
| re.findall(pattern, string) | Returns all matches as list |
| re.match(pattern, string) | Matches only from start |
| re.sub(pattern, repl, string) | Replaces occurrences |
| re.split(pattern, string) | Splits string by pattern |
| re.compile(pattern) | Compiles regex for reuse |

#### Example
```python
import re
text = "Emails: test@mail.com, info@abc.org"
emails = re.findall(r'\b[\w\.-]+@[\w\.-]+\.\w{2,4}\b', text)
print(emails)
# Output: ['test@mail.com', 'info@abc.org']
```
👉 `findall()` extracts all substrings that match the pattern.

---

### 2️⃣ SLICING

**Definition:**
Slicing extracts parts of a sequence (list, string, or tuple) using index ranges.

**Syntax:**
`sequence[start:end:step]` → extracts from start to end-1, moving by step.

#### Examples
```python
nums = [10, 20, 30, 40, 50, 60]
print(nums[1:4])    # [20, 30, 40]
print(nums[:3])     # [10, 20, 30]
print(nums[3:])     # [40, 50, 60]
print(nums[-3:])    # [40, 50, 60]
print(nums[:-2])    # [10, 20, 30, 40]
print(nums[::-1])   # [60, 50, 40, 30, 20, 10]
print(nums[-1:-5:-1])  # [60, 50, 40, 30]
```
👉 Negative indices start from the end, and `[::-1]` reverses a list.

---

### 3️⃣ DATA RESHAPING

**Definition:**
Transforming data structure — from wide to long or vice versa — using `pandas`.

**Concept:**
- **Wide → Long:** multiple columns become rows (tidy format)
- **Long → Wide:** rows expand into new columns

#### Example
```python
import pandas as pd

# Original wide data
df = pd.DataFrame({
    'Year': [2023, 2024],
    'Sales_A': [100, 120],
    'Sales_B': [90, 110]
})
print(df)

# Wide → Long
df_long = pd.melt(df, id_vars='Year', var_name='Product', value_name='Sales')
print(df_long)

# Long → Wide
df_wide = df_long.pivot(index='Year', columns='Product', values='Sales')
print(df_wide)
```
👉 `melt()` makes datasets tidy; `pivot()` restores them.

---

### 4️⃣ DATAFRAMES

**Definition:**
A DataFrame is a 2D labeled table of data (rows & columns) using pandas.

#### Common Methods with Examples
```python
import pandas as pd
df = pd.DataFrame({'Name':['A','B','C'], 'Age':[23,24,22], 'Dept':['IT','HR','IT']})

print(df.head(2))
df.info()
print(df.describe())
print(df.loc[0, 'Name'])
print(df.iloc[1, 1])
print(df.sort_values('Age'))
print(df.drop('Dept', axis=1))
print(df.rename(columns={'Dept':'Department'}))

dept_df = pd.DataFrame({'Dept':['IT','HR'], 'Manager':['Tom','Jane']})
merged = pd.merge(df, dept_df, on='Dept')
print(merged)
```
👉 `df` is just a variable name for your dataset.

---

### 5️⃣ DICTIONARIES & SETS

#### Dictionary
Stores key–value pairs (unordered, mutable).
```python
d = {'a': 1, 'b': 2, 'c': 3}
print(d.get('b'))
print(list(d.keys()))
print(list(d.values()))
print(list(d.items()))
d.update({'d': 4})
print(d)
print(d.pop('a'))
print(d)
d.clear()
print(d)
```
👉 `get()` avoids errors; `update()` merges; `pop()` removes a key.

#### Set
Stores unique unordered items — no duplicates.
```python
s = {1, 2, 3}
s.add(4)
s.remove(2)
s2 = {3, 4, 5}
print(s.union(s2))
print(s.intersection(s2))
print(s.difference(s2))
print(s.symmetric_difference(s2))
```
👉 Useful for mathematical set operations.

---

### 6️⃣ FILE MANAGEMENT

**Concept:**
Read/write files using Python’s `open()` or pandas.

#### Example
```python
# Writing to file
with open('test.txt', 'w') as f:
    f.write("Hello IFSCA")

# Reading file
with open('test.txt', 'r') as f:
    data = f.read()
print(data)
```
Using pandas:
```python
import pandas as pd
df = pd.DataFrame({'Name':['A','B'], 'Age':[23,24]})
df.to_csv('data.csv', index=False)
new_df = pd.read_csv('data.csv')
print(new_df)
```

---

### 7️⃣ CLASSES & FUNCTIONS

#### Functions Example
```python
def greet(name):
    return f"Hello, {name}"
print(greet("IFSCA"))
```

#### Class Example
```python
class Car:
    def __init__(self, brand, year):
        self.brand = brand
        self.year = year

    def drive(self):
        return f"{self.brand} ({self.year}) is driving."

mycar = Car("Tesla", 2025)
print(mycar.drive())
```

---

### 8️⃣ DATA MINING

**Concept:**
Extract patterns from data using ML algorithms.
```python
from sklearn.cluster import KMeans
import numpy as np
X = np.array([[1,2],[2,3],[10,11],[11,12]])
kmeans = KMeans(n_clusters=2, n_init=5).fit(X)
print(kmeans.labels_)
```

---

### 9️⃣ LISTS

**Concept:**
Ordered, mutable sequence of elements.
```python
nums = [3, 1, 4, 1, 5]
nums.append(9)
nums.extend([2,6])
nums.insert(2, 10)
nums.remove(1)
print(nums.pop())
nums.sort()
nums.reverse()
print(nums.count(10))
print(nums.index(5))
```
👉 Each method modifies or gives info about the list.

---

### 🔟 IMPORT / EXPORT DATA

**Concept:**
Use pandas for file I/O.
```python
import pandas as pd
df = pd.read_csv("sales.csv")
df.to_excel("sales.xlsx", index=False)
df2 = pd.read_json("data.json")
```

---

### 1️⃣1️⃣ CHARTS & GRAPHS

**Concept:**
Visualize data trends using `matplotlib` and `seaborn`.
```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd

df = pd.DataFrame({'Year':[2022,2023,2024], 'Sales':[200,300,250]})

plt.plot(df['Year'], df['Sales'])
plt.title("Yearly Sales Trend")
plt.show()

plt.bar(df['Year'], df['Sales'])
plt.show()

plt.scatter(df['Year'], df['Sales'])
plt.show()

data = [[1,2,3],[4,5,6],[7,8,9]]
sns.heatmap(data, annot=True)
plt.show()
```
👉 `plt.plot()` → line graph | `plt.bar()` → bar chart | `plt.scatter()` → relationships | `sns.heatmap()` → color grid.

