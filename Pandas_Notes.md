
## 🧾 **Complete Pandas Roadmap for Data Analysts**

Below is the **chapter-wise breakdown** (like a textbook), organized from **beginner → advanced**, with short notes on what to master in each.

---

### 📘 **Chapter 1: Introduction to Pandas**

**Goal:** Understand what Pandas is and why it’s essential.
**Topics:**

* What is Pandas and its role in Data Analysis
* Installation and importing (`import pandas as pd`)
* Pandas data structures: `Series` and `DataFrame`
* Creating a DataFrame from:

  * Dictionary
  * Lists of lists
  * CSV/Excel files

**Key functions:**
`pd.Series()`, `pd.DataFrame()`, `pd.read_csv()`, `pd.read_excel()`

---

### 📊 **Chapter 2: DataFrame Basics**

**Goal:** Learn to inspect, understand, and explore datasets.
**Topics:**

* Viewing top and bottom rows → `.head()`, `.tail()`
* Basic info → `.info()`, `.shape`, `.columns`, `.dtypes`
* Statistical summary → `.describe()`
* Accessing data:

  * `df['column']`
  * `.iloc[]`, `.loc[]`, `.at[]`, `.iat[]`

**Practice:**
Load a CSV (like sales or employee data) and try exploring it using these functions.

---

### ✂️ **Chapter 3: Data Selection, Filtering & Sorting**

**Goal:** Learn to extract and filter the data you need.
**Topics:**

* Selecting columns and rows
* Conditional filtering (`df[df['Salary'] > 50000]`)
* Multiple conditions (`&`, `|`, `~`)
* Sorting: `.sort_values()`, `.sort_index()`
* Renaming columns: `.rename()`

**Practice:**
Replicate SQL’s `SELECT`, `WHERE`, and `ORDER BY` using Pandas syntax.

---

### 🧹 **Chapter 4: Data Cleaning & Transformation**

**Goal:** Handle missing, inconsistent, and dirty data.
**Topics:**

* Handling missing values:

  * `.isnull()`, `.notnull()`, `.dropna()`, `.fillna()`
* Replacing values: `.replace()`
* Changing data types: `.astype()`
* Removing duplicates: `.drop_duplicates()`
* String operations: `.str.lower()`, `.str.contains()`, `.str.strip()`

**Practice:**
Simulate cleaning a messy CSV (like null emails, wrong salary formats).

---

### 🧮 **Chapter 5: Aggregation & Grouping**

**Goal:** Summarize and analyze data by category (like SQL `GROUP BY`).
**Topics:**

* Grouping data: `.groupby()`
* Aggregations: `.sum()`, `.mean()`, `.count()`, `.agg()`
* Multi-level grouping
* Pivot tables: `pd.pivot_table()`

**Practice:**
Replicate SQL queries such as:

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department;
```

in Pandas:

```python
df.groupby('department')['salary'].mean()
```

---

### 🔗 **Chapter 6: Merging, Joining, and Concatenating**

**Goal:** Combine data from multiple sources (like SQL `JOIN`).
**Topics:**

* `pd.concat()` – stacking data vertically or horizontally
* `pd.merge()` – joining tables (`inner`, `outer`, `left`, `right`)
* Joining on multiple keys

**Practice:**
Combine two dataframes (employees & departments) and mimic SQL joins.

---

### 📆 **Chapter 7: Working with Dates & Time**

**Goal:** Handle time-based data like sales, logs, or transactions.
**Topics:**

* Converting columns to datetime: `pd.to_datetime()`
* Extracting year/month/day/hour
* Filtering by date range
* Resampling time series (daily, weekly, monthly): `.resample()`
* Time-based grouping

**Practice:**
Aggregate monthly sales totals or calculate weekly averages.

---

### 📈 **Chapter 8: Data Visualization with Pandas**

**Goal:** Build quick insights directly from Pandas.
**Topics:**

* Built-in plotting: `.plot()`
* Bar, line, scatter, histogram plots
* Customizing visuals with `matplotlib`

**Practice:**
Create bar charts for revenue by region or trend lines for growth.

---

### 🧠 **Chapter 9: Advanced Pandas Operations**

**Goal:** Learn high-level transformations and performance tuning.
**Topics:**

* Apply functions: `.apply()`, `.map()`, `.applymap()`
* Lambda functions
* Vectorization for performance
* Handling multi-index dataframes
* `pd.cut()` and `pd.qcut()` for binning

**Practice:**
Apply functions to transform entire columns or categorize continuous data.

---

### 🧾 **Chapter 10: Input/Output & Exporting Data**

**Goal:** Save and load data efficiently.
**Topics:**

* Reading: CSV, Excel, JSON, SQL databases
* Writing: `.to_csv()`, `.to_excel()`, `.to_sql()`
* Reading data from APIs (using `requests` + Pandas)

**Practice:**
Export your cleaned dataset into a CSV for Power BI or Excel use.

---

### ⚙️ **Optional (Advanced for Analysts):**

**Chapter 11: Pandas + SQL Integration**

* Query databases directly using Pandas (`pd.read_sql()`)
* Combine SQL querying power with Pandas analysis

**Chapter 12: Pandas + NumPy + Matplotlib**

* Integrate numeric computing (`NumPy`) and visualization (`Matplotlib`)
* Build complete analysis pipelines

---

## 🧭 **Summary Table**

| Level                | Chapters | Focus                                         |
| -------------------- | -------- | --------------------------------------------- |
| 🟢 Beginner          | 1 – 3    | Pandas basics, filtering, and selection       |
| 🟡 Intermediate      | 4 – 6    | Cleaning, grouping, and merging               |
| 🔵 Advanced          | 7 – 9    | Date/time, visualization, and apply functions |
| ⚙️ Expert / Optional | 10 – 12  | SQL integration, optimization, and pipelines  |

---

### 🧩 **Estimated Coverage for a Data Analyst**

You should **master Chapters 1–9** (that’s about **75–80% of Pandas**).
Chapters 10–12 are **optional** but highly valuable for working with real-world data and dashboards.

---

---

# 🧾 **Pandas Chapter 1 — Introduction to Pandas**

---

## 🧠 **Concept Notes (Chapter 1)**

### 📘 **What is Pandas?**

**Pandas** (short for *Python Data Analysis Library*) is an open-source library built on top of **NumPy**, designed for **data manipulation, cleaning, and analysis**.

It provides two powerful data structures:

* **Series** → 1-D labeled array (like a column in Excel)
* **DataFrame** → 2-D labeled data (like a spreadsheet or SQL table)

---

### ⚙️ **Installing Pandas**

```bash
pip install pandas
```

Importing Pandas in Python:

```python
import pandas as pd
```

---

### 📊 **1. Pandas Data Structures**

#### 🔹 Series

A one-dimensional labeled array capable of holding any data type.

```python
import pandas as pd
s = pd.Series([10, 20, 30, 40])
print(s)
```

Output:

```
0    10
1    20
2    30
3    40
dtype: int64
```

👉 Default index starts from 0.

You can customize the index:

```python
s = pd.Series([10, 20, 30], index=['A', 'B', 'C'])
```

---

#### 🔸 DataFrame

A two-dimensional, tabular data structure — similar to an Excel sheet or SQL table.

Creating a DataFrame from a dictionary:

```python
data = {
    'Name': ['Ayaan', 'Ravi', 'Neha'],
    'Age': [31, 25, 28],
    'City': ['Lucknow', 'Delhi', 'Mumbai']
}
df = pd.DataFrame(data)
print(df)
```

Output:

```
    Name  Age     City
0  Ayaan   31  Lucknow
1   Ravi   25    Delhi
2   Neha   28   Mumbai
```

---

### 🧩 **2. Creating DataFrames from Different Sources**

| Source        | Function             | Example                       |
| ------------- | -------------------- | ----------------------------- |
| Dictionary    | `pd.DataFrame()`     | `pd.DataFrame(data)`          |
| List of lists | `pd.DataFrame(list)` | `pd.DataFrame([[1,2],[3,4]])` |
| CSV file      | `pd.read_csv()`      | `pd.read_csv('data.csv')`     |
| Excel file    | `pd.read_excel()`    | `pd.read_excel('data.xlsx')`  |

---

### 📋 **3. Basic DataFrame Operations**

```python
df.head()         # View first 5 rows
df.tail(3)        # View last 3 rows
df.info()         # Get column names, types, null counts
df.describe()     # Summary statistics (mean, std, etc.)
df.shape          # (rows, columns)
df.columns        # List of column names
df.dtypes         # Data types of each column
```

---

### 🔍 **4. Accessing Data**

#### Select one column:

```python
df['Name']
```

#### Select multiple columns:

```python
df[['Name', 'City']]
```

#### Select rows by index:

```python
df.loc[0]        # Label-based
df.iloc[1]       # Position-based
```

---

### 🧮 **5. Adding & Deleting Columns**

#### Add new column:

```python
df['Country'] = 'India'
```

#### Delete column:

```python
df.drop('Age', axis=1, inplace=True)
```

---

### 🧰 **6. Exporting Data**

Save your DataFrame for reuse:

```python
df.to_csv('output.csv', index=False)
df.to_excel('output.xlsx', index=False)
```

---

## 🧾 **Quick Summary**

| Concept            | Description                         |
| ------------------ | ----------------------------------- |
| **Series**         | 1D labeled data                     |
| **DataFrame**      | 2D table with rows and columns      |
| **Read CSV/Excel** | `pd.read_csv()`, `pd.read_excel()`  |
| **Inspect data**   | `.head()`, `.info()`, `.describe()` |
| **Select data**    | `.loc[]`, `.iloc[]`, column names   |
| **Save data**      | `.to_csv()`, `.to_excel()`          |

---

# 🧩 **Pandas Chapter 1 — Practice Sheet**

Try these hands-on exercises in your Jupyter Notebook or VS Code:

---

### **🧠 Basic Exercises**

**Q1.** Import Pandas and create a Series of your 5 favorite numbers.
**Q2.** Create a Series with index labels: `A, B, C, D, E`.
**Q3.** Create a DataFrame with columns:

* Name
* Age
* City
* Profession

and fill with at least 4 sample rows.

**Q4.** Load the following dictionary into a DataFrame:

```python
data = {
    'Product': ['Laptop', 'Tablet', 'Phone'],
    'Price': [70000, 25000, 40000],
    'Stock': [50, 80, 150]
}
```

**Q5.** Display:

* First 2 rows
* Info about the DataFrame
* Data types of all columns

---

### **⚙️ Intermediate Exercises**

**Q6.** Add a new column `Discount` = 10% of `Price`.
**Q7.** Delete the `Stock` column.
**Q8.** Rename `Price` → `UnitPrice`.
**Q9.** Display only `Product` and `UnitPrice` columns.
**Q10.** Export your DataFrame to `products.csv`.

---

### **💡 Challenge Question**

Read the `products.csv` file you just saved, and:

1. Display all rows where `UnitPrice > 30000`.
2. Count how many rows satisfy this condition.
3. Print only the `Product` names that meet it.

---

---

# 🧾 **Pandas Chapter 2 — DataFrame Basics**

---

## 🧠 **Concept Notes**

### 📘 **1. What is a DataFrame?**

A **DataFrame** is a **2D labeled data structure** (rows × columns).
Think of it like an **Excel sheet** or an **SQL table**.

You can load data from multiple sources:

```python
import pandas as pd

