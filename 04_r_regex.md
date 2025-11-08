🧮 **DATA ANALYTICS WITH R (Detailed Notes)**

---

### 1. REGEX (Regular Expressions)

**Definition:**  
Regular expressions in R are patterns used to search, match, and replace text within strings.

**Concept:**  
Regex works like a smart text filter — instead of manually checking words, you define patterns to match digits, emails, or capitalized words.

**Key Functions:**

| Function | Description |
|-----------|--------------|
| `grep(pattern, x)` | Returns index positions where pattern is found |
| `grepl(pattern, x)` | Returns TRUE/FALSE for matches |
| `gsub(pattern, replacement, x)` | Replaces all matches |
| `sub(pattern, replacement, x)` | Replaces first match |
| `regexpr(pattern, x)` | Gives position and length of first match |
| `gregexpr(pattern, x)` | Gives all match positions |
| `regmatches(x, regexpr())` | Extracts matched substrings |

**Example:**
```r
text <- "Data123 Science"
gsub("[0-9]", "#", text)
# Output: "Data### Science"
```
👉 `[0-9]` means any digit. `gsub()` replaces all of them.

**Practice:**
```r
regmatches(text, gregexpr("[A-Z][a-z]+", text))  # Extract capitalized words
gsub("\\d", "*", text)                         # Replace all digits
```

**MCQs:**
- Replace all matches → ✅ `gsub()`  
- Return TRUE/FALSE for matches → ✅ `grepl()`  
- `grep()` returns → ✅ Index positions

---

### 2. SLICING (Subsetting)

**Definition:** Selecting a portion (subset) of vectors, lists, or data frames.

**Concept:**  
R uses square brackets `[ ]` to extract data. Indexing starts at 1 (not 0 like Python). Selection can be by position, condition, or name.

**Syntax:**
```r
v[2:5]         # Elements 2–5
v[-1]          # All except 1st element
v[v > 10]      # Conditional selection
df[1:3, ]      # Rows 1–3
df[, "col"]     # Specific column
```
**Example:**
```r
v <- c(10, 20, 30, 40, 50)
v[2:4]  # 20 30 40
v[-1]   # Drops first element
```
👉 Slicing helps extract required portions without loops.

---

### 3. DATA RESHAPING

**Definition:** Changing data layout between wide (many columns) and long (many rows).

**Concept:** Transforming data between formats for analysis — `wide → long` or `long → wide`.

**Key Functions:**

| Function | Library | Description |
|-----------|----------|-------------|
| `melt()` | reshape2 | Convert wide → long |
| `dcast()` | reshape2 | Convert long → wide |
| `pivot_longer()` | tidyr | Modern wide → long |
| `pivot_wider()` | tidyr | Modern long → wide |
| `spread(), gather()` | tidyr (legacy) | Older equivalents |

**Example:**
```r
library(tidyr)
df <- data.frame(Year=c(2023,2024), Sales_A=c(100,120), Sales_B=c(90,110))

# Convert wide → long
df_long <- pivot_longer(df, cols=c(Sales_A, Sales_B), names_to="Product", values_to="Sales")
```
👉 `pivot_longer()` keeps Year as identifier and converts Sales columns into key–value pairs.

---

### 4. DATAFRAMES

**Definition:** A `data.frame` is R’s most common tabular data structure — similar to an Excel sheet.

**Concept:** Each column can have different data types (numeric, character, factor, etc.). You can view, subset, sort, and merge easily.

**Key Functions:**

| Function | Description |
|-----------|--------------|
| `data.frame()` | Create data frame |
| `head(), tail()` | View first/last rows |
| `names(), str(), summary()` | Inspect structure |
| `subset(df, condition)` | Filter rows |
| `merge(df1, df2, by="col")` | Join by key |
| `rbind(), cbind()` | Add rows or columns |
| `apply(), lapply(), sapply()` | Apply functions to data |

**Example:**
```r
df <- data.frame(Name=c("A","B"), Age=c(23,25))
subset(df, Age > 23)
```
👉 `df` stores data in rows and columns for easy analysis.

---

### 5. LISTS & SETS (Vectors)

**Definition:** Lists store heterogeneous elements; sets in R are handled via unique vectors.

**Concept:** Lists can hold mixed types; sets are unique-element vectors.

**Functions:**

