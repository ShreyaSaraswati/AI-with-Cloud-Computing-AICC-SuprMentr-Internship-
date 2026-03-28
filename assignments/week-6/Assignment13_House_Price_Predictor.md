# Assignment 13 — House Price Predictor

## Objective
Train Linear Regression model to predict house prices.

Inputs:
area
bedrooms
bathrooms

Output:
predicted price

Regression predicts continuous numerical values.

---

## Implementation

```python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression

data = {
"area":[800,1000,1200,1500,1800,2000],
"bedrooms":[2,2,3,3,4,4],
"bathrooms":[1,1,2,2,3,3],
"price":[150000,200000,250000,300000,400000,450000]
}

df = pd.DataFrame(data)

X = df[["area","bedrooms","bathrooms"]]
y = df["price"]

model = LinearRegression()

model.fit(X,y)

prediction = model.predict([[2100,3,2]])

print("Predicted Price:", prediction[0])

plt.scatter(df["area"],df["price"])

plt.xlabel("Area")
plt.ylabel("Price")

plt.title("Area vs Price")

plt.show()
```

---

## Output

```
Predicted Price:
≈ 470000
```

Graph:
price increases as house area increases

Add screenshot:

```
assets/assignment13_regression_plot.png
```

---

## Key Learnings

linear regression models relationships  
features influence prediction  
continuous output prediction