# From dictionary
data = {
    'Name': ['Ayaan', 'Ravi', 'Neha', 'Pooja'],
    'Age': [31, 25, 28, 30],
    'City': ['Lucknow', 'Delhi', 'Mumbai', 'Kolkata']
}
df = pd.DataFrame(data)
```

---

### 📋 **2. Inspecting DataFrames**

Before analysis, always **inspect your dataset** to understand its structure and health.

| Method          | Description                                        |
| --------------- | -------------------------------------------------- |
| `df.head()`     | View first 5 rows (use `df.head(10)` for more)     |
| `df.tail()`     | View last 5 rows                                   |
| `df.shape`      | Returns (rows, columns)                            |
| `df.columns`    | Shows column names                                 |
| `df.index`      | Shows row index range                              |
| `df.dtypes`     | Displays data types of columns                     |
| `df.info()`     | Overview — column names, non-null count, data type |
| `df.describe()` | Statistical summary for numeric columns            |

Example:

```python
df.head()
df.info()
df.describe()
```

---

### 📊 **3. Accessing Columns**

#### Single column:

```python
df['Name']
```

or

```python
df.Name   # Works only if column name has no spaces
```

#### Multiple columns:

```python
df[['Name', 'City']]
```

---

### 🔍 **4. Accessing Rows**

| Method              | Type           | Description               |
| ------------------- | -------------- | ------------------------- |
| `df.loc[label]`     | Label-based    | Access by row index label |
| `df.iloc[position]` | Position-based | Access by integer index   |

Examples:

```python
df.loc[0]      # Row with index label 0
df.iloc[2]     # Third row (index 2)
```

Select multiple rows:

```python
df.loc[0:2]      # From index 0 to 2 (inclusive)
df.iloc[0:3]     # From 0 to 2 (exclusive)
```

---

### 🎯 **5. Selecting Specific Rows and Columns Together**

```python
df.loc[0, 'Name']                 # Single cell
df.loc[0:2, ['Name', 'City']]     # Rows 0–2, specific columns
df.iloc[1:3, 0:2]                 # By numeric positions
```

---

### ✏️ **6. Modifying Data**

#### Add a new column:

```python
df['Country'] = 'India'
```

#### Update values:

```python
df.loc[df['Name'] == 'Ravi', 'City'] = 'Bangalore'
```

#### Delete a column:

```python
df.drop('Country', axis=1, inplace=True)
```

#### Rename columns:

```python
df.rename(columns={'Name': 'FullName'}, inplace=True)
```

---

### 🧮 **7. Summarizing Data**

| Function               | Purpose                          |
| ---------------------- | -------------------------------- |
| `df.count()`           | Count non-null entries           |
| `df.mean()`            | Column-wise mean                 |
| `df.min()`, `df.max()` | Minimum / Maximum values         |
| `df.value_counts()`    | Count frequency of unique values |

Examples:

```python
df['Age'].mean()
df['City'].value_counts()
```

---

### ⚙️ **8. Checking for Missing Data**

```python
df.isnull()          # Shows True/False for nulls
df.isnull().sum()    # Count missing values per column
```

Replace missing values:

```python
df['Age'].fillna(df['Age'].mean(), inplace=True)
```

---

### 📦 **9. Sorting and Reordering**

Sort rows or columns for easier analysis.

#### Sort by column:

```python
df.sort_values(by='Age', ascending=False)
```

#### Sort by multiple columns:

```python
df.sort_values(by=['City', 'Age'], ascending=[True, False])
```

#### Reorder columns:

```python
df = df[['City', 'Name', 'Age']]
```

---

### 💾 **10. Copying and Exporting DataFrames**

Make safe edits or save your progress:

```python
df_copy = df.copy()
df.to_csv('clean_data.csv', index=False)
```

---

## 🧾 **Quick Summary**

| Concept            | Function                                    |
| ------------------ | ------------------------------------------- |
| View data          | `.head()`, `.tail()`, `.info()`             |
| Column access      | `df['col']`, `df[['col1', 'col2']]`         |
| Row access         | `.loc[]` (labels), `.iloc[]` (indexes)      |
| Add/delete columns | `df['new']`, `.drop()`                      |
| Rename columns     | `.rename()`                                 |
| Check nulls        | `.isnull()`, `.fillna()`                    |
| Sort data          | `.sort_values()`                            |
| Summary stats      | `.describe()`, `.mean()`, `.value_counts()` |

---

# 🧩 **Pandas Chapter 2 — Practice Sheet**

Let’s strengthen your understanding with real exercises 👇

---

### 🧠 **Level 1: Basic Understanding**

**Q1.** Create a DataFrame of employees with columns:
`['Name', 'Department', 'Salary', 'City']`
and at least 5 rows of sample data.

**Q2.** Display:

* First 3 rows
* Total number of rows and columns
* Column names and data types

**Q3.** Show only the ‘Name’ and ‘Salary’ columns.

**Q4.** Access:

* 2nd row using `.iloc[]`
* Last row using `.tail(1)`

---

### ⚙️ **Level 2: Data Manipulation**

**Q5.** Add a new column `Bonus` = 10% of `Salary`.
**Q6.** Rename column `Department` → `Dept`.
**Q7.** Sort the DataFrame by `Salary` in descending order.
**Q8.** Delete the column `Bonus`.
**Q9.** Display employees whose `Salary` > 50,000.

---

### 💡 **Level 3: Analysis Challenges**

**Q10.** Count how many employees belong to each department.
**Q11.** Find the **average salary** of all employees.
**Q12.** Replace any missing `City` values with `'Unknown'`.
**Q13.** Create a copy of your DataFrame and save it as `employees_clean.csv`.

---

### 🧠 **Mini Project Challenge**

Create a DataFrame for a small **student performance dataset**:
Columns → `['Name', 'Math', 'Science', 'English']`
Then perform:

1. Find the average score for each student.
2. Find the student with the highest total score.
3. Sort by total marks (descending).
4. Save the results to `student_scores.csv`.

---

---

# 🧾 **Pandas Chapter 3 — Data Selection, Filtering & Sorting**

---

## 🧠 **Concept Notes**

---

### 📘 **1. Selecting Data**

#### 🔹 Select Columns

Select one column:

```python
df['Salary']
```

Select multiple columns:

```python
df[['Name', 'Salary']]
```

You can also reorder columns:

```python
df = df[['Salary', 'Name', 'City']]
```

---

#### 🔹 Select Rows by Index

| Method         | Description                    | Example      |
| -------------- | ------------------------------ | ------------ |
| `df.loc[]`     | Label-based access             | `df.loc[2]`  |
| `df.iloc[]`    | Position-based access          | `df.iloc[2]` |
| `df.loc[2:5]`  | Select rows 2 to 5 (inclusive) |              |
| `df.iloc[0:5]` | Select rows 0–4 (exclusive)    |              |

Example:

```python
df.loc[0:3, ['Name', 'City']]
df.iloc[0:3, 0:2]
```

---

#### 🔹 Select Specific Rows & Columns Together

```python
df.loc[1:3, ['Name', 'Salary']]
```

This returns rows 1–3 with only `Name` and `Salary` columns.

---

### 🔍 **2. Filtering Data (Like SQL WHERE Clause)**

Filtering lets you **extract specific subsets** of your data based on conditions.

#### Basic Filtering:

```python
df[df['Salary'] > 50000]
```

#### Multiple Conditions:

Use **`&`** (AND), **`|`** (OR), and **`~`** (NOT) operators.

```python
df[(df['Salary'] > 50000) & (df['Department'] == 'Finance')]
df[(df['City'] == 'Delhi') | (df['City'] == 'Mumbai')]
df[~(df['City'] == 'Delhi')]     # Exclude Delhi
```

💡 *Note: Always wrap each condition in parentheses `()`.*

---

#### Filtering with Text Functions:

Use `.str` accessor for text operations.

```python
df[df['Name'].str.startswith('A')]
df[df['City'].str.contains('del', case=False)]
```

---

#### Filtering Null or Missing Data:

```python
df[df['City'].isnull()]
df[df['City'].notnull()]
```

---

### 📊 **3. Conditional Filtering (Range or Membership)**

#### Using `.isin()` → similar to SQL `IN`

```python
df[df['City'].isin(['Delhi', 'Lucknow'])]
```

#### Using `.between()` → for numeric ranges

```python
df[df['Salary'].between(30000, 60000)]
```

---

### 🔁 **4. Sorting Data**

#### Sort by Column

```python
df.sort_values(by='Salary')  # Ascending by default
```

#### Sort in Descending Order

```python
df.sort_values(by='Salary', ascending=False)
```

#### Sort by Multiple Columns

```python
df.sort_values(by=['Department', 'Salary'], ascending=[True, False])
```

---

### 🧩 **5. Reset and Set Index**

Reset the index after filtering or sorting:

```python
df.reset_index(drop=True, inplace=True)
```

Set a column as index:

```python
df.set_index('Name', inplace=True)
```

Reset back:

```python
df.reset_index(inplace=True)
```

---

### 📋 **6. Conditional Assignment**

You can update values based on conditions (like SQL’s CASE WHEN).

```python
df.loc[df['Salary'] > 60000, 'Status'] = 'High Earner'
df.loc[df['Salary'] <= 60000, 'Status'] = 'Average'
```

---

### 📈 **7. Combining Filtering and Sorting**

Example:

```python
df_filtered = df[df['Department'] == 'IT']
df_sorted = df_filtered.sort_values(by='Salary', ascending=False)
```

Or combine directly:

```python
df[df['Department'] == 'IT'].sort_values(by='Salary', ascending=False)
```

---

### 💾 **8. Practical Tip for Data Analysts**

Filtering and sorting are your bread and butter for:

* Finding **top performers** or **highest sales**
* Filtering **region-specific data**
* Preparing data for **Power BI dashboards**
* Extracting subsets for Excel export

---

## 🧾 **Quick Summary**

| Concept            | Function                               |        |
| ------------------ | -------------------------------------- | ------ |
| Select columns     | `df['col']`, `df[['col1','col2']]`     |        |
| Select rows        | `.loc[]`, `.iloc[]`                    |        |
| Filter numeric     | `df[df['Salary'] > 50000]`             |        |
| Filter multiple    | `&`, `                                 | `, `~` |
| Filter text        | `.str.contains()`, `.str.startswith()` |        |
| Filter range       | `.between()`                           |        |
| Filter in list     | `.isin()`                              |        |
| Sort               | `.sort_values()`                       |        |
| Set index          | `.set_index()`, `.reset_index()`       |        |
| Conditional update | `.loc[condition, 'col'] = value`       |        |

---

# 🧩 **Pandas Chapter 3 — Practice Sheet**

Put your skills into practice with these structured tasks 👇

---

### 🧠 **Level 1: Column & Row Selection**

**Q1.** Create a DataFrame of 6 employees with columns:
`['EmpID', 'Name', 'Department', 'Salary', 'City']`.

**Q2.** Display only the `Name` and `Department` columns.
**Q3.** Show the first 3 rows only.
**Q4.** Display data for the employee with `EmpID = 3`.

---

### ⚙️ **Level 2: Filtering Data**

**Q5.** Display employees with `Salary > 50,000`.
**Q6.** Display employees working in `Finance` **or** `IT`.
**Q7.** Display employees **not** in `Delhi`.
**Q8.** Display employees whose name starts with `'A'`.
**Q9.** Show employees with `Salary` between `40,000` and `70,000`.

---

### 🧮 **Level 3: Sorting & Conditional Logic**

**Q10.** Sort all employees by `Salary` (descending).
**Q11.** Sort by `Department` ascending and then `Salary` descending.
**Q12.** Add a column `Level`:

* If `Salary > 60,000` → `'Senior'`
* Else → `'Junior'`

**Q13.** Set `EmpID` as index, display the top 3 earners.

---

### 💡 **Level 4: Real-World Challenge**

Create a DataFrame:

```python
data = {
    'Product': ['TV', 'Laptop', 'Phone', 'Tablet', 'Speaker', 'Camera'],
    'Price': [50000, 75000, 30000, 25000, 10000, 45000],
    'Category': ['Electronics', 'Electronics', 'Mobile', 'Mobile', 'Audio', 'Electronics'],
    'Stock': [10, 5, 20, 15, 25, 8]
}
```

Then:

1. Display all products with price above 30,000.
2. Filter items in the `'Electronics'` category.
3. Sort by stock (descending).
4. Add a column `Discount` = 10% of price.
5. Show only products with final price (`Price - Discount`) above 40,000.

---

### 🧠 **Mini Challenge**

Read a CSV file (e.g., `sales.csv`) and:

* Filter rows where `Region == 'North'` and `Sales > 10000`.
* Sort by `Sales` descending.
* Add a column `TargetAchieved = 'Yes'` if `Sales > 15000`, else `'No'`.
* Export the filtered dataset to `north_sales.csv`.

---

# 🧹 **Pandas Chapter 4 – Data Cleaning & Transformation**

This chapter is all about **fixing messy, incomplete, or inconsistent data**, preparing it for meaningful analysis or visualization (in Power BI, Excel, or SQL).

---

## 🧠 **Concept Notes**

---

### 📘 **1. What is Data Cleaning?**

**Data cleaning** (or *data wrangling*) means detecting and correcting errors in datasets —
such as:

* Missing values
* Wrong data types
* Duplicates
* Inconsistent formats
* Extra spaces or symbols

In Pandas, you can clean and transform your dataset easily using built-in functions.

---

### 🧩 **2. Handling Missing Values (NaN)**

#### 🔹 Detect Missing Values

```python
df.isnull()           # Shows True for missing values
df.isnull().sum()     # Count missing per column
df.notnull()          # Opposite of isnull()
```

#### 🔹 Remove Missing Data

```python
df.dropna()           # Drops any row with NaN
df.dropna(axis=1)     # Drops entire columns with NaN
df.dropna(subset=['Age'])  # Drops rows where 'Age' is missing
```

#### 🔹 Fill Missing Data

```python
df.fillna(0)                             # Replace NaN with 0
df['City'].fillna('Unknown', inplace=True)
df['Salary'].fillna(df['Salary'].mean(), inplace=True)  # Replace with average
```

#### 🔹 Forward / Backward Fill

```python
df.fillna(method='ffill')   # Forward fill
df.fillna(method='bfill')   # Backward fill
```

---

### 🔢 **3. Handling Duplicates**

#### 🔹 Check for Duplicates

```python
df.duplicated()
df.duplicated().sum()       # Count duplicates
```

#### 🔹 Remove Duplicates

```python
df.drop_duplicates(inplace=True)
```

#### 🔹 Remove Duplicates by Specific Columns

```python
df.drop_duplicates(subset=['Name', 'City'], inplace=True)
```

---

### 🔤 **4. Working with String Data**

#### Access string functions using `.str`

```python
df['Name'].str.upper()          # Convert to uppercase
df['Name'].str.lower()          # Convert to lowercase
df['City'].str.strip()          # Remove extra spaces
df['Email'].str.contains('@')   # Check for substring
df['Name'].str.replace('Mr. ', '')   # Replace text
```

#### Combine string columns

```python
df['FullName'] = df['FirstName'] + ' ' + df['LastName']
```

---

### 📆 **5. Changing Data Types**

Check data types:

```python
df.dtypes
```

Convert column types:

```python
df['Age'] = df['Age'].astype(int)
df['JoinDate'] = pd.to_datetime(df['JoinDate'])
```

Convert numeric text:

```python
df['Salary'] = pd.to_numeric(df['Salary'], errors='coerce')
```

---

### 🧮 **6. Replacing Incorrect Values**

Replace specific values:

```python
df['City'].replace({'Del': 'Delhi', 'Mum': 'Mumbai'}, inplace=True)
```

Replace using condition:

```python
df.loc[df['Salary'] < 10000, 'Salary'] = 10000
```

---

### 🧱 **7. Renaming Columns**

```python
df.rename(columns={'Salary': 'AnnualSalary', 'City': 'Location'}, inplace=True)
```

---

### 🧰 **8. Removing Unnecessary Columns or Rows**

```python
df.drop(['Remarks', 'TempCol'], axis=1, inplace=True)
df.drop(index=[0, 1], inplace=True)     # Remove rows by index
```

---

### 🧩 **9. Standardizing Text Data**

Inconsistent capitalization or spacing can cause grouping errors.

```python
df['City'] = df['City'].str.strip().str.title()
df['Department'] = df['Department'].str.upper()
```

---

### 📊 **10. Outlier Treatment (Basic Concept)**

Detect values far from the average:

```python
Q1 = df['Salary'].quantile(0.25)
Q3 = df['Salary'].quantile(0.75)
IQR = Q3 - Q1
df_filtered = df[~((df['Salary'] < (Q1 - 1.5 * IQR)) | (df['Salary'] > (Q3 + 1.5 * IQR)))]
```

---

### 💾 **11. Save the Cleaned Data**

After all transformations:

```python
df.to_csv('cleaned_data.csv', index=False)
```

---

## 🧾 **Quick Summary**

| Task                 | Function                                         |
| -------------------- | ------------------------------------------------ |
| Detect missing       | `.isnull()`, `.notnull()`                        |
| Drop missing         | `.dropna()`                                      |
| Fill missing         | `.fillna()`                                      |
| Handle duplicates    | `.duplicated()`, `.drop_duplicates()`            |
| String cleaning      | `.str.upper()`, `.str.strip()`, `.str.replace()` |
| Data type conversion | `.astype()`, `pd.to_datetime()`                  |
| Rename columns       | `.rename()`                                      |
| Replace values       | `.replace()`                                     |
| Drop columns/rows    | `.drop()`                                        |
| Handle outliers      | Quantile + IQR method                            |

---

# 🧩 **Pandas Chapter 4 — Practice Sheet**

Now, let’s apply everything you’ve learned 👇

---

### 🧠 **Level 1: Missing Data**

**Q1.** Create a DataFrame:

```python
data = {
    'Name': ['Ayaan', 'Ravi', 'Neha', 'Pooja', None],
    'City': ['Lucknow', None, 'Delhi', 'Mumbai', 'Kolkata'],
    'Salary': [50000, 60000, None, 55000, 58000]
}
```

**Tasks:**

1. Find missing values in each column.
2. Fill missing `Salary` with the mean.
3. Fill missing `City` with `'Unknown'`.
4. Drop rows where `Name` is missing.

---

### ⚙️ **Level 2: Duplicates & Text Cleaning**

**Q5.** Add a duplicate row manually. Then:

* Detect and remove duplicates.

**Q6.** Clean `City` column by removing extra spaces and converting all to title case.

**Q7.** Convert all names to uppercase.

---

### 🧩 **Level 3: Data Transformation**

**Q8.** Convert the `Salary` column to integer type.
**Q9.** Rename column `City` → `Location`.
**Q10.** Replace all `'Unknown'` with `'Not Provided'`.
**Q11.** Add new column `Bonus` = 10% of `Salary`.

---

### 📊 **Level 4: Mini Real-World Project**

**Dataset:**

```python
sales = {
    'Product': ['TV', 'Phone', 'Laptop', 'TV', 'Tablet', 'TV', 'Phone'],
    'Price': ['50000', '25000', '70000', '50000', '25000', '50000', '25000'],
    'City': ['Delhi', 'Delhi', 'Mumbai', 'Mumbai', 'Delhi', None, 'Kolkata']
}
df = pd.DataFrame(sales)
```

**Tasks:**

1. Convert `Price` to numeric.
2. Fill missing `City` with `'Unknown'`.
3. Remove duplicate rows.
4. Standardize `City` names (capitalize properly).
5. Create a column `DiscountedPrice = Price * 0.9`.
6. Save cleaned dataset as `sales_clean.csv`.

---

### 💡 **Bonus Challenge**

Download any **real dataset (CSV)** — e.g., from Kaggle — and:

* Identify missing and duplicate values.
* Clean strings, rename columns, and fix data types.
* Save the cleaned version.

---

✅ **Next Step Recommendation:**
Now that you can clean and transform data effectively, the next essential step is:

📘 **Chapter 5 – Aggregation & Grouping**

Here, you’ll learn how to:

* Use `groupby()` like SQL `GROUP BY`
* Perform aggregations (`sum`, `mean`, `count`)
* Create pivot tables
* Derive summaries used in dashboards and reports

---
---

# 🧾 **Pandas Chapter 5 — Aggregation & Grouping**

---

## 🧠 **Concept Notes**

---

### 📘 **1. What is Aggregation?**

Aggregation means **summarizing data** — turning multiple rows into single values based on groups or categories.

Example:

| Department | Employee | Salary |
| ---------- | -------- | ------ |
| HR         | Ayaan    | 50000  |
| HR         | Neha     | 55000  |
| IT         | Ravi     | 60000  |

➡ You can aggregate to find:

| Department | Avg_Salary |
| ---------- | ---------- |
| HR         | 52500      |
| IT         | 60000      |

---

### 🔹 **2. Using `.groupby()`**

The **`groupby()`** function is used to group rows that share a common value and then perform aggregation functions.

#### Syntax:

```python
df.groupby('column_name')
```

#### Example:

```python
df.groupby('Department')['Salary'].mean()
```

This groups employees by `Department` and returns the **average salary** per department.

---

### 🔹 **3. Applying Multiple Aggregations**

You can perform multiple operations simultaneously:

```python
df.groupby('Department')['Salary'].agg(['mean', 'sum', 'max', 'min', 'count'])
```

Output:

| Department | mean  | sum    | max   | min   | count |
| ---------- | ----- | ------ | ----- | ----- | ----- |
| HR         | 52500 | 105000 | 55000 | 50000 | 2     |
| IT         | 60000 | 60000  | 60000 | 60000 | 1     |

---

### 🔹 **4. Grouping by Multiple Columns**

You can group using more than one column:

```python
df.groupby(['Department', 'City'])['Salary'].mean()
```

This gives the average salary for each **department–city** combination.

---

### 🔹 **5. Resetting the Grouped Index**

By default, `groupby()` creates a hierarchical index (MultiIndex).
You can convert it back to a normal DataFrame:

```python
df.groupby('Department')['Salary'].mean().reset_index()
```

---

### 🔹 **6. Sorting Grouped Results**

Sort grouped data by aggregated value:

```python
df.groupby('Department')['Salary'].mean().sort_values(ascending=False)
```

---

### 🔹 **7. Named Aggregations (Cleaner Syntax)**

You can assign custom names to each aggregation:

```python
df.groupby('Department').agg(
    Avg_Salary=('Salary', 'mean'),
    Total_Salary=('Salary', 'sum'),
    Employee_Count=('Name', 'count')
).reset_index()
```

---

### 📊 **8. Pivot Tables**

Pivot tables are like an **Excel summary table** that shows aggregated data for combinations of rows and columns.

#### Syntax:

```python
pd.pivot_table(df, index='Department', values='Salary', aggfunc='mean')
```

#### Example:

```python
pd.pivot_table(df, index='Department', columns='City', values='Salary', aggfunc='sum', fill_value=0)
```

Output (example):

| City / Dept | Delhi | Mumbai | Lucknow |
| ----------- | ----- | ------ | ------- |
| HR          | 55000 | 0      | 50000   |
| IT          | 0     | 60000  | 0       |

---

### 📈 **9. Aggregation with Conditions (Filtering After Grouping)**

Example — departments with average salary > 55000:

```python
avg_salary = df.groupby('Department')['Salary'].mean().reset_index()
avg_salary[avg_salary['Salary'] > 55000]
```

---

### 🔁 **10. Custom Functions with `.apply()`**

You can define your own aggregation logic:

```python
def salary_range(x):
    return x.max() - x.min()

