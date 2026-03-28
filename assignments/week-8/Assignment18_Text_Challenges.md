# Assignment 18 – Text Challenges

## Description
Natural Language Processing (NLP) requires clean and structured text data.  
In real-world applications, text data often contains slang, emojis, spelling mistakes, and informal abbreviations.

The objective of this assignment is to collect messy text sentences, identify issues, and explain preprocessing techniques required before using the data in Machine Learning models.

---

## Problem Statement
Collect 20 messy sentences containing:
- slang words
- emojis
- spelling mistakes
- repeated letters
- short forms

Identify issues present in the sentences and describe preprocessing steps required to clean the data.

---

## Sample Sentences (Messy Text Data)

1. omg this movie is sooo gud!!!
2. lol that was funny 😂😂
3. i cant beleive this happened
4. brb going to clg
5. this food is amaaaazing
6. pls send notes asap
7. im sooo tired rn 😴
8. wat r u doing
9. this phone is gr8
10. idk what to do
11. thx for help
12. gud mrng everyone
13. meet me @ 5pm
14. ur work is awsm
15. im feeling happpy
16. c u soon
17. this is sooo cool 😎
18. msg me later
19. u did gr8 job
20. cant waitttt

---

## Issues Identified

### 1. Slang Words
Examples:
- omg → oh my god
- lol → laugh out loud
- idk → I do not know
- brb → be right back

Slang words reduce text clarity and consistency.

---

### 2. Emojis
Examples:
- 😂 😂
- 😎
- 😴

Emojis may contain sentiment information but must be handled properly.

---

### 3. Spelling Mistakes
Examples:
- beleive → believe
- gud → good
- happpy → happy

Spelling errors affect model accuracy.

---

### 4. Repeated Letters
Examples:
- sooo → so
- amaaaazing → amazing
- waitttt → wait

Repeated characters create inconsistent vocabulary.

---

### 5. Short Forms / Abbreviations
Examples:
- u → you
- ur → your
- msg → message
- clg → college

Short forms reduce readability.

---

### 6. Special Characters / Symbols
Examples:
- @
- !!!
- punctuation symbols

May not contribute useful meaning.

---

## Required Preprocessing Steps

### Convert text to lowercase
Ensures consistency across dataset.

Example:
OMG → omg

---

### Remove emojis
Emojis can be removed or converted into text sentiment labels.

Example:
😂 → happy emotion

---

### Correct spelling mistakes
Improves text clarity.

Example:
gud → good

---

### Remove punctuation
Removes unnecessary symbols.

Example:
movie!!! → movie

---

### Replace slang words
Convert informal words into standard language.

Example:
idk → I do not know

---

### Remove repeated letters
Standardizes vocabulary.

Example:
sooo → so

---

### Tokenization (optional)
Split sentence into individual words.

Example:
"this is cool" → ["this", "is", "cool"]

---

## Example Preprocessing Code

```python
import re

sentences = [
"omg this movie is sooo gud!!!",
"lol that was funny 😂😂",
"i cant beleive this happened"
]

def clean_text(text):

    text = text.lower()

    text = re.sub(r'[^\w\s]', '', text)

    text = re.sub(r'(.)\1+', r'\1\1', text)

    return text

for s in sentences:
    print(clean_text(s))
```

---

## Example Output

omg this movie is soo gud  
lol that was funny  
i cant beleive this happened  

---

## Concepts Used
- Text preprocessing
- Natural Language Processing (NLP)
- Data cleaning
- Regular Expressions
- Tokenization
- Feature preparation

---

## Key Learnings
- Raw text data is often noisy and unstructured
- Cleaning text improves model performance
- Standardization helps Machine Learning algorithms understand patterns
- NLP preprocessing is important before training models
- Handling slang and spelling improves dataset quality

---

## Conclusion
Text preprocessing is an essential step in Natural Language Processing workflows. Cleaning messy text improves accuracy, consistency, and model performance in applications such as chatbots, sentiment analysis, and spam detection.
