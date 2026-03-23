# Assignment 11 — Build Your First Dataset

## Objective
Create a simple dataset and identify:
- feature (input variable)
- label (output variable)
- relationship between variables

Understanding dataset structure is fundamental to Machine Learning workflows.

---

## Dataset

| Study Hours | Marks |
|------------|------|
| 1 | 40 |
| 2 | 45 |
| 3 | 50 |
| 4 | 55 |
| 5 | 65 |
| 6 | 70 |
| 7 | 75 |
| 8 | 85 |
| 9 | 90 |
| 10 | 95 |

Feature:
Study_Hours

Label:
Marks

---

## Implementation

```python
import pandas as pd
import matplotlib.pyplot as plt

data = {
    "Study_Hours":[1,2,3,4,5,6,7,8,9,10],
    "Marks":[40,45,50,55,65,70,75,85,90,95]
}

df = pd.DataFrame(data)

print(df)

plt.scatter(df["Study_Hours"], df["Marks"])

plt.xlabel("Study Hours")
plt.ylabel("Marks")

plt.title("Study Hours vs Marks")

plt.show()
```

---

## Output

```
   Study_Hours  Marks
0            1     40
1            2     45
...
9           10     95
```

Graph Insight:
Strong positive correlation between study hours and marks.

Add screenshot:

```
assets/assignment11_scatter.png
```

---

## Key Learnings

structured datasets contain features and labels  
visualization helps understand relationships  
foundation for regression models
