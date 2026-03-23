# Assignment 01 – Password Authentication

## Problem Statement
Create a strong password authentication system using Python.

Requirements:
- Minimum 6 characters
- Must include uppercase letter
- Must include lowercase letter
- Must include number
- User gets 3 login attempts

---

## Code

```python
import re

def check_password_strength(password):
    if len(password) < 6:
        return False, "Password must be at least 6 characters long."
    if not re.search("[A-Z]", password):
        return False, "Password must contain at least one uppercase letter."
    if not re.search("[a-z]", password):
        return False, "Password must contain at least one lowercase letter."
    if not re.search("[0-9]", password):
        return False, "Password must contain at least one number."
    return True, "Password is strong."

while True:
    password = input("Create a password: ")
    valid, message = check_password_strength(password)
    print(message)
    if valid:
        break

print("\nPassword created successfully!\n")

attempts = 3
while attempts > 0:
    login = input("Enter your password to login: ")

    if login == password:
        print("Login successful! ")
        break
    else:
        attempts -= 1
        print(f"Incorrect password. Attempts left: {attempts}")

if attempts == 0:
    print("Account locked. Too many failed attempts.")
```

---

## Output

```
Create a password: He@#$%123
Password is strong.

Password created successfully!

Enter your password to login: He@#$%123
Login successful! 
```

---

## Concepts Used
- Python
- Regex
- Conditions
- Loops