df.groupby('Department')['Salary'].apply(salary_range)
```

---

### 💡 **11. Real-World Use Cases**

You’ll use grouping and aggregation in:

* Sales or revenue reporting by region, product, or time
* Employee analytics by department or location
* Power BI / Excel dashboards with summarized metrics

---

## 🧾 **Quick Summary**

| Concept                   | Method / Function                         |
| ------------------------- | ----------------------------------------- |
| Grouping                  | `.groupby()`                              |
| Aggregation               | `.agg()`, `.mean()`, `.sum()`, `.count()` |
| Multiple Aggregations     | `.agg(['mean', 'sum', ...])`              |
| Group by Multiple Columns | `.groupby(['col1', 'col2'])`              |
| Reset grouped index       | `.reset_index()`                          |
| Pivot Tables              | `pd.pivot_table()`                        |
| Custom aggregation        | `.apply(function)`                        |

---

# 🧩 **Pandas Chapter 5 — Practice Sheet**

Let’s get hands-on 👇

---

### 🧠 **Level 1: Basic Grouping**

**Q1.** Create a DataFrame:

```python
data = {
    'Department': ['HR', 'HR', 'IT', 'IT', 'Finance', 'Finance'],
    'Employee': ['Ayaan', 'Neha', 'Ravi', 'Pooja', 'Arun', 'Meena'],
    'Salary': [50000, 55000, 60000, 62000, 70000, 72000],
    'City': ['Lucknow', 'Delhi', 'Delhi', 'Mumbai', 'Delhi', 'Mumbai']
}
df = pd.DataFrame(data)
```

**Tasks:**

1. Find the **average salary per department**.
2. Find the **total salary per city**.
3. Count the **number of employees per department**.

---

### ⚙️ **Level 2: Multiple Aggregations**

**Q4.** Find for each department:

* Average salary
* Maximum salary
* Total salary

**Q5.** Group by both **Department and City**, and show the **mean Salary**.

**Q6.** Sort the result from Q4 by average salary (descending).

---

### 🧩 **Level 3: Pivot Tables**

**Q7.** Create a pivot table showing the **sum of salaries** for each department by city.

**Q8.** Modify it to show **average salary** instead of sum.

**Q9.** Replace missing values in pivot table with `0` using `fill_value=0`.

---

### 📈 **Level 4: Custom Aggregation**

**Q10.** Write a custom function to find the **salary range (max - min)** per department.

**Q11.** Using `.agg()`, compute for each department:

* Mean Salary → `Avg_Salary`
* Employee Count → `Total_Employees`

**Q12.** Display only departments where the average salary > 60000.

---

### 💡 **Mini Project: Sales Summary**

Create a DataFrame:

```python
sales = {
    'Region': ['North', 'South', 'East', 'West', 'North', 'South', 'West', 'East'],
    'Product': ['TV', 'Laptop', 'TV', 'Phone', 'Phone', 'Laptop', 'Laptop', 'TV'],
    'Sales': [25000, 40000, 15000, 30000, 35000, 45000, 20000, 27000]
}
df = pd.DataFrame(sales)
```

**Tasks:**

1. Find total sales per region.
2. Find average sales per product.
3. Create a pivot table for region vs product showing total sales.
4. Identify which region has the highest total sales.
5. Save the summary as `sales_summary.csv`.

---

✅ **Next Step Recommendation:**

Now that you can summarize and aggregate, it’s time for **Chapter 6 – Merging, Joining, and Concatenating Data**
→ You’ll learn how to combine multiple datasets (like SQL joins), an *essential step* before analytics or Power BI integration.

---

# 🧾 **Pandas Chapter 6 — Merging, Joining, and Concatenation**

---

## 🧠 **Concept Notes**

Data rarely comes in one perfect table — you often have to combine **multiple sources** (like sales + customer + region tables).
Pandas provides **powerful merging and joining tools**, similar to **SQL JOINs** and **Excel VLOOKUPs**.

---

### 📘 **1. What is Data Merging?**

Merging means **combining two or more DataFrames** based on a common column (called a *key*).

---

### 🔹 **2. Using `pd.merge()` (Similar to SQL JOIN)**

#### Basic Syntax:

```python
pd.merge(left, right, on='key')
```

#### Example:

```python
import pandas as pd

employees = pd.DataFrame({
    'EmpID': [1, 2, 3, 4],
    'Name': ['Ayaan', 'Ravi', 'Neha', 'Pooja'],
    'DeptID': [101, 102, 101, 103]
})

departments = pd.DataFrame({
    'DeptID': [101, 102, 103],
    'Department': ['HR', 'Finance', 'IT']
})

merged = pd.merge(employees, departments, on='DeptID')
print(merged)
```

**Output:**

| EmpID | Name  | DeptID | Department |
| ----- | ----- | ------ | ---------- |
| 1     | Ayaan | 101    | HR         |
| 2     | Ravi  | 102    | Finance    |
| 3     | Neha  | 101    | HR         |
| 4     | Pooja | 103    | IT         |

---

### 🔸 **3. Types of Joins in Pandas**

Just like SQL, Pandas supports **4 main types of joins**:

| Join Type | Description                                             | Example      |
| --------- | ------------------------------------------------------- | ------------ |
| `inner`   | Returns matching rows only                              | Default type |
| `left`    | All rows from left DataFrame, matching from right       |              |
| `right`   | All rows from right DataFrame, matching from left       |              |
| `outer`   | All rows from both DataFrames (fills NaN where missing) |              |

#### Example:

```python
pd.merge(employees, departments, on='DeptID', how='left')
```

---

### 🧩 **4. Merging on Different Column Names**

When the key columns have **different names**, use:

```python
pd.merge(left, right, left_on='Emp_ID', right_on='Employee_ID')
```

---

### 📊 **5. Merging on Multiple Columns**

You can join using multiple keys:

```python
pd.merge(df1, df2, on=['City', 'Year'])
```

---

### ⚙️ **6. Handling Overlapping Column Names**

If both DataFrames have columns with the same name (other than the join key), Pandas automatically adds suffixes:

```python
pd.merge(df1, df2, on='EmpID', suffixes=('_left', '_right'))
```

---

### 🔗 **7. Joining DataFrames using `.join()`**

`DataFrame.join()` is a simpler method for joining on **index** (row labels).

Example:

```python
df1.join(df2, lsuffix='_x', rsuffix='_y')
```

It assumes you’re joining by index — use `set_index()` if needed.

---

### 🔢 **8. Concatenating DataFrames (Stacking)**

If you just want to **stack datasets**, use `pd.concat()`.

#### Vertically (Add rows):

```python
pd.concat([df1, df2])
```

#### Horizontally (Add columns):

```python
pd.concat([df1, df2], axis=1)
```

#### Reset index after concatenation:

```python
pd.concat([df1, df2], ignore_index=True)
```

---

### 📈 **9. Appending DataFrames**

`append()` is similar to vertical concat (but now deprecated):

```python
df1.append(df2, ignore_index=True)
```

Use `pd.concat()` instead for modern syntax.

---

### 🔁 **10. Practical Example:**

```python
sales_q1 = pd.DataFrame({
    'Month': ['Jan', 'Feb', 'Mar'],
    'Revenue': [25000, 30000, 28000]
})

sales_q2 = pd.DataFrame({
    'Month': ['Apr', 'May', 'Jun'],
    'Revenue': [32000, 35000, 33000]
})

sales = pd.concat([sales_q1, sales_q2], ignore_index=True)
```

---

### 💡 **11. Real-World Use Cases**

* Merge **employee** and **department** data (via IDs)
* Combine **sales** and **region** tables
* Append monthly or quarterly reports into one dataset
* Build unified datasets for Power BI dashboards

---

## 🧾 **Quick Summary**

| Task                    | Function                          |
| ----------------------- | --------------------------------- |
| Inner Join              | `pd.merge(df1, df2, on='key')`    |
| Left Join               | `pd.merge(df1, df2, how='left')`  |
| Right Join              | `pd.merge(df1, df2, how='right')` |
| Outer Join              | `pd.merge(df1, df2, how='outer')` |
| Join on Index           | `df1.join(df2)`                   |
| Concatenate Rows        | `pd.concat([df1, df2])`           |
| Concatenate Columns     | `pd.concat([df1, df2], axis=1)`   |
| Merge on Different Keys | `left_on`, `right_on`             |
| Handle Duplicates       | `suffixes=('_x', '_y')`           |

---

# 🧩 **Pandas Chapter 6 — Practice Sheet**

Let’s get your hands dirty 👇

---

### 🧠 **Level 1: Basic Merge**

**Q1.** Create DataFrames:

```python
employees = pd.DataFrame({
    'EmpID': [1, 2, 3, 4],
    'Name': ['Ayaan', 'Ravi', 'Neha', 'Pooja'],
    'DeptID': [101, 102, 101, 103]
})

departments = pd.DataFrame({
    'DeptID': [101, 102, 103, 104],
    'Department': ['HR', 'Finance', 'IT', 'Admin']
})
```

**Tasks:**

1. Perform an **inner join** on `DeptID`.
2. Perform a **left join**.
3. Perform a **right join**.
4. Perform a **full outer join**.

---

### ⚙️ **Level 2: Merging on Different Keys**

**Q5.** Create DataFrames:

```python
sales = pd.DataFrame({
    'ProductID': [1, 2, 3],
    'ProductName': ['TV', 'Phone', 'Laptop']
})

