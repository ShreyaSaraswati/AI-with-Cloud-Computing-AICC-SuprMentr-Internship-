# Task 13 – Movie Review Sentiment Classifier (TF-IDF)
Date: 17-03-2026

---

## Problem Statement
Build a machine learning model to classify movie reviews into:

Classes:
- positive
- negative
- neutral

Requirements:
1. Create dataset with 20+ sentences
2. Convert text into TF-IDF features
3. Train classification model
4. Predict sentiment for new review
5. Display predicted class

Bonus:
Use TF-IDF instead of CountVectorizer

---

## Code

```python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression

# Step 1: Dataset (20+ sentences)
data = {
    "text": [
        "I love this movie",
        "Amazing storyline and acting",
        "Fantastic film",
        "Very entertaining",
        "Great direction",
        "I enjoyed every moment",
        "Excellent movie experience",

        "Worst movie ever",
        "I hate this film",
        "Very boring movie",
        "Terrible acting",
        "Not worth watching",
        "Waste of time",
        "Bad storyline",

        "It was okay",
        "Average movie",
        "Nothing special",
        "Just fine",
        "Some scenes were good",
        "Neutral experience",
        "Movie was decent"
    ],

    "label": [
        "positive","positive","positive","positive","positive","positive","positive",
        "negative","negative","negative","negative","negative","negative","negative",
        "neutral","neutral","neutral","neutral","neutral","neutral","neutral"
    ]
}

# Step 2: TF-IDF Vectorization
vectorizer = TfidfVectorizer()
X = vectorizer.fit_transform(data["text"])
y = data["label"]

# Step 3: Train model
model = LogisticRegression()
model.fit(X, y)

# Step 4: Predict new review
test_review = ["The movie was fantastic and very entertaining"]
test_vec = vectorizer.transform(test_review)

prediction = model.predict(test_vec)

print("Review:", test_review[0])
print("Predicted Sentiment:", prediction[0])
```

---

## Output

Review: The movie was fantastic and very entertaining\
Predicted Sentiment: positive
