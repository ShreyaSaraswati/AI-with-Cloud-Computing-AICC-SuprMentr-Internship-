# Task 13 – Logistic Regression Threshold Tuning
Date: 23-03-2026

---

## Problem Statement
Use Logistic Regression on Breast Cancer dataset and evaluate model performance using different probability thresholds.

Steps:
1. Load Breast Cancer dataset
2. Train Logistic Regression model
3. Predict probabilities
4. Apply different thresholds (0.3, 0.5, 0.7)
5. Calculate Accuracy, Precision, Recall
6. Identify best threshold for cancer detection

---

## Code 

```python
from sklearn.datasets import load_breast_cancer
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, precision_score, recall_score

# Step 1: Load dataset
data = load_breast_cancer()
X = data.data
y = data.target

# Step 2: Train model
model = LogisticRegression(max_iter=5000)
model.fit(X, y)

# Step 3: Predict probabilities
probs = model.predict_proba(X)[:, 1]

# Step 4: Test different thresholds
thresholds = [0.3, 0.5, 0.7]

print("Threshold | Accuracy | Precision | Recall")
print("------------------------------------------")

for t in thresholds:
    preds = (probs >= t).astype(int)

    acc = accuracy_score(y, preds)
    prec = precision_score(y, preds)
    rec = recall_score(y, preds)

    print(f"{t}       | {acc:.2f}     | {prec:.2f}      | {rec:.2f}")
```

---

## Output

| Threshold | Accuracy | Precision | Recall |
|----------:|---------:|----------:|-------:|
| 0.3 | 0.95 | 0.94 | 0.99 |
| 0.5 | 0.96 | 0.96 | 0.97 |
| 0.7 | 0.94 | 0.98 | 0.92 |
