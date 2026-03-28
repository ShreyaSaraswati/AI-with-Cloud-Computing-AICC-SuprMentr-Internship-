# Assignment 04 – Logic Builder (FizzBuzz)
**Date:** 17-02-2026

## Description
Print numbers from 1 to 50 using FizzBuzz logic:

- Multiples of 3 → print "Fizz"
- Multiples of 5 → print "Buzz"
- Multiples of both 3 and 5 → print "FizzBuzz"
- Otherwise → print the number

Also count how many times Fizz, Buzz, and FizzBuzz occur using loops and functions.

---

## Code
```python
# Logic Builder - FizzBuzz Program

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


# Calling the function
fizz, buzz, fizzbuzz = fizz_buzz()

print("\n--- Count Summary ---")
print("Fizz count:", fizz)
print("Buzz count:", buzz)
print("FizzBuzz count:", fizzbuzz)
```

---

## Output
```
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
16
17
Fizz
19
Buzz
Fizz
22
23
Fizz
Buzz
26
Fizz
28
29
FizzBuzz
31
32
Fizz
34
Buzz
Fizz
37
38
Fizz
Buzz
41
Fizz
43
44
FizzBuzz
46
47
Fizz
49
Buzz

--- Count Summary ---
Fizz count: 13
Buzz count: 7
FizzBuzz count: 3
```

---

## Concepts Used
- Functions
- Loops (for loop)
- Conditional Statements (if-elif-else)
- Modulus Operator (%)
- Counters (count variables)
- Logic Building
- Python Programming

---

## Learning Outcome
- Learned how loops automate repetitive tasks
- Understood how conditions control program logic
- Learned how modulus operator helps identify multiples
- Learned how to count occurrences using variables
- Improved logical thinking and coding skills

---

## Conclusion
FizzBuzz is a classic programming problem used to improve logical thinking. This program demonstrates how loops, conditions, and functions work together to solve problems efficiently.
