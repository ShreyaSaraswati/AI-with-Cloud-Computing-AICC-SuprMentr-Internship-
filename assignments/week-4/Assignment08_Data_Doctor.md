# Assignment 08 – Data Doctor
Date: 26-02-2026

---

## Problem Statement
Clean a dataset using Pandas by:

- Handling missing values
- Removing duplicate records
- Standardizing text format
- Explaining why data cleaning is important

---

## Code
```python
# Data Doctor

import pandas as pd

# Step 1: Create a Sample Dataset
data = {
    "Name": ["Alice", "Bob", "alice", "Charlie", None, "Bob"],
    "Age": [25, 30, 25, None, 22, 30],
    "City": ["New York", "Los Angeles", "new york", "Chicago", "Chicago", "Los Angeles"]
}

df = pd.DataFrame(data)

print("Original Dataset:")
print(df)

# Step 2: Check Missing Values
print("\nMissing values in each column:")
print(df.isnull().sum())

# Step 3: Handle Missing Values
df["Name"] = df["Name"].fillna("Unknown")
df["Age"] = df["Age"].fillna(df["Age"].mean())

# Step 4: Remove Duplicate Rows
df = df.drop_duplicates()

# Step 5: Standardize Text (convert to lowercase and remove spaces)
df["Name"] = df["Name"].str.lower().str.strip()
df["City"] = df["City"].str.lower().str.strip()

# Step 6: Display Cleaned Dataset
print("\nCleaned Dataset:")
print(df)

# Step 7: Explanation
print("\nWhy Data Cleaning Matters:")
print("Data cleaning improves data quality by handling missing values, removing duplicates, and standardizing text. Clean data ensures accurate analysis and better decision-making.")
```

---

## Output
```
Original Dataset:
      Name   Age         City
0    Alice  25.0     New York
1      Bob  30.0  Los Angeles
2    alice  25.0     new york
3  Charlie   NaN      Chicago
4     None  22.0      Chicago
5      Bob  30.0  Los Angeles

Missing values in each column:
Name    1
Age     1
City    0
dtype: int64

Cleaned Dataset:
      Name   Age         City
0    alice  25.0     new york
1      bob  30.0  los angeles
2    alice  25.0     new york
3  charlie  26.4      chicago
4  unknown  22.0      chicago

Why Data Cleaning Matters:
Data cleaning improves data quality by handling missing values, removing duplicates, and standardizing text. Clean data ensures accurate analysis and better decision-making.
```

---

## Concepts Used
- Data Cleaning
- Pandas Library
- Missing Value Handling
- Removing Duplicates
- Text Standardization
- Data Preprocessing
- Data Quality Improvement

---

## Learning Outcome
- Learned how to detect missing values in dataset
- Learned how to replace missing values using mean and default text
- Learned how to remove duplicate rows
- Learned how to standardize text format
- Understood importance of clean data before analysis or ML model training

---

## Conclusion
Data cleaning is an important step in Data Science and Machine Learning. Clean and consistent data improves accuracy, reduces errors, and ensures reliable model performance.
