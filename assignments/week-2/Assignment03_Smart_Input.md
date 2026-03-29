# Assignment 03 – Smart Input Program
Date: 12-02-2026

---

## Problem Statement
Create a Python program that takes name, age, and hobby as input.
Display a personalized message and categorize age using conditional statements.

---

## Code
```python
# Smart Input Program

# Taking user input
name = input("Enter your name: ")
age = int(input("Enter your age: "))
hobby = input("Enter your hobby: ")

# Categorizing age using conditionals
if age < 13:
    category = "a Child"
elif age < 20:
    category = "a Teenager"
elif age < 60:
    category = "an Adult"
else:
    category = "a Senior"

# Displaying personalized message
print("\n--- Personalized Message ---")
print(f"Hello {name}!")
print(f"You are {category}.")
print(f"It's great that you enjoy {hobby}!")
```

---

## Output
```
Enter your name: Sam 
Enter your age: 20
Enter your hobby: Reading

--- Personalized Message ---
Hello Sam!
You are an Adult.
It's great that you enjoy Reading!
```

---

## Concepts Used
- User Input
- Variables
- Conditional Statements (if-elif-else)
- Data Types (int, string)
- Formatted Output (f-strings)
- Basic Python Programming

---

## Learning Outcome
- Learned how to take multiple inputs from user
- Learned how to convert input datatype using int()
- Learned how conditional statements work
- Learned how to create personalized output
- Understood how logic can categorize data

---

## Conclusion
This program demonstrates how user input can be processed using conditional statements to produce personalized output. It shows how Python can be used to build interactive programs.
