# Assignment 14 – Spam Classifier Thinking

## Problem Statement
Design a spam detection system conceptually and implement a simple Machine Learning model.

Email systems must automatically classify messages as:
- Spam
- Not Spam (Ham)

Spam classification is a supervised learning problem where the model learns from labeled examples.

---

Email platforms need automatic filtering systems to detect unwanted messages such as promotional content, scams, or phishing emails.

Goal:
Classify incoming messages into:
- Spam
- Not Spam

---

## Possible Features (Input Variables)
These features help the model detect spam patterns:

- Word frequency (common spam words)
- Presence of promotional keywords
- Message length
- Use of capital letters
- Special characters (!, $, %)
- Suspicious links
- Repeated words

Example spam keywords:
```
free
win
offer
discount
prize
click
```

---

## Dataset Requirement
Dataset must contain labeled messages.

Example:

| Message | Label |
|--------|------|
| Win free iPhone | Spam |
| Meeting at 5pm | Not Spam |
| Claim your prize | Spam |
| Project discussion tomorrow | Not Spam |

Labels:
- Spam = unwanted message
- Ham = normal message

---

## Possible Errors

### False Positive
Normal email incorrectly classified as spam.

Example:
Meeting reminder classified as spam.

### False Negative
Spam email not detected.

Example:
Promotional message classified as normal email.

Both errors affect user experience and system reliability.

---

## Code Implementation
```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.naive_bayes import MultinomialNB
from sklearn.metrics import accuracy_score, classification_report

# Create dataset
spam_messages = [
"Win a free iPhone now",
"Claim your prize money",
"Congratulations you won lottery",
"Limited time offer click now",
"Earn money fast online",
"Free gift card available",
"Exclusive offer just for you",
"Get rich quick scheme",
"Click here to claim reward",
"Congratulations you won cash"
]*5

ham_messages = [
"Meeting at 10 am tomorrow",
"Let's have lunch today",
"Project meeting reminder",
"Please review the document",
"Team meeting at office",
"Submit the assignment today",
"Call me when you are free",
"Let's discuss the project",
"Your appointment is confirmed",
"Don't forget the meeting"
]*5

messages = spam_messages + ham_messages
labels = ["spam"]*50 + ["ham"]*50

df = pd.DataFrame({
    "message": messages,
    "label": labels
})

# Convert labels to numeric
df["label_num"] = df.label.map({"ham":0, "spam":1})

X = df["message"]
y = df["label_num"]

# Convert text to numerical format
vectorizer = TfidfVectorizer()
X_vectorized = vectorizer.fit_transform(X)

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(
    X_vectorized, y, test_size=0.2, random_state=42
)

# Train model
model = MultinomialNB()
model.fit(X_train, y_train)

# Predictions
predictions = model.predict(X_test)

# Evaluation
print("Accuracy:", accuracy_score(y_test, predictions))
print(classification_report(y_test, predictions, zero_division=0))

# Test new message
new_message = ["You won free tickets click here"]

new_vector = vectorizer.transform(new_message)

prediction = model.predict(new_vector)

if prediction[0] == 1:
    print("Spam Message")
else:
    print("Not Spam")
```

---

## Output
```
Accuracy: 1.0

precision    recall  f1-score   support

0       1.00      1.00      1.00
1       1.00      1.00      1.00

Spam Message
```

---

## Concepts Used
- Text Classification
- Natural Language Processing (NLP)
- TF-IDF Vectorization
- Naive Bayes Algorithm
- Supervised Learning
- Feature Engineering
- Model Evaluation

---

## Key Learnings
- Classification models require labeled datasets
- Feature selection impacts model accuracy
- Text must be converted into numerical format
- Evaluation metrics help measure model performance
- Spam filtering is widely used in real-world email systems

---

## Conclusion
Spam detection systems use Machine Learning to automatically classify messages. Proper feature engineering and labeled data help improve accuracy and reduce errors such as false positives and false negatives.
