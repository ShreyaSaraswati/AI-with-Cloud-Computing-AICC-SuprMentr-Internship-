# Assignment 15 — Decision Tree Classification

## Objective
Build a Decision Tree model to predict whether a person should play outside based on weather conditions.

Decision Trees are supervised learning algorithms used for classification and regression tasks.

They work by splitting data into branches based on feature values.

---

## Dataset

| Weather | Temperature | Humidity | Wind | PlayOutside |
|--------|------------|---------|------|------------|
| Sunny | Hot | High | Weak | No |
| Sunny | Hot | High | Strong | No |
| Overcast | Hot | High | Weak | Yes |
| Rain | Mild | High | Weak | Yes |
| Rain | Cool | Normal | Weak | Yes |
| Rain | Cool | Normal | Strong | No |
| Overcast | Mild | Normal | Strong | Yes |
| Sunny | Cool | High | Weak | No |

---

## Implementation

```python
import pandas as pd
from sklearn.tree import DecisionTreeClassifier, plot_tree
import matplotlib.pyplot as plt

data = {
'Weather':['Sunny','Sunny','Overcast','Rain','Rain','Rain','Overcast','Sunny'],
'Temperature':['Hot','Hot','Hot','Mild','Cool','Cool','Mild','Cool'],
'Humidity':['High','High','High','High','Normal','Normal','Normal','High'],
'Wind':['Weak','Strong','Weak','Weak','Weak','Strong','Strong','Weak'],
'PlayOutside':['No','No','Yes','Yes','Yes','No','Yes','No']
}

df = pd.DataFrame(data)

X = pd.get_dummies(df.drop("PlayOutside",axis=1))

y = df["PlayOutside"]

model = DecisionTreeClassifier()

model.fit(X,y)

plt.figure(figsize=(12,8))

plot_tree(
model,
feature_names=X.columns,
class_names=model.classes_,
filled=True
)

plt.title("Decision Tree")

plt.show()
```

---

## Output

Decision Tree visualization showing rules used for prediction.

Example rule:

if Weather = Overcast → PlayOutside = Yes

if Weather = Sunny and Humidity = High → PlayOutside = No

Add screenshot:

```
assets/assignment15_decision_tree.png
```

---

## How Decision Tree Works

model splits data based on feature importance  
each node represents a decision condition  
leaf nodes represent final prediction  

---

## Key Learnings

Decision Trees are interpretable models  
useful for classification problems  
help understand decision logic visually  

---

## Concepts Used

Decision Tree  
Classification  
Feature Encoding  
Model Visualization