orders = pd.DataFrame({
    'PID': [1, 3, 4],
    'OrderQty': [5, 2, 1]
})
```

Merge using:

```python
pd.merge(sales, orders, left_on='ProductID', right_on='PID', how='outer')
```

Then drop redundant column `PID`.

---

### 🧩 **Level 3: Multiple Keys and Suffixes**

**Q6.** Create two DataFrames:

```python
data1 = pd.DataFrame({'City': ['Delhi', 'Mumbai'], 'Year': [2022, 2023], 'Sales': [100, 200]})
data2 = pd.DataFrame({'City': ['Delhi', 'Mumbai'], 'Year': [2022, 2023], 'Profit': [30, 40]})
```

Join on both columns `City` and `Year`.

---

### 🧮 **Level 4: Concatenation**

**Q7.** Combine quarterly sales reports:

```python
q1 = pd.DataFrame({'Month': ['Jan', 'Feb', 'Mar'], 'Revenue': [200, 220, 250]})
q2 = pd.DataFrame({'Month': ['Apr', 'May', 'Jun'], 'Revenue': [300, 320, 350]})
```

Use `pd.concat()` to stack vertically, reset index.

**Q8.** Concatenate horizontally two DataFrames:

```python
pd.concat([q1, q2], axis=1)
```

---

### 💡 **Level 5: Mini Real-World Challenge**

Create 3 DataFrames:

```python
customers = pd.DataFrame({
    'CustID': [1, 2, 3],
    'Name': ['Ayaan', 'Neha', 'Ravi']
})

orders = pd.DataFrame({
    'OrderID': [101, 102, 103],
    'CustID': [1, 2, 2],
    'Amount': [5000, 7000, 3000]
})

regions = pd.DataFrame({
    'CustID': [1, 2, 3],
    'Region': ['North', 'South', 'East']
})
```

**Tasks:**

1. Merge customers with orders (on CustID).
2. Merge the result with regions.
3. Calculate **total amount per region**.
4. Export final summary as `regional_sales.csv`.

---

✅ **Next Step Recommendation:**
You’re now equipped to merge and prepare complex datasets.
Next, we’ll move to:

📘 **Chapter 7 – Working with Dates & Time**
You’ll learn to:

* Parse and manipulate dates
* Extract year, month, day
* Filter data by date range
* Resample and aggregate by time (e.g., monthly sales)

---


# 🕒 **Pandas Chapter 7 — Working with Dates & Time**

---

## 🧠 **Concept Notes**

---

### 📘 **1. What is Datetime in Pandas?**

The **datetime module** in Pandas helps you **analyze and manipulate date/time data** efficiently.

Pandas automatically converts recognized date formats (e.g., `2024-11-15`, `15/11/2024`, etc.) into **`datetime64`** objects that support:

* Filtering by date
* Extracting year, month, day, weekday
* Resampling by month or week
* Calculating time differences

---

### 🧩 **2. Creating Datetime Columns**

#### From strings:

```python
import pandas as pd

df = pd.DataFrame({
    'Date': ['2024-01-05', '2024-01-10', '2024-02-15']
})
df['Date'] = pd.to_datetime(df['Date'])
print(df.dtypes)
```

**Output:**

```
Date    datetime64[ns]
dtype: object
```

---

### 🔹 **3. Extracting Components of Date**

Once converted to datetime, you can easily extract:

```python
df['Year'] = df['Date'].dt.year
df['Month'] = df['Date'].dt.month
df['Day'] = df['Date'].dt.day
df['Weekday'] = df['Date'].dt.day_name()
df['MonthName'] = df['Date'].dt.month_name()
```

---

### 🧮 **4. Filtering by Date Range**

#### Filter for a specific date:

```python
df[df['Date'] == '2024-01-10']
```

#### Filter by range:

```python
df[(df['Date'] >= '2024-01-01') & (df['Date'] <= '2024-01-31')]
```

#### Using `.between()`:

```python
df[df['Date'].between('2024-01-01', '2024-01-31')]
```

---

### 📆 **5. Sorting by Date**

```python
df.sort_values(by='Date', inplace=True)
```

---

### ⏱ **6. Time Differences and Durations**

You can calculate the time gap between two dates:

```python
df['NextDate'] = pd.to_datetime(['2024-01-06', '2024-01-15', '2024-02-20'])
df['DaysDiff'] = (df['NextDate'] - df['Date']).dt.days
```

Output:

| Date       | NextDate   | DaysDiff |
| ---------- | ---------- | -------- |
| 2024-01-05 | 2024-01-06 | 1        |
| 2024-01-10 | 2024-01-15 | 5        |
| 2024-02-15 | 2024-02-20 | 5        |

---

### 🧩 **7. Generating Date Ranges**

You can easily create date sequences:

```python
pd.date_range(start='2024-01-01', end='2024-01-10')
```

Or specify the frequency:

```python
pd.date_range(start='2024-01-01', periods=5, freq='D')   # Daily
pd.date_range(start='2024-01-01', periods=5, freq='M')   # Monthly
pd.date_range(start='2024-01-01', periods=5, freq='W')   # Weekly
```

---

### 🧭 **8. Setting Datetime as Index**

Setting the date column as index helps in **time series analysis**.

```python
df.set_index('Date', inplace=True)
```

Now you can use:

```python
df['2024-01']    # Select all rows in January 2024
df.loc['2024-01-05':'2024-01-10']
```

---

### 📈 **9. Resampling (Aggregating Over Time Periods)**

**Resampling** helps you aggregate data over a time frequency — e.g., daily → monthly.

#### Example:

```python
sales = pd.DataFrame({
    'Date': pd.date_range('2024-01-01', periods=10, freq='D'),
    'Sales': [100, 150, 200, 180, 160, 170, 300, 400, 250, 320]
})
sales.set_index('Date', inplace=True)
sales.resample('W').sum()     # Weekly total sales
sales.resample('M').mean()    # Monthly average
```

Common resample frequencies:

| Code | Period    | Example   |
| ---- | --------- | --------- |
| D    | Day       | Daily     |
| W    | Week      | Weekly    |
| M    | Month End | Monthly   |
| Q    | Quarter   | Quarterly |
| Y    | Year End  | Yearly    |

---

### 🧮 **10. Time Shifting**

Shift values forward or backward in time:

```python
sales['PrevSales'] = sales['Sales'].shift(1)
sales['Diff'] = sales['Sales'] - sales['PrevSales']
```

---

### 💡 **11. Converting Strings with Custom Formats**

If your date format is non-standard (e.g., `15-11-2024`):

```python
pd.to_datetime(df['Date'], format='%d-%m-%Y')
```

---

### 🧠 **12. Common Real-Life Use Cases**

✅ Monthly sales reporting
✅ Calculating time between purchases
✅ Building trend charts over time
✅ Time-based KPIs in Power BI / dashboards

---

## 🧾 **Quick Summary**

| Task                   | Function                            |
| ---------------------- | ----------------------------------- |
| Convert to datetime    | `pd.to_datetime()`                  |
| Extract year/month/day | `.dt.year`, `.dt.month`, `.dt.day`  |
| Filter by date         | `df[df['Date'] > 'YYYY-MM-DD']`     |
| Create date range      | `pd.date_range()`                   |
| Resample               | `.resample('M').sum()`              |
| Time difference        | `(df['End'] - df['Start']).dt.days` |
| Set date as index      | `.set_index('Date')`                |
| Shift values           | `.shift()`                          |

---

# 🧩 **Pandas Chapter 7 — Practice Sheet**

Let’s put this into action 👇

---

### 🧠 **Level 1: Basic Datetime Operations**

**Q1.** Create a DataFrame:

```python
data = {'Date': ['2024-01-05', '2024-01-10', '2024-02-15', '2024-02-25'],
        'Sales': [200, 250, 300, 280]}
df = pd.DataFrame(data)
```

**Tasks:**

1. Convert `Date` to datetime.
2. Extract `Year`, `Month`, `Day`, and `Weekday`.
3. Sort by `Date`.

---

### ⚙️ **Level 2: Filtering by Date**

**Q4.** Display sales only from **February 2024**.
**Q5.** Display records where date is between `2024-01-05` and `2024-02-15`.
**Q6.** Add a column `NextDay` = `Date + 1 day`.

---

### 🧩 **Level 3: Resampling**

**Q7.** Set `Date` as index and resample by **month** to find total monthly sales.
**Q8.** Calculate the **average weekly sales** using `.resample('W').mean()`.

---

### 📈 **Level 4: Time Difference & Shifting**

**Q9.** Add a column `PrevSales` = previous day’s sales (using `.shift()`).
**Q10.** Create a column `Change` = `Sales - PrevSales`.

---

### 💡 **Mini Project: Monthly Revenue Tracker**

Create:

```python
df = pd.DataFrame({
    'Date': pd.date_range(start='2024-01-01', periods=12, freq='M'),
    'Revenue': [25000, 27000, 30000, 32000, 31000, 33000, 35000, 37000, 36000, 40000, 42000, 45000]
})
```

**Tasks:**

1. Calculate month-over-month revenue change.
2. Find total revenue in Q1, Q2, Q3, Q4 (use `.resample('Q').sum()`).
3. Identify months where revenue increased compared to previous month.
4. Plot a simple revenue trend using `.plot(kind='line')`.

---

✅ **Next Step Recommendation:**

You’ve now mastered **time-based data handling**, a must-have for real-world analysis.
Up next —

📘 **Chapter 8 – Data Visualization with Pandas**
You’ll learn to create **charts, plots, and trends directly in Pandas** (before moving to tools like Power BI or Matplotlib).

---


# 🧾 **Pandas Chapter 8 — Data Visualization with Pandas**

---

## 🧠 **Concept Notes**

---

### 📘 **1. Why Visualize Data?**

Data visualization helps you:

* Identify **patterns and trends** quickly
* Spot **outliers or anomalies**
* Communicate insights effectively in dashboards or reports

Pandas integrates directly with **Matplotlib**, letting you visualize your DataFrame with **one line of code**.

---

### ⚙️ **2. Enabling Visualization**

Before plotting, make sure Matplotlib is installed:

```bash
pip install matplotlib
```

Then import it:

```python
import pandas as pd
import matplotlib.pyplot as plt
```

Most Pandas visualizations use:

```python
df.plot(kind='...')
plt.show()
```

---

### 📊 **3. Line Plot**

Used to visualize **trends over time** (e.g., sales, revenue, stock price).

```python
df = pd.DataFrame({
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
    'Revenue': [20000, 22000, 25000, 27000, 30000]
})

df.plot(x='Month', y='Revenue', kind='line', title='Monthly Revenue', marker='o')
plt.xlabel('Month')
plt.ylabel('Revenue')
plt.show()
```

---

### 📈 **4. Bar Chart**

Shows comparisons between categories.

#### Vertical Bar:

```python
df.plot(x='Month', y='Revenue', kind='bar', color='skyblue')
```

#### Horizontal Bar:

```python
df.plot(x='Month', y='Revenue', kind='barh', color='lightgreen')
```

---

### 🧱 **5. Multiple Columns in One Chart**

You can visualize multiple columns together:

```python
df = pd.DataFrame({
    'Month': ['Jan', 'Feb', 'Mar', 'Apr'],
    'Sales_A': [200, 220, 250, 270],
    'Sales_B': [180, 200, 230, 260]
})
df.plot(x='Month', kind='line', marker='o', title='Product Sales Comparison')
```

---

### 🧩 **6. Pie Chart**

Used to show **proportion or percentage share**.

```python
data = {'Product': ['TV', 'Phone', 'Laptop'], 'Sales': [30000, 50000, 40000]}
df = pd.DataFrame(data)

df.plot.pie(y='Sales', labels=df['Product'], autopct='%1.1f%%', figsize=(6,6))
plt.title('Sales Share by Product')
plt.ylabel('')
plt.show()
```

---

### 📉 **7. Scatter Plot**

Used for **correlation analysis** between two variables.

```python
df = pd.DataFrame({
    'Advertising': [10, 20, 30, 40, 50],
    'Sales': [15, 25, 35, 50, 60]
})

df.plot(kind='scatter', x='Advertising', y='Sales', color='orange', title='Advertising vs Sales')
```

---

### 📊 **8. Histogram**

Used to understand **data distribution** (like salary, age, or scores).

```python
df = pd.DataFrame({'Age': [22, 25, 28, 22, 30, 26, 24, 29, 27, 25]})
df['Age'].plot(kind='hist', bins=5, color='purple', rwidth=0.9, title='Age Distribution')
```

---

### 📈 **9. Box Plot**

Helps visualize **spread, median, and outliers** in numerical data.

```python
df = pd.DataFrame({'Salary': [30000, 35000, 40000, 45000, 60000, 80000, 90000]})
df.boxplot(column='Salary')
plt.title('Salary Distribution')
plt.show()
```

---

### 📅 **10. Time-Series Plot**

Visualize trends over time (common in analytics dashboards).

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.DataFrame({
    'Date': pd.date_range(start='2024-01-01', periods=6, freq='M'),
    'Revenue': [25000, 27000, 30000, 33000, 35000, 40000]
})
df.set_index('Date', inplace=True)
df.plot(kind='line', title='Monthly Revenue Trend', marker='o')
plt.ylabel('Revenue')
plt.show()
```

---

### 🧠 **11. Styling & Customization**

You can add styles to make charts look better:

```python
plt.style.use('seaborn-v0_8')

df.plot(kind='bar', color=['#00B4D8', '#48CAE4'])
plt.title('Sales Comparison')
plt.xlabel('Month')
plt.ylabel('Revenue ($)')
plt.grid(True)
plt.show()
```

---

### 💡 **12. Saving Your Charts**

Save plots for reports:

```python
plt.savefig('sales_trend.png', dpi=300, bbox_inches='tight')
```

---

### 🧮 **13. Real-World Use Cases**

✅ Trend charts for sales/revenue analysis
✅ Product or regional comparison
✅ Correlation between marketing spend and output
✅ Age/salary distribution plots for HR analytics

---

## 🧾 **Quick Summary**

| Chart Type  | Function                    | Use Case            |
| ----------- | --------------------------- | ------------------- |
| Line        | `kind='line'`               | Trends over time    |
| Bar         | `kind='bar'`                | Category comparison |
| Pie         | `.plot.pie()`               | Percentage share    |
| Scatter     | `kind='scatter'`            | Correlation         |
| Histogram   | `kind='hist'`               | Data distribution   |
| Box         | `.boxplot()`                | Spread & outliers   |
| Time Series | `.plot()` on datetime index | Temporal trends     |

---

# 🧩 **Pandas Chapter 8 — Practice Sheet**

---

### 🧠 **Level 1: Basic Plots**

**Q1.** Create:

```python
data = {'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
        'Sales': [220, 260, 280, 300, 350]}
df = pd.DataFrame(data)
```

Tasks:

1. Create a **line plot** showing monthly sales.
2. Add title and axis labels.
3. Save the plot as `monthly_sales.png`.

---

### ⚙️ **Level 2: Category Comparison**

**Q4.** Create a DataFrame:

```python
data = {'Product': ['TV', 'Laptop', 'Phone', 'Tablet'],
        'Revenue': [50000, 75000, 40000, 30000]}
```

Tasks:

1. Create a **bar chart** showing product revenue.
2. Create a **pie chart** of the same data.
3. Add labels and percentages to the pie chart.

---

### 🧩 **Level 3: Multi-Series Plot**

**Q7.** Create:

