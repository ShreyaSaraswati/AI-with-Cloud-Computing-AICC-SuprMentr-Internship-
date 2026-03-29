# Task 01 – Basic Python Programs

---

## a. Check Even or Odd

**Problem Statement:**  
Write a Python program to check whether a given number is even or odd.

```python
num = int(input("Enter a number: "))
if num % 2 == 0:
    print(f"{num} is even")
else:
    print(f"{num} is odd")
```

**Output:**

Enter a number: 7\
7 is odd

---

## b. Print Numbers from 10 to 1

**Problem Statement:**
Write a Python program to print numbers from 10 down to 1.

```python
for i in range(10, 0, -1):
    print(i, end=" ")
print()
```

**Output:**

10\
9\
8\
7\
6\
5\
4\
3\
2\
1

---

# c. Sum Numbers Until User Enters 0

**Problem Statement:**
Write a Python program that keeps taking numbers from the user and calculates the sum. Stop when the user enters 0.

```python
total = 0
while True:
    num = int(input("Enter a number (0 to stop): "))
    if num == 0:
        break
    total += num

print(f"Total sum: {total}")
```

**Output:**

Enter a number (0 to stop): 3\
Enter a number (0 to stop): 5\
Enter a number (0 to stop): 0\
Total sum: 8
