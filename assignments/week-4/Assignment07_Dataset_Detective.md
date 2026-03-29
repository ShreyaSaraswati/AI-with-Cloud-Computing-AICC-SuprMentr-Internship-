# Assignment 07 – Dataset Detective
Date: 24-02-2026

---

## Problem Statement
Load a dataset using Pandas and perform basic data analysis.

Tasks performed:
- Display top rows of dataset
- Find dataset shape (rows and columns)
- Identify column with highest value
- Count missing values
- Generate 5 data insights

---

## Code
```python
# Dataset Detective

import pandas as pd
import numpy as np

# Loading dataset
url = "https://raw.githubusercontent.com/Opensourcefordatascience/Data-sets/master/admission.csv"
df = pd.read_csv(url)

print("Dataset Loaded Successfully!\n")

# Display top rows
print("Top 5 Rows of Dataset:")
print(df.head())

# Dataset shape
print("\nDataset Shape (Rows, Columns):", df.shape)

# Finding column with highest value
numeric_cols = df.select_dtypes(include=[np.number])
max_values = numeric_cols.max()

highest_column = max_values.idxmax()
highest_value = max_values.max()

print("\nColumn with Highest Single Value:")
print("Column Name:", highest_column)
print("Highest Value:", highest_value)

# Checking missing values
print("\nMissing Values in Each Column:")
print(df.isnull().sum())

total_missing = df.isnull().sum().sum()
print("Total Missing Values in Dataset:", total_missing)

# Insights
print("\n==============================")
print("FIVE DATA INSIGHTS")
print("==============================")

print("1. Dataset contains", df.shape[0], "rows and", df.shape[1], "columns.")

print("2. Column with highest overall value is:", highest_column)

print("3. Average values of numerical columns:\n")
print(numeric_cols.mean())

print("4. Total missing values in dataset:", total_missing)

print("5. Dataset summary statistics:\n")
print(df.describe())
```

---

## Output
```
Dataset Loaded Successfully!

Top 5 Rows of Dataset:
   admit    gre   gpa  rank
0    0.0  380.0  3.61   3.0
1    1.0  660.0  3.67   3.0
2    1.0  800.0  4.00   1.0
3    1.0  640.0  3.19   4.0
4    0.0  520.0  2.93   4.0

Dataset Shape (Rows, Columns): (400, 4)

Column with Highest Single Value:
Column Name: gre
Highest Value: 800.0

Missing Values in Each Column:
admit    0
gre      0
gpa      0
rank     0
dtype: int64

Total Missing Values in Dataset: 0

==============================
FIVE DATA INSIGHTS
==============================
1. Dataset contains 400 rows and 4 columns.

2. Column with highest overall value is: gre

3. Average values of numerical columns:

admit      0.3175
gre      587.7000
gpa        3.3899
rank       2.4850
dtype: float64

4. Total missing values in dataset: 0

5. Dataset summary statistics:

            admit         gre         gpa       rank
count  400.000000  400.000000  400.000000  400.00000
mean     0.317500  587.700000    3.389900    2.48500
std      0.466087  115.516536    0.380567    0.94446
min      0.000000  220.000000    2.260000    1.00000
25%      0.000000  520.000000    3.130000    2.00000
50%      0.000000  580.000000    3.395000    2.00000
75%      1.000000  660.000000    3.670000    3.00000
max      1.000000  800.000000    4.000000    4.00000
```

---

## Concepts Used
- Pandas Library
- Data Analysis
- DataFrame
- Data Inspection
- Missing Value Detection
- Statistical Summary
- NumPy
- Python Programming

---

## Learning Outcome
- Learned how to load dataset using pandas
- Learned how to inspect dataset structure
- Learned how to detect missing values
- Learned how to analyze dataset statistics
- Understood importance of data exploration before model building

---

## Conclusion
This assignment demonstrates basic data analysis using Pandas. It helps understand dataset structure, detect missing values, and generate insights which are important steps in Machine Learning workflow.
