# Task 06 – Data Cleaning and Min-Max Scaling
Date: 16-02-2026

---

## Problem Statement
1. Create a dataset with columns:  
   - Age (with some missing values)  
   - Salary (with some missing values)  
   - City (mixed case values)  
   - Experience (with some duplicates)  
2. Remove duplicate rows  
3. Handle missing values  
4. Standardize city names to lowercase  
5. Apply Min-Max scaling on Age and Salary  
6. Display the final cleaned dataset

---

## Code
```python
import pandas as pd
from sklearn.preprocessing import MinMaxScaler

# Step 1: Create dataset
data = {
    "age": [25, 30, None, 35, 30],
    "salary": [50000, None, 60000, 70000, 50000],
    "city": ["hyderabad", "HYDERABAD", "Hyderabad", "delhi", "delhi"],
    "experience": [2, 3, 4, 5, 3]
}

df = pd.DataFrame(data)
print("Original Dataset:\n", df)

# Step 2: Remove duplicates
df.drop_duplicates(inplace=True)
print("\nAfter Removing Duplicates:\n", df)

# Step 3: Handle missing values (fill numeric columns with mean)
df["age"].fillna(df["age"].mean(), inplace=True)
df["salary"].fillna(df["salary"].mean(), inplace=True)

# Step 4: Standardize city names to lowercase
df["city"] = df["city"].str.lower()

# Step 5: Min-Max Scaling on Age and Salary
scaler = MinMaxScaler()
df[["age", "salary"]] = scaler.fit_transform(df[["age", "salary"]])

print("\nCleaned and Scaled Dataset:\n", df)
```
----

## Output

**Original Dataset:**
| age  | salary   | city       | experience |
|------|---------|------------|------------|
| 25.0 | 50000.0 | hyderabad  | 2          |
| 30.0 | NaN     | HYDERABAD  | 3          |
| NaN  | 60000.0 | Hyderabad  | 4          |
| 35.0 | 70000.0 | delhi      | 5          |
| 30.0 | 50000.0 | delhi      | 3          |

---

**After Removing Duplicates:**
| age  | salary   | city       | experience |
|------|---------|------------|------------|
| 25.0 | 50000.0 | hyderabad  | 2          |
| 30.0 | NaN     | HYDERABAD  | 3          |
| NaN  | 60000.0 | Hyderabad  | 4          |
| 35.0 | 70000.0 | delhi      | 5          |

---

**Cleaned and Scaled Dataset:**
| age       | salary    | city       | experience |
|-----------|----------|------------|------------|
| 0.000000  | 0.000000 | hyderabad  | 2          |
| 0.333333  | 0.333333 | hyderabad  | 3          |
| 0.250000  | 0.500000 | hyderabad  | 4          |
| 1.000000  | 1.000000 | delhi      | 5          |
