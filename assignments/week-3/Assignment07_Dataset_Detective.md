# Assignment 07 – Dataset Detective

## Problem Statement
Load dataset and:
- display top rows
- dataset shape
- highest value column
- missing values
- 5 insights

---

## Code

```python
import pandas as pd

url="https://raw.githubusercontent.com/Opensourcefordatascience/Data-sets/master/admission.csv"

df=pd.read_csv(url)

print(df.head())

print(df.shape)

print(df.isnull().sum())

print(df.describe())
```

---

## Insights

Dataset has 400 rows  
GRE has highest value  
No missing values  
Average GPA ~3.38  
Rank ranges 1–4

---

## Concepts Used

Pandas  
Data Analysis  
Statistics
