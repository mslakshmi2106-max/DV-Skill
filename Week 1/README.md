# Sales Data Analysis using Python

## 📌 Project Overview

This project performs Exploratory Data Analysis (EDA) on the Sample Superstore dataset using Python. The goal is to analyze sales performance, understand category-wise sales, examine sales distribution, and calculate delivery times between order and shipment dates.

## 🎯 Objectives

* Load and explore the Superstore dataset.
* Convert date columns into proper datetime format.
* Calculate delivery days for each order.
* Check for missing values.
* Analyze total sales by category.
* Visualize sales trends using charts.

## 🛠 Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn

## 📂 Dataset

Dataset Used: **Sample Superstore**

File Name:
`samplesuperstore - samplesuperstore.csv`

## 📋 Steps Performed

### 1. Import Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load Dataset

```python
df = pd.read_csv("samplesuperstore - samplesuperstore.csv")
```

### 3. Explore Data

* View first few records
* Check data types
* Generate descriptive statistics

### 4. Data Preprocessing

* Convert `Order Date` and `Ship Date` to datetime format.
* Create a new column called `Delivery Days`.

```python
df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days
```

### 5. Data Cleaning

* Check for missing values.

```python
df.isnull().sum()
```

### 6. Sales Analysis

Calculate total sales for each category.

```python
category_sales = df.groupby('Category')['Sales'].sum()
```

### 7. Data Visualization

#### Sales by Category

Bar chart showing total sales for each product category.

#### Sales Distribution

Histogram displaying the distribution of sales values.

## 📊 Results

* Technology category generated significant sales.
* Sales values are unevenly distributed across orders.
* Delivery days can be analyzed to evaluate shipping efficiency.

## 🚀 How to Run

1. Clone the repository:

```bash
git clone <repository-url>
```

2. Install required libraries:

```bash
pip install pandas numpy matplotlib seaborn
```

3. Place the dataset file in the project folder.

4. Run the Python script:

```bash
python sales_analysis.py
```

## 📷 Sample Visualizations

* Sales by Category (Bar Chart)
* Sales Distribution (Histogram)

## 📈 Future Improvements

* Profit Analysis
* Regional Sales Analysis
* Customer Segment Analysis
* Interactive Dashboard using Power BI or Streamlit

## 👨‍💻 Author

Jonitha.P
BCA

## 📄 License

This project is created for educational and learning purposes.

# Sample Superstore Data Analysis

## Project Overview

This project performs an Exploratory Data Analysis (EDA) on the **Sample Superstore** dataset using Python. The objective is to analyze sales performance, profit trends, product categories, discounts, delivery times, and relationships between different business metrics.

The analysis helps identify key business insights that can support better decision-making and improve overall business performance.

---

# Objectives

The main objectives of this project are:

* Understand the structure of the Superstore dataset.
* Analyze sales and profit performance.
* Identify the best-performing product categories.
* Examine the relationship between discounts and profit.
* Calculate delivery time between order and shipment.
* Detect patterns, trends, and correlations within the data.
* Visualize important business metrics using graphs and charts.

---

# Technologies Used

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn

---

# Dataset Description

The Sample Superstore dataset contains retail sales information including:

* Order Details
* Customer Information
* Product Categories
* Sales
* Profit
* Discounts
* Shipping Information

### Important Columns

| Column Name | Description                 |
| ----------- | --------------------------- |
| Order Date  | Date when order was placed  |
| Ship Date   | Date when order was shipped |
| Category    | Product category            |
| Sales       | Revenue generated           |
| Profit      | Profit earned               |
| Discount    | Discount offered            |

---

# Steps Performed

## 1. Import Required Libraries

The following libraries are imported for data analysis and visualization:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### Purpose

* Pandas → Data manipulation
* NumPy → Numerical operations
* Matplotlib → Plotting charts
* Seaborn → Advanced visualizations

---

## 2. Load Dataset

The dataset is loaded using Pandas:

```python
df = pd.read_excel("samplesuperstore.xlsx")
```

### Purpose

* Reads the Excel dataset.
* Stores data in a DataFrame for analysis.

---

## 3. Display Initial Records

```python
df.head()
```

### Purpose

Displays the first few rows of the dataset to understand its structure.

---

## 4. Dataset Information

```python
df.info()
```

### Purpose

Provides:

* Number of rows and columns
* Data types
* Missing values
* Memory usage

---

## 5. Statistical Summary

```python
df.describe()
```

### Purpose

Generates descriptive statistics such as:

