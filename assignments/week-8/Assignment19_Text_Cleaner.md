# Assignment 19 – Build a Text Cleaner

## Problem Statement
Write Python code to clean text by:

- removing punctuation
- converting text to lowercase
- removing stopwords

---

## Example Text
Original sentence:

This is a Sample sentence, with PUNCTUATION!

---

## Code

```python
import string

# list of stopwords
stopwords = ["is","a","the","and","to","in","of","for"]

# input text
text = "This is a Sample sentence, with PUNCTUATION!"

# convert to lowercase
text = text.lower()

# remove punctuation
text = text.translate(
    str.maketrans("", "", string.punctuation)
)

# split sentence into words
words = text.split()

# remove stopwords
filtered_words = [
    w for w in words
    if w not in stopwords
]

# join words into cleaned sentence
clean_text = " ".join(filtered_words)

print(clean_text)
```

---

## Output

sample sentence with punctuation

---

## Step-by-Step Explanation

### Convert to lowercase
Ensures consistency in text formatting.

Example:
Sample → sample

---

### Remove punctuation
Eliminates symbols that do not add meaning.

Example:
sentence, → sentence

---

### Remove stopwords
Stopwords are common words that do not carry significant meaning.

Examples of stopwords:
is, a, the, and, to, in, of, for

Removing them helps focus on important words.

---

### Tokenization
Splits sentence into individual words.

Example:
"sample sentence punctuation"
→ ["sample","sentence","punctuation"]

---

## Concepts Used
- Text preprocessing
- Stopwords removal
- String operations
- Natural Language Processing basics
- Tokenization
- Data cleaning

---

## Key Learnings
- Raw text data needs preprocessing before using in ML models
- Removing stopwords improves text quality
- Lowercase conversion ensures consistency
- Punctuation removal simplifies analysis
- Text cleaning is essential for NLP tasks

---

## Applications
Text cleaning is widely used in:

- Chatbots
- Sentiment analysis
- Spam detection
- Search engines
- Recommendation systems
- Text classification models

---

## Conclusion
Text cleaning improves the quality of textual data and helps Machine Learning models perform better. Preprocessing steps such as removing stopwords, punctuation, and standardizing text are fundamental in NLP workflows.
