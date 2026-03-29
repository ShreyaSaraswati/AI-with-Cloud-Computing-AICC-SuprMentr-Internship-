# Task 11 – NLP Preprocessing with Lemmatization 
Date: 13-03-2026

---

## Problem Statement
Perform advanced NLP preprocessing on text:

Steps to perform:
1. Convert text to lowercase
2. Remove punctuation
3. Tokenize text
4. Remove stopwords
5. Apply lemmatization
6. Convert text into TF-IDF features
7. Display processed text and TF-IDF values

---

## Code

```python
import string
import nltk
from nltk.corpus import stopwords
from nltk.stem import WordNetLemmatizer
from nltk.tokenize import word_tokenize
from sklearn.feature_extraction.text import TfidfVectorizer

# Download resources (run once)
nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('stopwords')
nltk.download('wordnet')

# Sample text
text = "I am learning NLP and it is very exciting. NLP helps computers understand human language."

# Step 1: lowercase
text = text.lower()

# Step 2: remove punctuation
text = text.translate(str.maketrans('', '', string.punctuation))

# Step 3: tokenization
tokens = word_tokenize(text)

# Step 4: remove stopwords
stop_words = set(stopwords.words('english'))
tokens = [word for word in tokens if word not in stop_words]

# Step 5: lemmatization
lemmatizer = WordNetLemmatizer()
lemmatized = [lemmatizer.lemmatize(word) for word in tokens]

processed_text = " ".join(lemmatized)

print("Processed Text:", processed_text)

# Step 6: TF-IDF
vectorizer = TfidfVectorizer()
tfidf_matrix = vectorizer.fit_transform([processed_text])

# Step 7: Display TF-IDF values
tfidf_df = dict(zip(vectorizer.get_feature_names_out(), tfidf_matrix.toarray()[0]))

print("\nTF-IDF Values:")
for word, score in tfidf_df.items():
    print(word, ":", round(score, 3))
```
---

## Output

**Processed Text:** learning nlp exciting nlp help computer understand human language

**TF-IDF Values:**\
computer : 0.316\
exciting : 0.316\
help : 0.316\
human : 0.316\
language : 0.316\
learning : 0.316\
nlp : 0.632\
understand : 0.316