* Mean
* Median
* Standard deviation
* Minimum value
* Maximum value

---

## 6. Convert Date Columns

```python
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])
```

### Purpose

Converts date columns into proper datetime format for time-based calculations.

---

## 7. Calculate Delivery Days

```python
df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days
```

### Purpose

Creates a new column showing the number of days required for delivery.

### Business Benefit

Helps analyze shipping efficiency and customer service performance.

---

## 8. Explore Product Categories

```python
df['Category'].unique()
```

### Purpose

Displays all unique product categories available in the dataset.

Examples:

* Furniture
* Office Supplies
* Technology

---

## 9. Check Missing Values

```python
df.isnull().sum()
```

### Purpose

Identifies missing values in each column.

### Importance

Missing data can affect analysis accuracy and model performance.

---

# Sales Analysis

## Total Sales by Category

```python
category_sales = df.groupby('Category')['Sales'].sum()
```

### Purpose

Calculates total sales generated by each product category.

---

## Sales by Category Bar Chart

```python
category_sales.plot(kind='bar')
```

### Visualization

Shows which category contributes the most revenue.

### Insight

Management can focus on top-performing categories to maximize profits.

---

# Sales Distribution Analysis

## Histogram of Sales

```python
sns.histplot(df['Sales'], bins=30)
```

### Purpose

Analyzes the distribution of sales values.

### Insight

Helps determine:

* Common sales ranges
* Outliers
* Customer purchasing behavior

---

# Profit Analysis

## Profit by Category

```python
sns.barplot(
    data=df,
    x="Category",
    y="Profit"
)
```

### Purpose

Compares profit generated by each category.

### Business Value

Identifies categories that contribute the most profit.

---

## Sales Distribution by Category

```python
sns.barplot(
    data=df,
    x="Category",
    y="Sales"
)
```

### Purpose

Compares sales performance across categories.

---

# Profit Distribution

## Overall Profit Distribution

```python
sns.boxplot(
    data=df,
    y="Profit"
)
```

### Purpose

Detects:

* Median profit
* Outliers
* Profit variability

### Benefit

Helps identify unusually high or low-profit transactions.

---

## Profit Variation Across Categories

```python
sns.boxplot(
    data=df,
    x="Category",
    y="Profit"
)
```

### Purpose

Compares profit spread among categories.

### Insight

Shows which categories have stable or highly variable profits.

---

# Discount Analysis

## Unique Discount Values

```python
df["Discount"].unique()
```

### Purpose

Displays all discount percentages used in sales transactions.

---

## Impact of Discount on Profit

```python
sns.scatterplot(
    data=df,
    x="Discount",
    y="Profit"
)
```

### Purpose

Analyzes the relationship between discount and profit.

### Possible Insight

* Higher discounts may reduce profit.
* Some discounted products may still remain profitable.

---

# Correlation Analysis

## Select Numerical Columns

```python
numeric_df = df.select_dtypes(include="number")
```

### Purpose

Filters only numeric columns for correlation analysis.

---

## Correlation Matrix

```python
corr = numeric_df.corr()
```

### Purpose

Measures relationships between numerical variables.

Values range from:

* +1 → Strong Positive Correlation
* 0 → No Correlation
* -1 → Strong Negative Correlation

---

## Correlation Heatmap

```python
sns.heatmap(
    corr,
    annot=True
)
```

### Purpose

Visual representation of relationships between variables.

### Example Relationships

* Sales vs Profit
* Discount vs Profit
* Quantity vs Sales

### Benefit

Helps identify factors that influence business performance.

---

# Key Insights Generated

The analysis can help answer questions such as:

1. Which product category generates the highest sales?
2. Which category earns the highest profit?
3. How do discounts affect profitability?
4. What is the average delivery time?
5. Are there any outliers in profit data?
6. Which variables have strong correlations?

---

# Business Applications

This project can be used by:

### Retail Managers

To monitor sales and profitability.

### Marketing Teams

To evaluate discount strategies.

### Supply Chain Teams

To improve delivery performance.

### Business Analysts

To identify trends and support decision-making.

---

# Conclusion

This Superstore Data Analysis project demonstrates the use of Python for business analytics. By performing data cleaning, visualization, and correlation analysis, valuable insights can be extracted from retail data. The project highlights sales trends, profit patterns, discount impacts, and operational efficiency, enabling data-driven business decisions.

The analysis serves as a foundation for advanced analytics, predictive modeling, and business intelligence solutions.
