# Assignment 04 – Logic Builder (FizzBuzz)

## Problem Statement
Print numbers from 1 to 50:
- multiples of 3 → Fizz
- multiples of 5 → Buzz
- multiples of both → FizzBuzz

Also count occurrences.

---

## Code

```python
def fizz_buzz():
    fizz_count = 0
    buzz_count = 0
    fizzbuzz_count = 0

    for num in range(1, 51):
        if num % 3 == 0 and num % 5 == 0:
            print("FizzBuzz")
            fizzbuzz_count += 1
        elif num % 3 == 0:
            print("Fizz")
            fizz_count += 1
        elif num % 5 == 0:
            print("Buzz")
            buzz_count += 1
        else:
            print(num)

    return fizz_count, buzz_count, fizzbuzz_count

fizz, buzz, fizzbuzz = fizz_buzz()

print("\nCounts:")
print("Fizz:", fizz)
print("Buzz:", buzz)
print("FizzBuzz:", fizzbuzz)
```

---

## Output (summary)

```
Fizz count: 13
Buzz count: 7
FizzBuzz count: 3
```

---

## Concepts Used

Loops  
Functions  
Conditions  
Counters
