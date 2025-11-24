** Pandas Chapter 1 — Introduction to Pandas **
=============================================

🧠 **Concept Notes (Chapter 1)**
--------------------------------

### 📘 **What is Pandas?**

**Pandas** (short for _Python Data Analysis Library_) is an open-source library built on top of **NumPy**, designed for **data manipulation, cleaning, and analysis**.

It provides two powerful data structures:

*   **Series** → 1-D labeled array (like a column in Excel)
    
*   **DataFrame** → 2-D labeled data (like a spreadsheet or SQL table)
    

### ⚙️ **Installing Pandas**

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   pip install pandas   `

Importing Pandas in Python:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   import pandas as pd   `

### 📊 **1\. Pandas Data Structures**

#### 🔹 Series

A one-dimensional labeled array capable of holding any data type.

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   import pandas as pd  s = pd.Series([10, 20, 30, 40])  print(s)   `

Output:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   0    10  1    20  2    30  3    40  dtype: int64   `

👉 Default index starts from 0.

You can customize the index:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   s = pd.Series([10, 20, 30], index=['A', 'B', 'C'])   `

#### 🔸 DataFrame

A two-dimensional, tabular data structure — similar to an Excel sheet or SQL table.

Creating a DataFrame from a dictionary:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   data = {      'Name': ['Ayaan', 'Ravi', 'Neha'],      'Age': [31, 25, 28],      'City': ['Lucknow', 'Delhi', 'Mumbai']  }  df = pd.DataFrame(data)  print(df)   `

Output:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML    `Name  Age     City  0  Ayaan   31  Lucknow  1   Ravi   25    Delhi  2   Neha   28   Mumbai`

### 🧩 **2\. Creating DataFrames from Different Sources**

SourceFunctionExampleDictionarypd.DataFrame()pd.DataFrame(data)List of listspd.DataFrame(list)pd.DataFrame(\[\[1,2\],\[3,4\]\])CSV filepd.read\_csv()pd.read\_csv('data.csv')Excel filepd.read\_excel()pd.read\_excel('data.xlsx')

### 📋 **3\. Basic DataFrame Operations**

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   df.head()         # View first 5 rows  df.tail(3)        # View last 3 rows  df.info()         # Get column names, types, null counts  df.describe()     # Summary statistics (mean, std, etc.)  df.shape          # (rows, columns)  df.columns        # List of column names  df.dtypes         # Data types of each column   `

### 🔍 **4\. Accessing Data**

#### Select one column:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   df['Name']   `

#### Select multiple columns:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   df[['Name', 'City']]   `

#### Select rows by index:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   df.loc[0]        # Label-based  df.iloc[1]       # Position-based   `

### 🧮 **5\. Adding & Deleting Columns**

#### Add new column:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   df['Country'] = 'India'   `

#### Delete column:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   df.drop('Age', axis=1, inplace=True)   `

### 🧰 **6\. Exporting Data**

Save your DataFrame for reuse:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   df.to_csv('output.csv', index=False)  df.to_excel('output.xlsx', index=False)   `

🧾 **Quick Summary**
--------------------

ConceptDescription**Series**1D labeled data**DataFrame**2D table with rows and columns**Read CSV/Excel**pd.read\_csv(), pd.read\_excel()**Inspect data**.head(), .info(), .describe()**Select data**.loc\[\], .iloc\[\], column names**Save data**.to\_csv(), .to\_excel()

🧩 **Pandas Chapter 1 — Practice Sheet**
========================================

Try these hands-on exercises in your Jupyter Notebook or VS Code:

### **🧠 Basic Exercises**

**Q1.** Import Pandas and create a Series of your 5 favorite numbers.**Q2.** Create a Series with index labels: A, B, C, D, E.**Q3.** Create a DataFrame with columns:

*   Name
    
*   Age
    
*   City
    
*   Profession
    

and fill with at least 4 sample rows.

**Q4.** Load the following dictionary into a DataFrame:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   data = {      'Product': ['Laptop', 'Tablet', 'Phone'],      'Price': [70000, 25000, 40000],      'Stock': [50, 80, 150]  }   `

**Q5.** Display:

*   First 2 rows
    
*   Info about the DataFrame
    
*   Data types of all columns
    

### **⚙️ Intermediate Exercises**

**Q6.** Add a new column Discount = 10% of Price.**Q7.** Delete the Stock column.**Q8.** Rename Price → UnitPrice.**Q9.** Display only Product and UnitPrice columns.**Q10.** Export your DataFrame to products.csv.

### **💡 Challenge Question**

Read the products.csv file you just saved, and:

1.  Display all rows where UnitPrice > 30000.
    
2.  Count how many rows satisfy this condition.
    
3.  Print only the Product names that meet it.
