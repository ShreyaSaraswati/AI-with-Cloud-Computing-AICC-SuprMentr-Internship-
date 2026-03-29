# Task 02 – Shopping Cart with Lists
Date: 11-02-2026

---

## Problem Statement
1. Create a shopping cart using Python lists  
2. Allow adding items to the cart  
3. Remove one item from the cart  
4. Print all items and total number of items in the cart

---

## Code:
```python
# Create a shopping cart
cart = []

# Adding items
cart.append("Apple")
cart.append("Banana")
cart.append("Orange")
cart.append("Milk")

print("Items in cart:", cart)

# Remove one item
cart.remove("Banana")
print("After removing Banana:", cart)

# Total items
print("Total number of items:", len(cart))
```
---

## Output:
Items in cart: ['Apple', 'Banana', 'Orange', 'Milk']\
After removing Banana: ['Apple', 'Orange', 'Milk']\
Total number of items: 3
