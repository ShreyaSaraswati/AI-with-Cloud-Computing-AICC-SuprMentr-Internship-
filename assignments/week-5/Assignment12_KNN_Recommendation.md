# Assignment 12 – KNN in Real Life
Date: 07-03-2026

---

## Problem Statement
Understand how recommendation systems work using the K-Nearest Neighbors (KNN) algorithm.

KNN predicts output based on similarity between users or items. It identifies the closest data points (neighbors) and uses them to make predictions.

Common applications:
- Movie recommendations
- Product suggestions
- Music recommendations

Platforms using similar techniques include Netflix, Amazon, and Spotify.

---

## Example Dataset

| User | Action | Comedy | Drama | Sci-Fi |
|------|-------|-------|------|-------|
| User 1 | 5 | 3 | 0 | 1 |
| User 2 | 4 | 0 | 0 | 1 |
| User 3 | 1 | 1 | 0 | 5 |
| User 4 | 0 | 0 | 5 | 4 |
| User 5 | 0 | 1 | 5 | 4 |

New user preferences:

| Action | Comedy | Drama | Sci-Fi |
|-------|-------|------|-------|
| 5 | 4 | 0 | 0 |

---

## Code
```python
import numpy as np
from sklearn.neighbors import NearestNeighbors

# Dataset (ratings given by users)
ratings = np.array([
    [5,3,0,1],
    [4,0,0,1],
    [1,1,0,5],
    [0,0,5,4],
    [0,1,5,4]
])

# KNN model
model = NearestNeighbors(n_neighbors=2, metric="cosine")

# Training model
model.fit(ratings)

# New user preferences
new_user = np.array([[5,4,0,0]])

# Finding similar users
distances, indices = model.kneighbors(new_user)

print("Similar Users:", indices)
print("Distances:", distances)

# Average rating from similar users
similar_users = ratings[indices[0]]

scores = similar_users.mean(axis=0)

# Movie categories
movies = ["Action","Comedy","Drama","Sci-Fi"]

# Recommended category
recommended_movie = movies[np.argmax(scores)]

print("Recommendation Scores:", scores)
print("Recommended Movie:", recommended_movie)
```

---

## Output
```
Similar Users: [[0 1]]

Distances: [[0.0232672  0.24244598]]

Recommendation Scores: [4.5 1.5 0.  1. ]

Recommended Movie: Action
```

---

## Observation
- Users with similar preferences receive similar recommendations
- KNN identifies closest users using distance metrics
- Cosine similarity helps measure how similar user preferences are
- Recommendations are based on average ratings of nearest neighbors

---

## Concepts Used
- K-Nearest Neighbors (KNN)
- Recommendation Systems
- Cosine Similarity
- Feature Similarity
- Supervised Learning
- NumPy
- Scikit-learn

---

## Learning Outcome
- Learned how recommendation systems work
- Understood concept of similarity between users
- Learned how KNN identifies nearest neighbors
- Understood importance of distance metrics
- Learned basic implementation of recommender system

---

## Conclusion
KNN is a simple yet powerful algorithm used in many real-world applications such as movie, music, and product recommendations. It works by identifying similar users or items and predicting preferences based on nearest neighbors.
