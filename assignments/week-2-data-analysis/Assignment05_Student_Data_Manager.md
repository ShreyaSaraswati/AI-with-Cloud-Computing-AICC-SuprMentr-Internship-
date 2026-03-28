# Assignment 05 – Student Data Manager

## Problem Statement
Store marks of 5 students using a Python dictionary.  
Calculate class average, identify the topper, and assign grades to each student based on marks.

Grade Criteria:
- 90 and above → Grade A
- 80–89 → Grade B
- 70–79 → Grade C
- Below 70 → Grade D

---

## Code
```python
# Student Data Manager

# Storing student data (Name: Marks)
students = {
    "Aman": 85,
    "Riya": 92,
    "Karan": 76,
    "Sneha": 88,
    "Arjun": 95
}

# Finding class average
average = sum(students.values()) / len(students)

# Finding topper
topper = max(students, key=students.get)

# Function to assign grade
def assign_grade(marks):
    if marks >= 90:
        return "A"
    elif marks >= 80:
        return "B"
    elif marks >= 70:
        return "C"
    else:
        return "D"

print("---- Student Grades ----")

for name, marks in students.items():
    print(f"{name}: {marks} marks - Grade {assign_grade(marks)}")

print("\nClass Average:", average)
print("Topper:", topper, "with", students[topper], "marks")
```

---

## Output
```
---- Student Grades ----
Aman: 85 marks - Grade B
Riya: 92 marks - Grade A
Karan: 76 marks - Grade C
Sneha: 88 marks - Grade B
Arjun: 95 marks - Grade A

Class Average: 87.2
Topper: Arjun with 95 marks
```

---

## Concepts Used
- Dictionary (storing key-value data)
- Functions
- Loops (for loop)
- Conditional Statements (if-elif-else)
- Built-in functions (sum, len, max)
- Data Processing
- Python Programming

---

## Learning Outcome
- Learned how to store structured data using dictionary
- Learned how to calculate average using built-in functions
- Learned how to find maximum value from dictionary
- Learned how to assign grades using conditions
- Improved data handling and logic building skills

---

## Conclusion
This program demonstrates how Python dictionaries can be used to manage student records efficiently. It calculates class performance metrics and assigns grades automatically.
