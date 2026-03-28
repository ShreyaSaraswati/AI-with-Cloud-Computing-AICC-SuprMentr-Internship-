# Assignment 08 – Data Doctor

## Problem Statement
Clean dataset by:
- handling missing values
- removing duplicates
- standardizing text

Explain importance.

---

## Code

```python
import pandas as pd

data = {
"Name":["Alice","Bob","alice",None],
"Age":[25,30,None,22]
}

df=pd.DataFrame(data)

df["Name"]=df["Name"].fillna("Unknown")

df["Age"]=df["Age"].fillna(df["Age"].mean())

df["Name"]=df["Name"].str.lower()

df=df.drop_duplicates()

print(df)
```

---

## Why Cleaning Matters

Improves accuracy  
Removes errors  
Ensures reliable ML models

---

## Concepts Used

Data Cleaning  
Pandas  
Preprocessing
