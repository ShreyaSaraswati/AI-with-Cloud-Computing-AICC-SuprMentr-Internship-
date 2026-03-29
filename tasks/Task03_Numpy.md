# Task 03 – NumPy Temperature Analysis
Date: 13-02-2026

---

## Problem Statement
1. Create a list of temperatures in degree Celsius: `[28, 32, 40, 37, 26, 38]`  
2. Convert the list into a NumPy array  
3. Print minimum and maximum temperature  
4. Calculate average temperature  
5. Display temperatures of the last 3 days

---

## Code:
```python
import numpy as np

# Temperature list
temps = [28, 32, 40, 37, 26, 38]

# Convert to NumPy array
temp_array = np.array(temps)

# Min and Max temperature
min_temp = np.min(temp_array)
max_temp = np.max(temp_array)

# Average temperature
avg_temp = np.mean(temp_array)

# Last 3 days temperatures
last_3_days = temp_array[-3:]

print("Temperature Array:", temp_array)
print("Minimum Temperature:", min_temp)
print("Maximum Temperature:", max_temp)
print("Average Temperature:", avg_temp)
print("Last 3 Days Temperature:", last_3_days)
```
----

## Output:
Temperature Array: [28 32 40 37 26 38]\
Minimum Temperature: 26\
Maximum Temperature: 40\
Average Temperature: 33.5\
Last 3 Days Temperature: [37 26 38]
