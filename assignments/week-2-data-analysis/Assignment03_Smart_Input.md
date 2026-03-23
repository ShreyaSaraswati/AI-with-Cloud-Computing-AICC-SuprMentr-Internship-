# Assignment 03 – Smart Input Program

## Problem Statement
Create a Python program that takes name, age, and hobby as input.  
Display a personalized message and categorize age using conditions.

---

## Code

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
hobby = input("Enter your hobby: ")

if age < 13:
    category = "a Child"
elif age < 20:
    category = "a Teenager"
elif age < 60:
    category = "an Adult"
else:
    category = "a Senior"

print("\n--- Personalized Message ---")
print(f"Hello {name}!")
print(f"You are {category}.")
print(f"It's great that you enjoy {hobby}!")
```

---

## Output

```
Enter your name: Sam
Enter your age: 23
Enter your hobby: Reading

Hello Shreya!
You are an Adult.
It's great that you enjoy Reading!
```

---

## Concepts Used

User Input  
Conditional Statements  
Variables  
Formatted Output
