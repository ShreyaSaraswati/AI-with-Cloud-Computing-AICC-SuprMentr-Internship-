# Assignment 15 — Customer Segmentation using KMeans

## Objective
Group customers based on behavior using clustering.

Clustering finds patterns in unlabeled data.

KMeans groups data points based on similarity.

---

## Implementation

```python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
import numpy as np

data = pd.DataFrame({
"income":np.random.randint(20,150,200),
"score":np.random.randint(1,100,200)
})

X=data[["income","score"]]

kmeans=KMeans(n_clusters=5, random_state=42)

clusters=kmeans.fit_predict(X)

plt.scatter(X["income"],X["score"])

plt.scatter(
kmeans.cluster_centers_[:,0],
kmeans.cluster_centers_[:,1]
)

plt.xlabel("Income")
plt.ylabel("Spending Score")
plt.title("Customer Segments")

plt.show()
```

---

## Output

Graph shows 5 clusters of customers.

Add screenshot:

```
assets/assignment15_clusters.png
```

---

## Business Insight

high income high spending → premium customers  
low income high spending → impulsive buyers  
low income low spending → budget customers  

---

## Key Learnings

unsupervised learning finds hidden patterns  
clustering useful for marketing strategy