| Function | Description |
|-----------|--------------|
| `list()` | Create list |
| `unlist()` | Flatten list |
| `unique()` | Remove duplicates |
| `union(), intersect(), setdiff()` | Set operations |
| `length()` | Count elements |

**Example:**
```r
a <- c(1,2,3)
b <- c(3,4,5)
union(a,b)      # 1 2 3 4 5
intersect(a,b)  # 3
```
👉 `union()` keeps unique values; `intersect()` keeps common ones.

---

### 6. FILE MANAGEMENT

**Definition:** Reading from and writing to files.

**Concept:** R provides built-in functions for structured (CSV, text) and native (.RData) files.

| Function | Purpose |
|-----------|----------|
| `read.csv()` | Load CSV data |
| `write.csv()` | Save to CSV |
| `read.table()` | Import text files |
| `save()` | Save R object |
| `load()` | Load saved object |
| `sink()` | Redirect output |
| `file.exists(), file.remove()` | Check/delete file |

**Example:**
```r
data <- read.csv("sales.csv")
write.csv(data, "new_sales.csv", row.names=FALSE)
```
👉 Always set `row.names=FALSE` to avoid extra index columns.

---

### 7. FUNCTIONS & CLASSES

**Definition:** Functions organize reusable logic; classes define structured objects.

**Concept:** Functions make code modular. R supports S3, S4, and R6 class systems for OOP.

**Function Example:**
```r
add <- function(a, b = 0) {
  return(a + b)
}
add(5, 3)  # 8
```

**Apply Family:**

| Function | Use |
|-----------|------|
| `apply()` | Apply over rows/columns of matrix |
| `lapply()` | Apply to list elements (returns list) |
| `sapply()` | Simplified apply (vector/matrix) |
| `tapply()` | Apply function by group |

**Classes:**
- **S3:** Simple, flexible (default)
- **S4:** Formal, type-checked
- **R6:** Modern OOP (used in big packages)

---

### 8. DATA MINING

**Definition:** Extracting patterns or predictive models from datasets.

**Concept:** R uses ML libraries like `caret`, `rpart`, `randomForest`, and `e1071` for data mining.

| Task | Function |
|------|-----------|
| Data split | `sample.split()` (caTools) |
| Train model | `train()` (caret) |
| Decision tree | `rpart()` |
| Prediction | `predict()` |
| Accuracy | `confusionMatrix()` |

**Example:**
```r
library(rpart)
fit <- rpart(Species ~ ., data = iris)
predict(fit, iris, type = "class")
```
👉 `rpart()` builds a tree; `predict()` applies it.

---

### 9. IMPORT / EXPORT DATA

**Definition:** Transferring data between R and external formats (Excel, JSON, SQL, etc.).

**Concept:** R supports multiple data sources via packages.

| Format | Import | Export |
|---------|---------|---------|
| CSV | `read.csv()` | `write.csv()` |
| Excel | `readxl::read_excel()` | `writexl::write_xlsx()` |
| JSON | `jsonlite::fromJSON()` | `toJSON()` |
| SQL | `RSQLite::dbReadTable()` | `dbWriteTable()` |

**Example:**
```r
library(readxl)
data <- read_excel("sales.xlsx")
```

---

### 10. CHARTS & GRAPHS

**Definition:** Visualizing data for insights using base R, ggplot2, or plotly.

**Concept:** Helps detect trends, patterns, and outliers.

| Library | Function | Description |
|----------|-----------|-------------|
| base | `plot()`, `hist()`, `boxplot()`, `barplot()` | Basic charts |
| ggplot2 | `ggplot() + geom_*()` | Grammar of Graphics |
| plotly | `plot_ly()` | Interactive graphs |

**Example:**
```r
library(ggplot2)
ggplot(mtcars, aes(x=mpg, y=hp)) +
  geom_point(color="blue") +
  ggtitle("Horsepower vs MPG")
```
👉 Each `geom_*()` adds a visualization layer.

---

### ✅ Summary Notes

| Concept | Python Equivalent | R Equivalent |
|----------|--------------------|---------------|
| DataFrame | `pd.DataFrame()` | `data.frame()` |
| Regex | `re` module | `grep`, `gsub`, `regexpr` |
| Reshaping | `pd.melt() / pivot()` | `pivot_longer() / pivot_wider()` |
| File I/O | `open()`, `read_csv()` | `read.csv()`, `save()` |
| Visualization | `matplotlib`, `seaborn` | `ggplot2`, `plotly` |