```python
data = {'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
        'Sales_A': [100, 120, 150, 170, 190],
        'Sales_B': [90, 110, 140, 160, 180]}
```

Tasks:

1. Plot both series on one line chart.
2. Add gridlines and a legend.
3. Use a seaborn style.

---

### 📈 **Level 4: Distribution & Correlation**

**Q10.** Create:

```python
data = {'Age': [22, 24, 25, 27, 28, 30, 32, 35, 40],
        'Salary': [25000, 28000, 30000, 35000, 36000, 40000, 45000, 48000, 50000]}
```

Tasks:

1. Create a **scatter plot** (Age vs Salary).
2. Create a **histogram** of Age.
3. Create a **box plot** of Salary.

---

### 💡 **Mini Project: Sales Dashboard**

**Dataset:**

```python
df = pd.DataFrame({
    'Month': pd.date_range('2024-01-01', periods=6, freq='M'),
    'Revenue': [22000, 25000, 27000, 29000, 31000, 35000],
    'Profit': [5000, 6000, 7000, 8000, 8500, 9500]
})
```

**Tasks:**

1. Plot a **dual line chart** (Revenue & Profit vs Month).
2. Create a **bar chart** for monthly revenue.
3. Add styling (title, colors, legend).
4. Save all plots to PNG files for a mini dashboard.

---

✅ **Next Step Recommendation:**
Now that you can visualize directly with Pandas, the next chapter takes it a step further —
📘 **Chapter 9 – Advanced Pandas Operations**
You’ll learn:

* `apply()`, `map()`, and `lambda` functions
* Vectorized transformations
* Categorization with `pd.cut()`
* Multi-index operations for complex data

---


# 🧾 **Pandas Chapter 9 — Advanced Pandas Operations**

---

## 🧠 **Concept Notes**

---

### 📘 **1. Why Advanced Pandas?**

Advanced Pandas helps you:

* Write **cleaner, faster code**
* Apply **custom logic efficiently**
* Perform **complex column-wise transformations**
* Handle **multi-level data** and **categorization**

These tools elevate you from just analyzing data to **engineering insights** 💡

---

## ⚙️ **2. Using `apply()`, `map()`, and `applymap()`**

These are essential functions for **applying custom logic** to data.

---

### 🔹 **`map()`**

Used only for **Series** (single column).

```python
df['Marks'] = [45, 67, 89, 72, 50]
df['Result'] = df['Marks'].map(lambda x: 'Pass' if x >= 60 else 'Fail')
```

**Result:**

| Marks | Result |
| ----- | ------ |
| 45    | Fail   |
| 67    | Pass   |
| 89    | Pass   |
| 72    | Pass   |
| 50    | Fail   |

---

### 🔸 **`apply()`**

Used for **DataFrame or Series** — applies a function **column-wise or row-wise**.

#### On Series:

```python
df['Marks'].apply(lambda x: x + 5)
```

#### On DataFrame (row-wise):

```python
df['Total'] = df.apply(lambda row: row['Math'] + row['Science'], axis=1)
```

(`axis=1` → apply function row by row)

---

### 🔹 **`applymap()`**

Used for **element-wise operations** on entire DataFrame.

```python
df = pd.DataFrame({'A': [1, 2], 'B': [3, 4]})
df.applymap(lambda x: x * 10)
```

Output:

| A  | B  |
| -- | -- |
| 10 | 30 |
| 20 | 40 |

---

### 💡 **When to Use What**

| Function     | Works On           | Scope        | Use Case                          |
| ------------ | ------------------ | ------------ | --------------------------------- |
| `map()`      | Series             | Element-wise | Column-wise transformations       |
| `apply()`    | Series / DataFrame | Row/column   | Custom logic (row sum, condition) |
| `applymap()` | DataFrame          | Element-wise | Apply function to all cells       |

---

## 🧩 **3. Vectorized Operations**

Instead of loops, Pandas uses **vectorization** (like NumPy) — faster and cleaner.

```python
df['DiscountedPrice'] = df['Price'] * 0.9
```

This applies to every row — **no loop required** ✅

---

## 🧱 **4. Conditional Updates with `np.where()`**

`np.where()` is a fast, vectorized way to assign conditional values.

```python
import numpy as np
df['Status'] = np.where(df['Sales'] >= 50000, 'High', 'Low')
```

---

## 🧮 **5. Binning & Categorization (`pd.cut` and `pd.qcut`)**

These functions help you **group continuous data** into ranges or percentiles.

#### Using `pd.cut()` → Manual bins

```python
df['AgeGroup'] = pd.cut(df['Age'], bins=[0, 18, 35, 60, 100],
                        labels=['Child', 'Youth', 'Adult', 'Senior'])
```

#### Using `pd.qcut()` → Quantile-based bins

```python
df['SalaryLevel'] = pd.qcut(df['Salary'], q=4, labels=['Low', 'Mid', 'High', 'Very High'])
```

---

## 🔁 **6. MultiIndex (Hierarchical Indexing)**

Used for **grouped data with multiple levels**.

#### Example:

```python
arrays = [
    ['HR', 'HR', 'IT', 'IT'],
    ['Ayaan', 'Neha', 'Ravi', 'Pooja']
]
index = pd.MultiIndex.from_arrays(arrays, names=('Department', 'Employee'))
df = pd.DataFrame({'Salary': [50000, 52000, 60000, 62000]}, index=index)
```

Now you can:

```python
df.loc['HR']          # Select all HR employees
df.loc[('HR', 'Ayaan')]
```

---

## 📊 **7. Group Aggregation with `apply()`**

You can apply custom logic after grouping.

```python
df.groupby('Department')['Salary'].apply(lambda x: x.max() - x.min())
```

→ Salary range per department.

---

## 🧮 **8. Ranking Data**

Assign ranks to data:

```python
df['Rank'] = df['Sales'].rank(ascending=False)
```

---

## 🧰 **9. Cumulative Functions**

Track running totals or percentages:

```python
df['Cumulative_Sales'] = df['Sales'].cumsum()
df['Cumulative_Percent'] = df['Sales'].cumsum() / df['Sales'].sum() * 100
```

---

## 📈 **10. Advanced Aggregations with `agg()` and Dictionaries**

You can apply **different aggregations per column**:

```python
df.agg({
    'Salary': ['mean', 'max'],
    'Experience': 'sum'
})
```

---

## 💡 **11. Practical Real-World Use Cases**

✅ Categorizing customers by age or spend range
✅ Ranking top-performing sales regions
✅ Applying business logic across multiple columns
✅ Creating summary metrics (e.g., salary range, revenue gap)
✅ Building grouped KPIs for dashboards

---

## 🧾 **Quick Summary**

| Concept            | Function                            | Purpose                   |
| ------------------ | ----------------------------------- | ------------------------- |
| Custom Logic       | `.apply()`, `.map()`, `.applymap()` | Transform data            |
| Conditional Update | `np.where()`                        | Assign based on condition |
| Categorization     | `pd.cut()`, `pd.qcut()`             | Group continuous data     |
| Vectorization      | `df['col'] * 2`                     | Fast column operations    |
| Ranking            | `.rank()`                           | Assign order              |
| Cumulative         | `.cumsum()`                         | Running total             |
| MultiIndex         | `pd.MultiIndex`                     | Hierarchical data         |
| Aggregation        | `.agg()`                            | Multi-column summary      |

---

# 🧩 **Pandas Chapter 9 — Practice Sheet**

Let’s get hands-on 👇

---

### 🧠 **Level 1: Apply, Map, Applymap**

**Q1.** Create a DataFrame:

```python
data = {'Name': ['Ayaan', 'Ravi', 'Neha', 'Pooja'],
        'Marks': [85, 62, 47, 91]}
df = pd.DataFrame(data)
```

**Tasks:**

1. Use `map()` to classify students as **Pass/Fail** (`>= 60`).
2. Use `apply()` to add 5 grace marks to all students.
3. Apply a function to capitalize all names using `.applymap()`.

---

### ⚙️ **Level 2: Conditional Updates**

**Q4.** Create:

```python
data = {'Sales': [20000, 35000, 45000, 55000, 70000]}
```

1. Create a new column `Status` = “High” if Sales > 50000, else “Low” (using `np.where()`).
2. Add a column `Bonus` = 5% of Sales if “High”, else 2%.

---

### 🧩 **Level 3: Binning and Categorization**

**Q6.** Create a DataFrame:

```python
data = {'Age': [15, 23, 35, 46, 62, 80]}
```

Use `pd.cut()` to classify ages as:

* 0–18: Child
* 19–35: Youth
* 36–60: Adult
* 61–100: Senior

---

### 🧱 **Level 4: MultiIndex & Aggregation**

**Q9.** Create:

```python
data = {
    'Department': ['HR', 'HR', 'IT', 'IT', 'Finance', 'Finance'],
    'Employee': ['Ayaan', 'Neha', 'Ravi', 'Pooja', 'Arun', 'Meena'],
    'Salary': [50000, 52000, 60000, 62000, 70000, 72000]
}
df = pd.DataFrame(data)
```

**Tasks:**

1. Set MultiIndex with `Department` & `Employee`.
2. Get salary for `'HR'` department only.
3. Find salary range per department using `groupby().apply()`.

---

### 📈 **Level 5: Ranking & Cumulative**

**Q12.** Create:

```python
data = {'Product': ['TV', 'Laptop', 'Phone', 'Tablet'],
        'Sales': [50000, 75000, 30000, 40000]}
```

Tasks:

1. Add a column `Rank` by Sales (highest = rank 1).
2. Add a column `Cumulative_Sales` showing running total.
3. Calculate cumulative percentage of total sales.

---

### 💡 **Mini Project: Employee Performance Analysis**

**Dataset:**

```python
df = pd.DataFrame({
    'Name': ['Ayaan', 'Ravi', 'Neha', 'Pooja', 'Meena', 'Arun'],
    'Department': ['IT', 'IT', 'HR', 'Finance', 'Finance', 'HR'],
    'Salary': [60000, 65000, 50000, 70000, 72000, 52000],
    'Experience': [3, 5, 2, 8, 9, 4]
})
```

**Tasks:**

1. Add a column `Level`:

   * `< 3 years` → “Junior”
   * `3–7 years` → “Mid”
   * `> 7 years` → “Senior”
2. Group by Department and find:

   * Avg Salary
   * Max Experience
3. Rank all employees by Salary.
4. Find cumulative salary by department.
5. Save the final output to `employee_analysis.csv`.

---

✅ **Next Step Recommendation:**
You now understand **advanced data manipulation**, Ayaan — the final chapters will tie everything together.
Up next:

📘 **Chapter 10 – Input/Output & Exporting Data**
You’ll learn to:

* Read/write CSV, Excel, SQL
* Handle large datasets efficiently
* Integrate with Power BI, Excel, and SQL pipelines

---


# 🧾 **Pandas Chapter 10 — Input / Output & Exporting Data**

---

## 🧠 **Concept Notes**

---

### 📘 **1. Introduction**

In real-world data analysis, your datasets come from multiple places:
✅ CSV files
✅ Excel spreadsheets
✅ Databases (SQL)
✅ JSON or APIs

Pandas provides simple, powerful tools for **reading and writing data** to these formats.

---

## 📂 **2. Reading Data from CSV**

#### Syntax:

```python
import pandas as pd
df = pd.read_csv('data.csv')
```

#### Common parameters:

| Parameter                 | Description                       |
| ------------------------- | --------------------------------- |
| `sep=','`                 | Field separator                   |
| `header=0`                | Row number to use as column names |
| `index_col='id'`          | Column to use as index            |
| `nrows=100`               | Read first N rows                 |
| `usecols=['Name', 'Age']` | Read specific columns             |

#### Example:

```python
df = pd.read_csv('employees.csv', usecols=['Name', 'Salary'], nrows=10)
```

---

## 📊 **3. Writing Data to CSV**

```python
df.to_csv('output.csv', index=False)
```

**index=False** → prevents writing row numbers.

You can also set a custom separator:

```python
df.to_csv('output.tsv', sep='\t')
```

---

## 🧾 **4. Reading Data from Excel**

You’ll need **openpyxl** or **xlrd** installed:

```bash
pip install openpyxl
```

#### Read Excel:

```python
df = pd.read_excel('sales.xlsx', sheet_name='Sheet1')
```

#### Write Excel:

```python
df.to_excel('sales_summary.xlsx', index=False, sheet_name='Summary')
```

---

## 🌐 **5. Reading Data from JSON**

JSON (JavaScript Object Notation) is widely used in APIs and web data.

#### Example:

```python
data = pd.read_json('data.json')
```

If you have a JSON string:

```python
import json
records = '[{"Name": "Ayaan", "Age": 31}, {"Name": "Ravi", "Age": 25}]'
df = pd.read_json(records)
```

#### Export to JSON:

```python
df.to_json('data_output.json', orient='records', indent=4)
```

---

## 🧮 **6. Reading and Writing SQL Data**

Pandas integrates with SQL databases like MySQL, SQLite, PostgreSQL.

You’ll need **SQLAlchemy**:

```bash
pip install sqlalchemy
```

#### Example using SQLite:

```python
from sqlalchemy import create_engine

engine = create_engine('sqlite:///company.db')

# Read from SQL
df = pd.read_sql('SELECT * FROM employees', con=engine)

# Write to SQL
df.to_sql('employee_backup', con=engine, index=False, if_exists='replace')
```

| Parameter   | Description                                              |
| ----------- | -------------------------------------------------------- |
| `index`     | Include row index?                                       |
| `if_exists` | What to do if table exists (‘fail’, ‘replace’, ‘append’) |

---

## 🔁 **7. Reading Data from Clipboard**

Quickly copy-paste data from Excel or websites:

```python
df = pd.read_clipboard()
```

Then check:

```python
df.head()
```

---

## 🧩 **8. Reading Data from URLs**

You can directly load data hosted online:

```python
url = 'https://raw.githubusercontent.com/datasets/covid-19/main/data/countries-aggregated.csv'
df = pd.read_csv(url)
```

---

## 🧰 **9. Working with Large Files**

For massive datasets (millions of rows):

#### Read in chunks:

```python
chunks = pd.read_csv('large_file.csv', chunksize=100000)
for chunk in chunks:
    print(chunk.shape)
```

#### Read only specific columns:

```python
df = pd.read_csv('large_file.csv', usecols=['Name', 'Salary'])
```

#### Memory optimization:

```python
df = pd.read_csv('large_file.csv', dtype={'ID': 'int32', 'Salary': 'float32'})
```

---

## 🧱 **10. Export Formats Summary**

| Format     | Read | Write | Function                           |
| ---------- | ---- | ----- | ---------------------------------- |
| CSV        | ✅    | ✅     | `pd.read_csv()`, `df.to_csv()`     |
| Excel      | ✅    | ✅     | `pd.read_excel()`, `df.to_excel()` |
| JSON       | ✅    | ✅     | `pd.read_json()`, `df.to_json()`   |
| SQL        | ✅    | ✅     | `pd.read_sql()`, `df.to_sql()`     |
| Clipboard  | ✅    | ❌     | `pd.read_clipboard()`              |
| HTML Table | ✅    | ✅     | `pd.read_html()`, `df.to_html()`   |

