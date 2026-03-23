# Assignment 16 – Customer Segmentation

## Problem Statement
Perform K-Means clustering on a mall customer dataset and group customers based on similar characteristics.

Goal:
Identify different types of customers based on income and spending habits.

---

## Code

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Create sample dataset
data = pd.DataFrame({
    "Annual Income (k$)": np.random.randint(15,140,200),
    "Spending Score (1-100)": np.random.randint(1,100,200)
})

# Select features
X = data[["Annual Income (k$)","Spending Score (1-100)"]]

# Elbow Method
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i, random_state=42)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.title("Elbow Method")
plt.xlabel("Clusters")
plt.ylabel("WCSS")
plt.show()

# Apply KMeans
kmeans = KMeans(n_clusters=5, random_state=42)
clusters = kmeans.fit_predict(X)

# Plot clusters
plt.scatter(X.iloc[:,0], X.iloc[:,1])
plt.scatter(kmeans.cluster_centers_[:,0],
            kmeans.cluster_centers_[:,1])
plt.xlabel("Income")
plt.ylabel("Spending Score")
plt.title("Customer Segments")
plt.show()
```

---

## Customer Groups (Example Interpretation)

High income – high spending → premium customers  
Low income – high spending → impulsive buyers  
High income – low spending → careful spenders  
Low income – low spending → budget customers  

---

## Concepts Used

K-Means Clustering  
Unsupervised Learning  
Customer Segmentation  
Data Visualization
