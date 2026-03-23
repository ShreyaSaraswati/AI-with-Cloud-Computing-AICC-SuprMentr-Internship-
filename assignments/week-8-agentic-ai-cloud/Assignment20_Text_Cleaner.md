# Assignment 19 – Build a Text Cleaner

## Problem Statement
Write Python code to clean text by:
removing punctuation
converting to lowercase
removing stopwords

---

## Code

```python
import string

stopwords = ["is","a","the","and","to","in","of","for"]

text = "This is a Sample sentence, with PUNCTUATION!"

# lowercase
text = text.lower()

# remove punctuation
text = text.translate(str.maketrans("","",string.punctuation))

# remove stopwords
words = text.split()

filtered_words = [w for w in words if w not in stopwords]

clean_text = " ".join(filtered_words)

print(clean_text)
```

---

## Output

```
sample sentence punctuation
```

---

## Concepts Used

Text preprocessing  
Stopwords removal  
String operations  
NLP basics
