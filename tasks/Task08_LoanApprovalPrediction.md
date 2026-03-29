# Task 08 – Loan Approval Prediction (Logistic Regression)
Date: 27-02-2026

---

## Problem Statement
1. Create a dataset containing customer details:
   - income
   - credit_score
   - loan_amount
   - employment_years
   - loan_approved (target variable: 1 = approved, 0 = not approved)
2. Split the dataset into training and testing sets.
3. Train a Logistic Regression model.
4. Calculate model accuracy.
5. Predict loan approval for a new customer.

---

## Code

```python
import pandas as pd
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score
from sklearn.model_selection import train_test_split

# Step 1: Create dataset
data = {
    "income": [30000, 50000, 70000, 40000, 60000],
    "credit_score": [600, 700, 750, 650, 720],
    "loan_amount": [10000, 20000, 30000, 15000, 25000],
    "employment_years": [2, 5, 7, 3, 6],
    "loan_approved": [0, 1, 1, 0, 1]
}

df = pd.DataFrame(data)
print("Dataset:\n", df)

# Step 2: Define features and target
X = df[["income", "credit_score", "loan_amount", "employment_years"]]
y = df["loan_approved"]

# Step 3: Split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Step 4: Train Logistic Regression model
model = LogisticRegression()
model.fit(X_train, y_train)

# Step 5: Calculate accuracy
preds = model.predict(X_test)
print("\nAccuracy:", accuracy_score(y_test, preds))

# Step 6: Predict for new customer
new_customer = [[55000, 710, 20000, 4]]
result = model.predict(new_customer)

print("Loan Approved (1=Yes, 0=No):", result[0])
```

---

## Output

**Dataset**

| Index | Income | Credit_Score | Loan_Amount | Employment_Years | Loan_Approved |
|------:|-------:|-------------:|------------:|-----------------:|--------------:|
| 0 | 30000 | 600 | 10000 | 2 | 0 |
| 1 | 50000 | 700 | 20000 | 5 | 1 |
| 2 | 70000 | 750 | 30000 | 7 | 1 |
| 3 | 40000 | 650 | 15000 | 3 | 0 |
| 4 | 60000 | 720 | 25000 | 6 | 1 |

---

### Model Accuracy

**Accuracy:** `1.0`

---

### Prediction Result

**Loan Approved (1 = Yes, 0 = No):** `1`