---

## 📈 **11. Export to HTML or Power BI Integration**

Exporting to HTML (for dashboards or reports):

```python
df.to_html('report.html', index=False)
```

Power BI can directly connect to:

* CSV
* Excel
* SQL Databases

You can prepare cleaned datasets in Pandas and **export to CSV or SQL**, then connect Power BI to those sources.

---

## 🧮 **12. Real-World Use Cases**

✅ Import Excel sales files from multiple months
✅ Merge them and clean data with Pandas
✅ Export to `clean_sales.csv` → load into Power BI
✅ Read/write SQL data for automated reporting pipelines

---

## 🧾 **Quick Summary**

| Task        | Function              |
| ----------- | --------------------- |
| Read CSV    | `pd.read_csv()`       |
| Write CSV   | `.to_csv()`           |
| Read Excel  | `pd.read_excel()`     |
| Write Excel | `.to_excel()`         |
| Read JSON   | `pd.read_json()`      |
| Write JSON  | `.to_json()`          |
| SQL Read    | `pd.read_sql()`       |
| SQL Write   | `.to_sql()`           |
| URL Data    | `pd.read_csv(url)`    |
| Clipboard   | `pd.read_clipboard()` |

---

# 🧩 **Pandas Chapter 10 — Practice Sheet**

---

### 🧠 **Level 1: Basic File Operations**

**Q1.** Load a CSV file named `employees.csv`.
**Q2.** Display only `Name`, `Department`, and `Salary` columns.
**Q3.** Export the filtered DataFrame as `employees_summary.csv`.

---

### ⚙️ **Level 2: Excel Files**

**Q4.** Read data from an Excel file named `sales_data.xlsx`.
**Q5.** Create a new column `Discounted_Price = Price * 0.9`.
**Q6.** Save the updated file as `sales_updated.xlsx`.

---

### 🧩 **Level 3: JSON and SQL**

**Q7.** Read a JSON file `products.json`.
**Q8.** Convert it to a DataFrame and export it as `products.csv`.
**Q9.** Load a table named `orders` from an SQLite database `shop.db`.
**Q10.** Export it to a new table `orders_backup`.

---

### 🧱 **Level 4: URL and Large File Handling**

**Q11.** Read online CSV from:

```python
url = 'https://raw.githubusercontent.com/datasets/population/master/data/population.csv'
```

Display top 5 rows.

**Q12.** Read the same file in chunks of 50000 rows and count the number of chunks.

---

### 💡 **Mini Project: Complete Data Pipeline**

Create a full pipeline:

1. Import CSV file → `sales_q1.csv`
2. Clean missing values and drop duplicates
3. Add a column `Quarter = 'Q1'`
4. Save as `clean_sales_q1.csv`
5. Export the cleaned file to a SQL table `sales_data`
6. Export a summary to Excel as `sales_summary.xlsx`

---

✅ **You’ve now completed all core and advanced Pandas chapters!**

You can now:

* Import data (CSV, Excel, SQL)
* Clean, transform, and merge datasets
* Aggregate, visualize, and export your results
* Build full **data analysis workflows** ready for Power BI or dashboards

---

# 🧾 **Pandas Chapter 11 — NoSQL & API Integration with Pandas**

---

## 🧠 **Concept Notes**

---

### 📘 **1. Why Learn This?**

Modern analysts often need to pull data from:

* Web APIs (like weather, stock market, or social media data)
* NoSQL databases (like MongoDB)
* JSON responses from cloud-based systems

Learning to handle **API + NoSQL data** with Pandas lets you:
✅ Automate data collection
✅ Work with real-time data sources
✅ Build modern analytics pipelines

---

## 🌐 **2. What is an API?**

**API (Application Programming Interface)** lets two systems talk to each other.
In data analysis, you can use APIs to pull live data in JSON format.

Example APIs:

