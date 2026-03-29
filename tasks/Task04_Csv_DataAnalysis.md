# Task 04 – Student Marks Analysis
Date: 14-02-2026

---

## Problem Statement
1. Read a CSV file containing `Name, Maths, Science, English`  
2. Handle missing values (if any)  
3. Add a new column `Total` (sum of all subjects)  
4. Add a column `Average`  
5. Find top 3 students based on total marks  
6. Calculate department-wise average marks  
7. List students scoring above 75 in all subjects

---

## CSV dataset 
| Name    | Maths | Science | English |
|---------|-------|---------|---------|
| Alice   | 80    | 70      | 90      |
| Bob     | 65    | 85      | 78      |
| Charlie | 90    | 95      | 88      |
| David   | 55    | 60      | 65      |
| Eva     | 82    | 78      | 88      |
| Frank   | 88    | -       | 92      |

---

## Code
```python
import pandas as pd
import numpy as np

# Read CSV file
df = pd.read_csv("students.csv")

# Handle missing values by filling with average of the column
df['Maths'].fillna(df['Maths'].mean(), inplace=True)
df['Science'].fillna(df['Science'].mean(), inplace=True)
df['English'].fillna(df['English'].mean(), inplace=True)

# Add Total and Average columns
df['Total'] = df[['Maths', 'Science', 'English']].sum(axis=1)
df['Average'] = df[['Maths', 'Science', 'English']].mean(axis=1)

# Top 3 students based on Total
top_3 = df.nlargest(3, 'Total')

# Department-wise average (mean of all students per subject)
dept_avg = df[['Maths', 'Science', 'English']].mean()

# Students scoring above 75 in all subjects
above_75 = df[(df['Maths'] > 75) & (df['Science'] > 75) & (df['English'] > 75)]

print("Complete DataFrame:\n", df)
print("\nTop 3 Students based on Total:\n", top_3)
print("\nDepartment-wise Average Marks:\n", dept_avg)
print("\nStudents scoring above 75 in all subjects:\n", above_75)
```

## Output:
**Complete DataFrame:**
| Name    | Maths | Science | English | Total  | Average |
|---------|-------|---------|---------|--------|---------|
| Alice   | 80.0  | 70.0    | 90      | 240.0  | 80.0    |
| Bob     | 65.0  | 85.0    | 78      | 228.0  | 76.0    |
| Charlie | 90.0  | 95.0    | 88      | 273.0  | 91.0    |
| David   | 55.0  | 60.0    | 65      | 180.0  | 60.0    |
| Eva     | 82.0  | 78.0    | 88      | 248.0  | 82.7    |
| Frank   | 88.0  | 77.6    | 92      | 257.6  | 85.9    |

**Top 3 Students based on Total:**
| Name    | Maths | Science | English | Total  | Average |
|---------|-------|---------|---------|--------|---------|
| Charlie | 90.0  | 95.0    | 88      | 273.0  | 91.0    |
| Frank   | 88.0  | 77.6    | 92      | 257.6  | 85.9    |
| Eva     | 82.0  | 78.0    | 88      | 248.0  | 82.7    |


**Department-wise Average Marks:**
| Subject | Average |
|---------|---------|
| Maths   | 76.67   |
| Science | 77.92   |
| English | 83.50   |

**Students scoring above 75 in all subjects:**
| Name    | Maths | Science | English | Total  | Average |
|---------|-------|---------|---------|--------|---------|
| Alice   | 80.0  | 70.0    | 90      | 240.0  | 80.0    |
| Charlie | 90.0  | 95.0    | 88      | 273.0  | 91.0    |
| Eva     | 82.0  | 78.0    | 88      | 248.0  | 82.7    |
| Frank   | 88.0  | 77.6    | 92      | 257.6  | 85.9    |
