# Assignment 06 – NumPy Speed Test

## Problem Statement 
Compare execution time of Python list vs NumPy array using 1 million numbers.  
Measure performance difference and observe which method is faster.

---

## Code
```python
# NumPy Speed Test

import time
import numpy as np

# Creating Python list with 1 million numbers
python_list = list(range(1_000_000))

# Measuring execution time for Python list
start_time = time.time()
result_list = [x * 2 for x in python_list]
end_time = time.time()
list_time = end_time - start_time

# Converting list to NumPy array
numpy_array = np.array(python_list)

# Measuring execution time for NumPy array
start_time = time.time()
result_numpy = numpy_array * 2
end_time = time.time()
numpy_time = end_time - start_time


# Printing results
print("Python List Execution Time:", list_time, "seconds")
print("NumPy Array Execution Time:", numpy_time, "seconds")

print("\nPerformance Difference:")
print("NumPy is faster by:", list_time - numpy_time, "seconds")
```

---

## Output
```
Python List Execution Time: 0.051215171813964844 seconds
NumPy Array Execution Time: 0.004180908203125 seconds

Performance Difference:
NumPy is faster by: 0.047034263610839844 seconds
```

---

## Observations
- NumPy performs calculations faster than Python lists
- Vectorized operations reduce execution time
- NumPy is efficient for large datasets
- Performance difference increases with larger data size

---

## Concepts Used
- NumPy Library
- Arrays
- Python Lists
- Performance Testing
- Time Module
- Vectorized Operations
- Data Processing

---

## Learning Outcome
- Learned difference between Python list and NumPy array
- Learned how to measure execution time using time module
- Understood how NumPy improves performance
- Learned importance of optimized libraries in data science
- Observed speed advantage of vectorized operations

---

## Conclusion
NumPy arrays perform faster than Python lists for large datasets because they use optimized and vectorized operations. NumPy is widely used in AI, Machine Learning, and Data Science for efficient numerical computation.