* [OpenWeatherMap](https://openweathermap.org/api)
* [CoinGecko](https://www.coingecko.com/en/api)
* [REST Countries](https://restcountries.com/)
* [Fake Store API](https://fakestoreapi.com/)

---

## 🔹 **3. Fetching Data from an API**

You use the **`requests`** library to call APIs.

Install it first (if needed):

```bash
pip install requests
```

Example:

```python
import requests
import pandas as pd

url = 'https://restcountries.com/v3.1/all'
response = requests.get(url)

# Convert JSON response to Python object
data = response.json()

# Load into Pandas DataFrame
df = pd.json_normalize(data)
```

---

### 🔍 **4. Understanding `pd.json_normalize()`**

APIs often return **nested JSON** (like dictionaries inside dictionaries).
`json_normalize()` helps flatten this into columns.

Example:

```python
data = [
    {'name': {'common': 'India'}, 'region': 'Asia', 'population': 1400000000},
    {'name': {'common': 'Germany'}, 'region': 'Europe', 'population': 83000000}
]

df = pd.json_normalize(data)
print(df)
```

**Output:**

| name.common | region | population |
| ----------- | ------ | ---------- |
| India       | Asia   | 1400000000 |
| Germany     | Europe | 83000000   |

---

### ⚙️ **5. Selecting Useful Columns**

Often, JSON APIs return many fields you don’t need.

Example:

```python
df = df[['name.common', 'region', 'population']]
df.rename(columns={'name.common': 'Country'}, inplace=True)
```

---

### 📈 **6. Example: Fetching Cryptocurrency Data**

```python
url = 'https://api.coingecko.com/api/v3/coins/markets'
params = {'vs_currency': 'usd', 'order': 'market_cap_desc', 'per_page': 5}
response = requests.get(url, params=params)
data = response.json()

df = pd.json_normalize(data)
df[['id', 'symbol', 'current_price', 'market_cap']]
```

**Output Example:**

| id       | symbol | current_price | market_cap   |
| -------- | ------ | ------------- | ------------ |
| bitcoin  | btc    | 37000         | 700000000000 |
| ethereum | eth    | 2100          | 250000000000 |

---

## 🧩 **7. Connecting Pandas to MongoDB (NoSQL)**

MongoDB stores data in JSON-like documents — perfect for Pandas.

Install **pymongo**:

```bash
pip install pymongo
```

#### Example:

```python
from pymongo import MongoClient
import pandas as pd

# Connect to MongoDB
client = MongoClient('mongodb://localhost:27017/')
db = client['company']
collection = db['employees']

# Fetch all documents
data = list(collection.find())

# Convert to DataFrame
df = pd.DataFrame(data)
print(df.head())
```

---

### 🧱 **8. Writing Data from Pandas to MongoDB**

```python
records = df.to_dict(orient='records')
collection.insert_many(records)
```

---

### 📊 **9. Converting API or Mongo Data for Power BI**

After pulling API or NoSQL data, you can:

```python
df.to_csv('api_data.csv', index=False)
```

Then import into:

* **Power BI**
* **Excel**
* **SQL database**

---

### 💡 **10. Example Workflow: API → Pandas → Power BI**

#### Step 1: Fetch API Data

```python
url = 'https://fakestoreapi.com/products'
response = requests.get(url)
data = response.json()
df = pd.json_normalize(data)
```

#### Step 2: Clean & Transform

```python
df = df[['id', 'title', 'price', 'category']]
df['price'] = df['price'].astype(float)
```

#### Step 3: Export to CSV

```python
df.to_csv('fakestore_data.csv', index=False)
```

✅ Now this CSV can be imported directly into Power BI or Excel dashboards.

---

### 🧮 **11. Common Real-World Use Cases**

| Use Case                      | Data Source                        | Method                        |
| ----------------------------- | ---------------------------------- | ----------------------------- |
| Stock market data             | API (Yahoo Finance, Alpha Vantage) | `requests`                    |
| Weather data                  | API (OpenWeatherMap)               | `requests` + `json_normalize` |
| MongoDB company data          | NoSQL                              | `pymongo`                     |
| Product data from Shopify API | REST API                           | `requests`                    |
| Social analytics              | Twitter / Reddit APIs              | `requests` or libraries       |

---

## 🧾 **Quick Summary**

| Task                              | Function / Tool            |
| --------------------------------- | -------------------------- |
| Fetch API data                    | `requests.get()`           |
| Convert JSON → DataFrame          | `pd.json_normalize()`      |
| Connect to MongoDB                | `pymongo.MongoClient()`    |
| Insert Pandas DataFrame → MongoDB | `collection.insert_many()` |
| Export to CSV                     | `.to_csv()`                |
| Clean nested JSON                 | `.json_normalize()`        |

---

# 🧩 **Pandas Chapter 11 — Practice Sheet**

---

### 🧠 **Level 1: JSON to Pandas**

**Q1.** Fetch data from:

```python
url = 'https://restcountries.com/v3.1/all'
```

Tasks:

1. Load it into a DataFrame.
2. Keep only `name.common`, `region`, and `population`.
3. Rename columns to `Country`, `Region`, `Population`.

---

### ⚙️ **Level 2: API + Data Cleaning**

**Q4.** Fetch cryptocurrency data:

```python
url = 'https://api.coingecko.com/api/v3/coins/markets'
params = {'vs_currency': 'usd', 'order': 'market_cap_desc', 'per_page': 5}
```

Tasks:

1. Create a DataFrame of top 5 coins.
2. Display columns: `id`, `symbol`, `current_price`, `market_cap`.
3. Save it as `crypto_top5.csv`.

---

### 🧩 **Level 3: MongoDB Connection**

**Q7.** Connect to local MongoDB collection `students`.

1. Read data using `find()`.
2. Convert to Pandas DataFrame.
3. Export the data to `students_backup.csv`.

---

### 💡 **Level 4: Real API Integration Challenge**

Fetch from Fake Store API:

```python
url = 'https://fakestoreapi.com/products'
```

**Tasks:**

1. Load into Pandas DataFrame.
2. Extract columns: `id`, `title`, `price`, `category`.
3. Filter only products with `price > 50`.
4. Save cleaned data as `expensive_products.csv`.

---

### 🚀 **Mini Project: Weather Data API**

**Goal:** Build a mini dataset from OpenWeatherMap API.

1. Register for a free API key: [https://openweathermap.org/api](https://openweathermap.org/api)
2. Use this code:

```python
import requests, pandas as pd

cities = ['London', 'Delhi', 'Mumbai', 'New York']
api_key = 'YOUR_API_KEY'
data = []

for city in cities:
    url = f'https://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}&units=metric'
    r = requests.get(url)
    d = r.json()
    data.append({
        'City': city,
        'Temperature': d['main']['temp'],
        'Weather': d['weather'][0]['description']
    })

df = pd.DataFrame(data)
print(df)
df.to_csv('weather_report.csv', index=False)
```

✅ This gives you a **real-time weather report** DataFrame — perfect for dashboarding in Power BI or Excel!

---

## 🧾 **Chapter Summary**

| Concept             | Key Skill                                      |
| ------------------- | ---------------------------------------------- |
| API Integration     | Fetch live data using `requests`               |
| JSON Handling       | Flatten nested JSON with `pd.json_normalize()` |
| MongoDB Integration | Read/write with `pymongo`                      |
| Export for BI Tools | `.to_csv()` / `.to_excel()`                    |
| Real-World Pipeline | API → Pandas → CSV → Power BI                  |

---

✅ **You’ve now completed all core + advanced + integration chapters (1–11)!**

You can now:

* Work with CSV, Excel, SQL, NoSQL, and API data
* Clean, merge, and analyze it
* Create visualizations
* Build end-to-end analysis pipelines for dashboards

---


# 🧾 **Pandas Chapter 12 — Performance Optimization & Large Dataset Handling**

---

## 🧠 **Concept Notes**

---

### 📘 **1. Why Optimize Pandas?**

By default, Pandas loads everything into memory (RAM).
When you’re dealing with **large CSVs, millions of rows, or complex operations**, performance can degrade.

Optimization ensures:
✅ Faster data loading
✅ Lower memory usage
✅ Efficient calculations
✅ Scalability for enterprise-level analysis

---

## ⚙️ **2. Understanding Memory Usage**

Check how much memory your DataFrame consumes:

```python
df.info(memory_usage='deep')
```

You can calculate total memory used:

```python
df.memory_usage(deep=True).sum() / (1024**2)  # in MB
```

---

### 🧩 **3. Reduce Data Types (Downcasting)**

Large datasets often use unnecessarily large data types.
Convert columns to **smaller, efficient dtypes**.

#### Example:

```python
df['ID'] = df['ID'].astype('int32')
df['Price'] = df['Price'].astype('float32')
df['Category'] = df['Category'].astype('category')
```

This can **reduce memory by 50–80%**.

---

### 🧮 **4. Convert Object Columns to Category**

Categorical data (like “City”, “Department”) often repeats — converting them helps.

```python
df['City'] = df['City'].astype('category')
```

**Before:** stored as strings
**After:** stored as numeric category codes internally

You can check unique category codes:

```python
df['City'].cat.codes
```

---

### ⚙️ **5. Use `usecols` and `dtype` When Reading Large CSVs**

When importing large files, always limit columns and define dtypes.

```python
df = pd.read_csv('large_dataset.csv',
                 usecols=['Name', 'Salary', 'Department'],
                 dtype={'Salary': 'float32', 'Department': 'category'})
```

---

### 🧾 **6. Read Data in Chunks (Streaming)**

Instead of loading a 5 GB CSV all at once, read it **in parts**.

```python
chunks = pd.read_csv('sales_data.csv', chunksize=100000)
for chunk in chunks:
    print(chunk.shape)
```

You can process and aggregate while reading:

```python
total_sales = 0
for chunk in pd.read_csv('sales.csv', chunksize=50000):
    total_sales += chunk['Revenue'].sum()
print(total_sales)
```

---

### 💡 **7. Drop Unused Columns Early**

Remove unnecessary columns **as soon as possible** after loading:

```python
df.drop(['Address', 'Remarks'], axis=1, inplace=True)
```

---

### 🧩 **8. Use Vectorized Operations (Avoid Loops)**

Avoid slow `for` loops — use Pandas built-in vectorized methods.

❌ Slow:

```python
for i in range(len(df)):
    df.loc[i, 'Discounted'] = df.loc[i, 'Price'] * 0.9
```

✅ Fast:

```python
df['Discounted'] = df['Price'] * 0.9
```

Pandas operations are internally optimized using **NumPy’s C engine**, so they run faster.

---

### 🧮 **9. Use `.apply()` Wisely**

`apply()` is convenient but not always the fastest.
Use **vectorized functions or NumPy** instead, when possible.

#### Example:

```python
import numpy as np

df['CategoryFlag'] = np.where(df['Category'] == 'Electronics', 1, 0)
```

---

### ⚡ **10. Optimize String Operations**

String operations can be slow — use `.str` methods efficiently.

Instead of:

```python
df['Email'].apply(lambda x: x.lower())
```

Use vectorized:

```python
df['Email'] = df['Email'].str.lower()
```

---

### 🧰 **11. Use `categorical` and Indexing for Speed**

#### Set index for faster lookups:

```python
df.set_index('ID', inplace=True)
df.loc[12345]
```

#### Convert text to category for joins or filters:

```python
df['Department'] = df['Department'].astype('category')
```

---

### 🧮 **12. Parallelization with Dask (Optional Advanced)**

For very large data (10M+ rows), you can use **Dask**, which extends Pandas to multi-core parallelism.

Install:

```bash
pip install dask
```

Use:

```python
import dask.dataframe as dd
df = dd.read_csv('huge_file.csv')
df['Revenue'].mean().compute()
```

✅ Works like Pandas, but processes in parallel chunks.

---

### 🧱 **13. Save Efficient File Formats (Feather / Parquet)**

Feather and Parquet are **compressed, columnar formats** that load **10–50x faster** than CSV.

#### Save as Feather:

```python
df.to_feather('data.feather')
```

#### Read Feather:

```python
pd.read_feather('data.feather')
```

#### Save as Parquet:

```python
df.to_parquet('data.parquet', index=False)
```

#### Read Parquet:

```python
pd.read_parquet('data.parquet')
```

---

### ⚙️ **14. Garbage Collection for Memory Cleanup**

When working with big loops or temporary DataFrames:

```python
import gc
del temp_df
gc.collect()
```

---

### 🧩 **15. Summarizing Optimization Techniques**

| Technique             | Description                | Benefit                  |
| --------------------- | -------------------------- | ------------------------ |
| Downcast dtypes       | Use smaller numeric types  | ↓ Memory                 |
| Convert to category   | Replace strings with codes | ↓ Memory, ↑ Speed        |
| Read in chunks        | Stream data                | ↓ Memory                 |
| Use vectorized ops    | Replace loops              | ↑ Speed                  |
| Drop columns early    | Remove junk columns        | ↓ Memory                 |
| Use efficient formats | Feather/Parquet            | ↑ I/O Speed              |
| Parallelization       | Dask or Modin              | ↑ Multi-core performance |

---

## 🧾 **Quick Summary**

| Task                   | Method                            |
| ---------------------- | --------------------------------- |
| Check memory usage     | `.info(memory_usage='deep')`      |
| Convert to category    | `.astype('category')`             |
| Read selective columns | `usecols=`                        |
| Process large files    | `chunksize=`                      |
| Avoid loops            | Vectorized ops                    |
| Save fast format       | `.to_parquet()` / `.to_feather()` |
| Free memory            | `gc.collect()`                    |

---

# 🧩 **Pandas Chapter 12 — Practice Sheet**

---

### 🧠 **Level 1: Memory Optimization**

**Q1.** Load a large CSV file named `employees_large.csv`.
**Q2.** Check its memory usage.
**Q3.** Convert all `object` columns to `category`.
**Q4.** Downcast numeric columns to smallest types.
**Q5.** Check memory usage again — how much reduced?

---

### ⚙️ **Level 2: Chunk Loading**

**Q6.** Load `sales_data.csv` using `chunksize=100000`.
**Q7.** For each chunk, calculate the sum of `Revenue`.
**Q8.** Combine total revenue from all chunks.

---

### 🧩 **Level 3: Vectorization**

**Q9.** Add a column `DiscountedPrice` = `Price * 0.9` without using loops.
**Q10.** Add a flag column `IsHighValue` = 1 if `Price > 50000`, else 0.

---

### 📈 **Level 4: Parquet Conversion**

**Q11.** Save your cleaned DataFrame as `cleaned_data.parquet`.
**Q12.** Read the Parquet file back into Pandas.
**Q13.** Compare loading time vs the same file in CSV format.

---

### 💡 **Level 5: Real-World Project — Large Data Pipeline**

**Goal:** Process and optimize a large sales dataset for analysis.

**Steps:**

1. Load `sales_2024.csv` (5M+ rows) in chunks of 100,000.
2. For each chunk:

   * Drop unnecessary columns (`Address`, `Remarks`)
   * Calculate `NetRevenue = Revenue - Discount`
   * Append to a list
3. Combine all chunks into one DataFrame using `pd.concat()`.
4. Convert `Category` and `Region` to `category`.
5. Save optimized data as `sales_2024_optimized.parquet`.
6. Print total memory saved compared to CSV.

---

✅ **You’ve now mastered every professional Pandas concept!**

You can now handle:

* CSV, Excel, JSON, SQL, MongoDB, and APIs
* Clean and merge complex datasets
* Visualize and aggregate
* Optimize and scale for large data pipelines


---

---

# 🧾 **Pandas Chapter 13 — Pandas + NumPy + Matplotlib Integration**

---

## 🧠 **Concept Notes**

---

### 📘 **1. Why Combine Pandas, NumPy, and Matplotlib?**

| Library        | Role in Data Analysis                        |
| -------------- | -------------------------------------------- |
| **Pandas**     | Data handling, transformation, cleaning      |
| **NumPy**      | Numerical computing, arrays, math operations |
| **Matplotlib** | Data visualization and charting              |

Together, they form a **complete data analysis ecosystem** — everything from importing to visualization.

---

## ⚙️ **2. The Data Analysis Workflow**

Here’s the typical order in any real-world project:

1️⃣ **Load data with Pandas**
2️⃣ **Clean and preprocess data**
3️⃣ **Use NumPy for math/statistics**
4️⃣ **Visualize results with Matplotlib or Seaborn**

---

## 🧩 **3. Using NumPy with Pandas**

NumPy powers Pandas internally — you can directly apply NumPy functions to Pandas columns.

#### Example:

```python
import pandas as pd
import numpy as np

df = pd.DataFrame({
    'Product': ['TV', 'Laptop', 'Phone', 'Tablet'],
    'Price': [50000, 75000, 30000, 25000],
    'Discount': [10, 5, 15, 8]
})

df['DiscountedPrice'] = df['Price'] - (df['Price'] * df['Discount'] / 100)
df['ProfitMargin'] = np.where(df['DiscountedPrice'] > 40000, 'High', 'Low')
```

✅ Here, Pandas handled the data, and NumPy handled conditional and mathematical logic.

---

### 💡 Common NumPy Functions with Pandas

| Function      | Description        | Example                               |
| ------------- | ------------------ | ------------------------------------- |
| `np.mean()`   | Mean               | `np.mean(df['Price'])`                |
| `np.median()` | Median             | `np.median(df['Price'])`              |
| `np.std()`    | Standard deviation | `np.std(df['Price'])`                 |
| `np.where()`  | Conditional update | `np.where(df['Price'] > 40000, 1, 0)` |
| `np.round()`  | Rounding values    | `np.round(df['DiscountedPrice'], 2)`  |

---

### 🧮 **4. Statistical Analysis Example**

```python
avg_price = np.mean(df['Price'])
max_discount = np.max(df['Discount'])
price_std = np.std(df['Price'])

print(f"Average Price: {avg_price}")
print(f"Max Discount: {max_discount}")
print(f"Price Std Dev: {price_std}")
```

---

## 📊 **5. Using Matplotlib with Pandas**

### Basic Setup:

```python
import matplotlib.pyplot as plt
plt.style.use('seaborn-v0_8')
```

You can directly plot Pandas DataFrames using Matplotlib.

---

### 🧱 **Example 1: Bar Chart**

```python
df.plot(x='Product', y='Price', kind='bar', color='skyblue', title='Product Prices')
plt.ylabel('Price')
plt.show()
```

---

### 🧩 **Example 2: Line Chart**

```python
sales = pd.DataFrame({
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
    'Revenue': [20000, 25000, 23000, 27000, 30000]
})
sales.plot(x='Month', y='Revenue', kind='line', marker='o', title='Monthly Revenue Trend')
plt.show()
```

---

### 📈 **Example 3: Scatter Plot (Correlation)**

```python
df.plot(kind='scatter', x='Price', y='DiscountedPrice', color='orange', title='Price vs Discounted Price')
plt.show()
```

---

### 🧠 **6. Combining NumPy Calculations + Matplotlib Visualization**

Let’s calculate a statistical insight using NumPy and visualize it using Matplotlib.

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

data = np.random.randint(20, 80, 50)
df = pd.DataFrame({'Marks': data})

mean = np.mean(df['Marks'])
std_dev = np.std(df['Marks'])

plt.hist(df['Marks'], bins=10, color='lightblue', edgecolor='black')
plt.axvline(mean, color='red', linestyle='dashed', linewidth=2, label=f'Mean = {mean:.2f}')
plt.axvline(mean + std_dev, color='green', linestyle='dotted', linewidth=1, label='+1 Std Dev')
plt.axvline(mean - std_dev, color='green', linestyle='dotted', linewidth=1)
plt.title('Student Marks Distribution')
plt.legend()
plt.show()
```

✅ NumPy did the stats; Matplotlib visualized it.

---

### 🧮 **7. Correlation Heatmap Example**

Combine Pandas + NumPy + Matplotlib for correlation analysis.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

df = pd.DataFrame({
    'Sales': np.random.randint(1000, 5000, 10),
    'Profit': np.random.randint(200, 800, 10),
    'Expense': np.random.randint(500, 2000, 10)
})

corr = df.corr()
plt.imshow(corr, cmap='coolwarm', interpolation='none')
plt.colorbar()
plt.xticks(range(len(corr)), corr.columns, rotation=45)
plt.yticks(range(len(corr)), corr.columns)
plt.title('Correlation Heatmap')
plt.show()
```

---

### 💾 **8. Saving Visualizations**

You can export any plot to an image for reports or dashboards.

```python
plt.savefig('correlation_heatmap.png', dpi=300, bbox_inches='tight')
```

---

## 🧱 **9. End-to-End Example: Sales Analysis Pipeline**

This example shows how Pandas + NumPy + Matplotlib work together in a real project.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load data
sales = pd.DataFrame({
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'],
    'Revenue': [20000, 25000, 23000, 27000, 30000, 33000],
    'Expense': [12000, 15000, 14000, 16000, 18000, 20000]
})

# Step 2: Analysis with NumPy
sales['Profit'] = sales['Revenue'] - sales['Expense']
avg_profit = np.mean(sales['Profit'])

# Step 3: Visualization with Matplotlib
plt.plot(sales['Month'], sales['Revenue'], label='Revenue', marker='o')
plt.plot(sales['Month'], sales['Expense'], label='Expense', marker='s')
plt.plot(sales['Month'], sales['Profit'], label='Profit', marker='^')

plt.axhline(avg_profit, color='red', linestyle='--', label=f'Avg Profit = {avg_profit:.0f}')
plt.title('Company Performance Overview')
plt.xlabel('Month')
plt.ylabel('Amount ($)')
plt.legend()
plt.grid(True)
plt.show()
```

✅ Pandas handles data, NumPy adds insights, and Matplotlib tells the story visually.

---

## 🧾 **Quick Summary**

| Task          | Library    | Function                                        |
| ------------- | ---------- | ----------------------------------------------- |
| Data handling | Pandas     | `DataFrame`, `groupby`, `merge`                 |
| Numeric ops   | NumPy      | `mean`, `std`, `where`, `round`                 |
| Visualization | Matplotlib | `plot`, `bar`, `scatter`, `hist`                |
| Integration   | All        | Pandas + NumPy for logic, Matplotlib for output |

---

# 🧩 **Pandas Chapter 13 — Practice Sheet**

---

### 🧠 **Level 1: NumPy + Pandas Integration**

**Q1.** Create a DataFrame:

```python
df = pd.DataFrame({'Sales': [20000, 35000, 40000, 45000, 50000]})
```

Tasks:

1. Use NumPy to calculate mean and standard deviation.
2. Add a new column `Performance` = `'High'` if Sales > mean, else `'Low'`.

---

### ⚙️ **Level 2: Basic Visualization**

**Q4.** Plot a **bar chart** of Sales.
**Q5.** Add a horizontal line showing the average Sales using `plt.axhline()`.

---

### 🧩 **Level 3: Combined Analysis**

**Q7.** Create:

```python
data = {'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
        'Revenue': [10000, 15000, 20000, 25000, 30000],
        'Expense': [5000, 7000, 9000, 12000, 15000]}
```

Tasks:

1. Compute Profit = Revenue – Expense (NumPy).
2. Plot all three (Revenue, Expense, Profit) on a single line chart (Matplotlib).
3. Add average Profit line in red.

---

### 💡 **Level 4: Correlation Heatmap**

**Q10.** Create a DataFrame with `Revenue`, `Profit`, and `Expense` for 10 records.

1. Compute correlation matrix with `df.corr()`.
2. Visualize with `plt.imshow()` and colorbar.
3. Save chart as `correlation_heatmap.png`.

---

### 🚀 **Mini Project: End-to-End Analytics Dashboard**

**Goal:** Combine all libraries to build a complete performance dashboard.

**Steps:**

1. Import monthly financial data (Pandas).
2. Clean data (drop NAs, convert to proper types).
3. Use NumPy to calculate:

   * Profit, Loss%
   * Average Revenue
4. Visualize trends using Matplotlib (line chart for Revenue & Profit).
5. Save both cleaned data (`clean_financials.csv`) and visual charts.

---

## 🧾 **Chapter Summary**

| Step          | Library    | Function                               |
| ------------- | ---------- | -------------------------------------- |
| Import/Clean  | Pandas     | `read_csv()`, `.dropna()`, `.astype()` |
| Math/Logic    | NumPy      | `np.mean()`, `np.where()`, `np.std()`  |
| Visualization | Matplotlib | `.plot()`, `.bar()`, `.hist()`         |
| Save Output   | All        | `.to_csv()`, `plt.savefig()`           |

---

✅ **You’ve now completed the full Pandas Master Series (Ch. 1–13)!**

You can now:

* Build **data pipelines from raw files, APIs, or databases**
* Perform **statistical and mathematical analysis**
* Visualize with **Matplotlib**
* Export clean results for **Power BI or dashboards**

---

---

# 🧾 **📊 Pandas Capstone Project — Retail Sales Analysis Dashboard**

---

## 🎯 **Project Objective**

You’re a **Data Analyst** for a retail company called **RetailX**.
Your task is to analyze and visualize **sales performance across regions, products, and time periods**, and generate insights for management.

The dataset comes from different sources:

* `sales.csv` → Daily sales transactions
* `customers.csv` → Customer demographics
* `products.csv` → Product catalog
* `regions.csv` → Regional targets

---

## 📂 **1. Project Data Overview**

Each file contains:

### 🧾 `sales.csv`

| Column     | Description           |
| ---------- | --------------------- |
| SaleID     | Unique transaction ID |
| Date       | Date of sale          |
| CustomerID | Customer reference    |
| ProductID  | Product reference     |
| Quantity   | Number of units sold  |
| UnitPrice  | Price per unit        |
| Region     | Region of sale        |

---

### 🧑‍🤝‍🧑 `customers.csv`

| Column     | Description       |
| ---------- | ----------------- |
| CustomerID | Unique ID         |
| Name       | Customer name     |
| Age        | Customer age      |
| Gender     | Male/Female       |
| City       | Customer location |

---

### 📦 `products.csv`

| Column    | Description                                    |
| --------- | ---------------------------------------------- |
| ProductID | Unique product ID                              |
| Category  | Product category (Electronics, Clothing, etc.) |
| Brand     | Product brand                                  |
| CostPrice | Cost per unit                                  |

---

### 🌍 `regions.csv`

| Column        | Description                          |
| ------------- | ------------------------------------ |
| Region        | Region name                          |
| TargetRevenue | Target sales revenue for that region |

---

---

## ⚙️ **2. Step-by-Step Data Analysis Pipeline**

---

### 🔹 **Step 1: Import Libraries**

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
plt.style.use('seaborn-v0_8')
```

---

### 🔹 **Step 2: Load Data**

```python
sales = pd.read_csv('sales.csv')
customers = pd.read_csv('customers.csv')
products = pd.read_csv('products.csv')
regions = pd.read_csv('regions.csv')
```

---

### 🔹 **Step 3: Initial Exploration**

```python
print(sales.head())
print(sales.info())
print(sales.describe())
```

✅ Check for:

* Missing values
* Duplicates
* Data types

---

### 🔹 **Step 4: Data Cleaning**

```python
# Handle missing values
sales.dropna(inplace=True)

# Convert date to datetime
sales['Date'] = pd.to_datetime(sales['Date'])

# Remove duplicates
sales.drop_duplicates(inplace=True)

# Standardize string columns
sales['Region'] = sales['Region'].str.title()
```

---

### 🔹 **Step 5: Data Enrichment (Merging)**

Combine all datasets into one master table.

```python
df = sales.merge(customers, on='CustomerID', how='left')
df = df.merge(products, on='ProductID', how='left')
df = df.merge(regions, on='Region', how='left')
```

✅ Now `df` contains all the data in one place.

---

### 🔹 **Step 6: Feature Engineering**

Add new derived columns for deeper insights.

```python
df['Revenue'] = df['Quantity'] * df['UnitPrice']
df['Profit'] = df['Revenue'] - (df['Quantity'] * df['CostPrice'])
df['ProfitMargin'] = np.round((df['Profit'] / df['Revenue']) * 100, 2)
df['Month'] = df['Date'].dt.month_name()
df['Year'] = df['Date'].dt.year
```

---

### 🔹 **Step 7: Aggregations & KPIs**

#### a) Overall KPIs:

```python
total_revenue = df['Revenue'].sum()
total_profit = df['Profit'].sum()
avg_margin = df['ProfitMargin'].mean()

print(f"Total Revenue: ₹{total_revenue:,.0f}")
print(f"Total Profit: ₹{total_profit:,.0f}")
print(f"Avg Profit Margin: {avg_margin:.2f}%")
```

#### b) Region-wise performance:

```python
region_summary = df.groupby('Region')[['Revenue', 'Profit']].sum().reset_index()
region_summary['TargetAchieved_%'] = (region_summary['Revenue'] / df.groupby('Region')['TargetRevenue'].first()) * 100
```

#### c) Category-wise sales:

```python
category_summary = df.groupby('Category')[['Revenue', 'Profit']].sum().sort_values('Revenue', ascending=False)
```

---

### 🔹 **Step 8: Visualization (Matplotlib)**

#### a) **Revenue by Region**

```python
region_summary.plot(kind='bar', x='Region', y='Revenue', title='Revenue by Region', color='skyblue')
plt.ylabel('Revenue (₹)')
plt.show()
```

#### b) **Profit by Category**

```python
category_summary.plot(kind='barh', y='Profit', color='lightgreen', title='Profit by Product Category')
plt.xlabel('Profit (₹)')
plt.show()
```

#### c) **Monthly Trend**

```python
monthly_trend = df.groupby(['Year', 'Month'])['Revenue'].sum().reset_index()
plt.plot(monthly_trend['Month'], monthly_trend['Revenue'], marker='o', color='orange')
plt.title('Monthly Revenue Trend')
plt.xlabel('Month')
plt.ylabel('Revenue (₹)')
plt.grid(True)
plt.show()
```

---

### 🔹 **Step 9: Regional Target Comparison**

```python
merged_target = region_summary.merge(regions, on='Region')
merged_target.plot(x='Region', y=['Revenue', 'TargetRevenue'], kind='bar', title='Target vs Actual Revenue')
plt.ylabel('Revenue (₹)')
plt.show()
```

---

### 🔹 **Step 10: Customer Insights**

```python
customer_age = df.groupby('Age')['Revenue'].sum()
customer_age.plot(kind='line', color='purple', title='Revenue by Customer Age')
plt.xlabel('Age')
plt.ylabel('Revenue (₹)')
plt.show()
```

---

### 🔹 **Step 11: Top Products**

```python
top_products = df.groupby('ProductID')['Revenue'].sum().sort_values(ascending=False).head(5)
top_products.plot(kind='bar', title='Top 5 Products by Revenue', color='gold')
plt.ylabel('Revenue (₹)')
plt.show()
```

---

### 🔹 **Step 12: Export Insights**

Export clean datasets and summaries:

```python
df.to_csv('clean_sales_data.csv', index=False)
region_summary.to_csv('region_summary.csv', index=False)
category_summary.to_csv('category_summary.csv', index=False)
```

---

## 🧮 **13. Summary Metrics**

| Metric          | Formula                            | Example                              |
| --------------- | ---------------------------------- | ------------------------------------ |
| Revenue         | `Quantity * UnitPrice`             | 10 × 200 = ₹2,000                    |
| Profit          | `Revenue - (Quantity * CostPrice)` | ₹2,000 - ₹1,500 = ₹500               |
| Profit Margin   | `(Profit / Revenue) × 100`         | (500 / 2000) × 100 = 25%             |
| Target Achieved | `(Actual / Target) × 100`          | (1,200,000 / 1,000,000) × 100 = 120% |

---

## 📊 **14. Expected Outputs**

✅ **Data Insights**

* Which regions achieved targets?
* Which product categories generated the most profit?
* What are the seasonal (monthly) trends?
* Which customer age groups spend the most?

✅ **Visualizations**

* Revenue by Region (Bar Chart)
* Profit by Category (Horizontal Bar)
* Monthly Revenue Trend (Line Chart)
* Target vs Actual Revenue (Dual Bar)
* Revenue by Age Group (Line Chart)

✅ **Deliverables**

* `clean_sales_data.csv`
* `region_summary.csv`
* `category_summary.csv`
* 5 Matplotlib charts (saved as `.png`)

---

## 🏁 **Capstone Outcome**

By completing this project, you will have:
✅ Built a full **ETL (Extract, Transform, Load)** pipeline in Pandas
✅ Integrated **NumPy for computation**
✅ Created **Matplotlib visual dashboards**
✅ Produced exportable datasets for **Power BI or Excel reporting**

---

---

# 🧾 **Power BI Integration Project — Connecting Pandas to Power BI**

---

## 🎯 **Project Objective**

You’ll integrate your **Pandas-generated dataset** (from the Capstone Project or any analysis) directly into **Microsoft Power BI**, to visualize dynamic KPIs like:

* 💰 **Total Sales & Profit by Region**
* 🛍 **Top Products by Revenue**
* 👥 **Customer Demographics (Age, Gender)**
* 🕒 **Monthly Sales Trends**
* 🎯 **Target vs Actual Performance**

This project mimics what **real-world data analysts** do: combining **Python + Power BI** to create automated, refreshable dashboards.

---

## 🧱 **Workflow Overview**

The full integration process looks like this:

```
Pandas (Python) → Cleaned CSV / SQL Output → Power BI Data Source → Interactive Dashboard
```

---

## ⚙️ **Step 1: Prepare Data in Pandas**

From your **Capstone Project**, you already have clean data exports such as:

* `clean_sales_data.csv`
* `region_summary.csv`
* `category_summary.csv`

If not, let’s generate one again 👇

```python
import pandas as pd
import numpy as np

# Example clean dataset
sales = pd.read_csv('sales.csv')
products = pd.read_csv('products.csv')
regions = pd.read_csv('regions.csv')

df = sales.merge(products, on='ProductID', how='left')
df = df.merge(regions, on='Region', how='left')

df['Revenue'] = df['Quantity'] * df['UnitPrice']
df['Profit'] = df['Revenue'] - (df['Quantity'] * df['CostPrice'])
df['ProfitMargin'] = np.round((df['Profit'] / df['Revenue']) * 100, 2)
df['Date'] = pd.to_datetime(df['Date'])
df['Month'] = df['Date'].dt.month_name()

df.to_csv('pbi_sales_clean.csv', index=False)
```

✅ **Output:** `pbi_sales_clean.csv` → Ready for Power BI import.

---

## 🧩 **Step 2: Connect Power BI to Your Pandas Output**

1️⃣ Open **Power BI Desktop**
2️⃣ Click **Home → Get Data → Text/CSV**
3️⃣ Choose the file: `pbi_sales_clean.csv`
4️⃣ Click **Load**

Power BI will automatically detect columns and datatypes.
If you created multiple summary CSVs (`region_summary.csv`, `category_summary.csv`), load them too.

---

## 🔄 **Step 3: Automate Refresh from Pandas**

When your Python script generates new data daily or weekly, Power BI can automatically refresh it.

### Option 1 — Auto-overwrite the same CSV file

Every time your Python script runs:

```python
df.to_csv('pbi_sales_clean.csv', index=False)
```

Power BI will automatically pick up changes on refresh.

### Option 2 — Use Power BI “Python Script” connector

1. Go to **Home → Get Data → Python script**
2. Enter your Pandas script:

   ```python
   import pandas as pd
   import numpy as np

   df = pd.read_csv('sales.csv')
   df['Revenue'] = df['Quantity'] * df['UnitPrice']
   df['Profit'] = df['Revenue'] - (df['Quantity'] * df['CostPrice'])
   df
   ```
3. Power BI will run your Python code directly and load the DataFrame output.

✅ Advantage: You can update both **data and logic** inside Power BI automatically.

---

## 📊 **Step 4: Build Dashboard Visuals in Power BI**

Once data is loaded, build these key visuals:

| Dashboard Component       | Visual Type             | Fields                                                  |
| ------------------------- | ----------------------- | ------------------------------------------------------- |
| Total Revenue / Profit    | **Card**                | `SUM(Revenue)`, `SUM(Profit)`                           |
| Revenue by Region         | **Bar Chart**           | Axis: `Region`, Value: `SUM(Revenue)`                   |
| Top Products              | **Bar/Column Chart**    | Axis: `Product`, Value: `SUM(Revenue)`                  |
| Monthly Trend             | **Line Chart**          | Axis: `Month`, Value: `SUM(Revenue)`                    |
| Profit Margin by Category | **Clustered Bar Chart** | Axis: `Category`, Value: `AVG(ProfitMargin)`            |
| Target vs Actual          | **Combo Chart**         | Axis: `Region`, Lines: `TargetRevenue`, Bars: `Revenue` |

Add **filters (slicers)** for:

* Year
* Region
* Category
* Gender

---

## 🧮 **Step 5: Add KPIs and Measures**

Create **Power BI DAX Measures** to enhance insights.

Example DAX formulas:

```DAX
Total Revenue = SUM(pbi_sales_clean[Revenue])
Total Profit = SUM(pbi_sales_clean[Profit])
Profit Margin % = DIVIDE(SUM(pbi_sales_clean[Profit]), SUM(pbi_sales_clean[Revenue]), 0)
Target Achieved % = DIVIDE(SUM(pbi_sales_clean[Revenue]), SUM(pbi_sales_clean[TargetRevenue]), 0) * 100
```

✅ These dynamic measures update automatically with slicers or filters.

---

## ⚡ **Step 6: Automate Refresh Schedule**

To make it refresh automatically:

### Option A — Power BI Desktop:

Click **Refresh → Apply Changes** manually.

### Option B — Power BI Service (Cloud):

1. Publish your report to **Power BI Service**
2. Go to **Datasets → Schedule Refresh**
3. Connect your data source (local or cloud)
4. Set refresh frequency (daily/hourly)

---

## 📈 **Step 7: Optional — Connect Power BI to SQL (Pandas Export)**

Instead of CSV, store your Pandas output in a **SQL database** and connect Power BI directly.

In Python:

```python
from sqlalchemy import create_engine
engine = create_engine('sqlite:///retailx.db')
df.to_sql('sales_summary', con=engine, index=False, if_exists='replace')
```

In Power BI:

> **Get Data → SQL Server / SQLite → Enter Database Path → Load Table**

✅ Now Power BI pulls data straight from your Pandas-managed SQL database.

---

## 🧾 **Step 8: Dashboard Layout Recommendation**

### 💡 Dashboard Sections:

1. **Top KPIs**

   * Total Revenue
   * Total Profit
   * Avg Profit Margin
   * Target Achieved %

2. **Regional Analysis**

   * Bar chart → Revenue by Region
   * Combo → Target vs Actual

3. **Product Analysis**

   * Horizontal bar → Profit by Category
   * Card → Top Product by Revenue

4. **Customer Insights**

   * Donut → Gender distribution
   * Line chart → Revenue by Age group

5. **Trends**

   * Line → Monthly Revenue Trend

---

## 📦 **Step 9: Deliverables**

✅ **Python Files:**

* `generate_clean_data.py` → Creates CSV or SQL output
* `auto_refresh_script.py` → (Optional, for scheduled jobs)

✅ **Power BI Dashboard:**

* `Retail_Sales_Dashboard.pbix`

✅ **Data Files:**

* `pbi_sales_clean.csv`
* `region_summary.csv`

✅ **Documentation:**

* “How Data Flows from Python to Power BI.pdf”

---

## 🚀 **End Result: A Fully Automated BI Workflow**

**Python (ETL + Analysis) → Power BI (Visualization + Insights)**

This setup gives you:

* A **live dashboard** powered by your Python pipeline
* **Automatic refreshes** via CSV or SQL connection
* **Dynamic KPIs and filters** for decision-making

This is exactly how data analysts and BI professionals work in real-world organizations. 🧠💼

---

## 🧾 **Bonus: Extend the Integration**

| Tool                             | Purpose                                     |
| -------------------------------- | ------------------------------------------- |
| **Power BI Gateway**             | Auto-refresh local files                    |
| **Power Automate**               | Trigger Python scripts via workflow         |
| **Azure / Google Cloud Storage** | Host CSV files for cloud dashboards         |
| **DAX Measures**                 | Add advanced business logic inside Power BI |

---

## 🏁 **Project Summary**

✅ You learned to:

* Export Pandas DataFrames to Power BI–friendly formats
* Connect Power BI to Python (via CSV or script)
* Create dynamic visuals and KPIs
* Automate updates with refresh scheduling
* Integrate SQL pipelines for enterprise setups

---
