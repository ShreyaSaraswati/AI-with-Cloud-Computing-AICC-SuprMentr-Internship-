# Assignment 12 — KNN in Real Life

## Objective
Understand how recommendation systems work using K-Nearest Neighbors (KNN).

KNN predicts output based on similarity between users or items.

Common applications:
Netflix
Amazon
Spotify

KNN is a supervised learning algorithm that predicts values based on nearest data points. :contentReference[oaicite:0]{index=0}

---

## Implementation

```python
import numpy as np
from sklearn.neighbors import NearestNeighbors

ratings = np.array([
[5,3,0,1],
[4,0,0,1],
[1,1,0,5],
[0,0,5,4],
[0,1,5,4]
])

model = NearestNeighbors(n_neighbors=2, metric="cosine")

model.fit(ratings)

new_user = np.array([[5,4,0,0]])

distances, indices = model.kneighbors(new_user)

print("Similar Users:", indices)

similar_users = ratings[indices[0]]

scores = similar_users.mean(axis=0)

movies=["Action","Comedy","Drama","Sci-Fi"]

recommended_movie = movies[np.argmax(scores)]

print("Recommended Movie:", recommended_movie)
```

---

## Output

```
Similar Users: [[0 1]]

Recommended Movie: Action
```

---

## Insight

users with similar preferences receive similar recommendations  
distance metrics determine similarity  
widely used in recommender systems

