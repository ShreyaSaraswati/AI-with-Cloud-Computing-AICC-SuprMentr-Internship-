# Assignment 05 – Student Data Manager

## Problem Statement
Store marks of 5 students using dictionary.
Find:
- class average
- topper
- grade for each student

---

## Code

```python
students = {
    "Aman": 85,
    "Riya": 92,
    "Karan": 76,
    "Sneha": 88,
    "Arjun": 95
}

average = sum(students.values()) / len(students)

topper = max(students, key=students.get)

def assign_grade(marks):
    if marks >= 90:
        return "A"
    elif marks >= 80:
        return "B"
    elif marks >= 70:
        return "C"
    else:
        return "D"

for name, marks in students.items():
    print(name, marks, assign_grade(marks))

print("Average:", average)
print("Topper:", topper)
```

---

## Output

```
Average: 87.2
Topper: Arjun
```

---

## Concepts Used

Dictionary  
Functions  
Loops  
Data Processing
