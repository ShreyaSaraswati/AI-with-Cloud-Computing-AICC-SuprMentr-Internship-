# Assignment 01

```md id="a1md"
# Assignment 01 – Password Authentication
📅 Date: 07-02-2026

## Problem Statement
Create a strong password authentication system using Python.

Password must:
- contain uppercase letter
- contain lowercase letter
- contain number
- be at least 6 characters long

User gets 3 login attempts.

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
        print("Login successful! ✅")
        break
    else:
        attempts -= 1
        print(f"Incorrect password. Attempts left: {attempts}")

if attempts == 0:
    print("Account locked.")
