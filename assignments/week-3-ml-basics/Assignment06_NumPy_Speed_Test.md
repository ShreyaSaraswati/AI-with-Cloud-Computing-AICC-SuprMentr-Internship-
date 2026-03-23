# Assignment 06 – NumPy Speed Test

## Problem Statement
Compare execution time of Python list vs NumPy array using 1 million numbers.

---

## Code

```python
import time
import numpy as np

python_list = list(range(1_000_000))

start = time.time()
[x*2 for x in python_list]
end = time.time()

list_time = end-start

arr = np.array(python_list)

start = time.time()
arr*2
end = time.time()

numpy_time = end-start

print("List time:", list_time)
print("NumPy time:", numpy_time)
```

---

## Observations

NumPy is significantly faster  
Vectorized operations improve performance  
Useful for large datasets

---

## Concepts Used

NumPy  
Performance testing  
Time module
