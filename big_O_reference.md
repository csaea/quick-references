```python
import time
import random

#The following are simple examples of different Big O time scales and their notation. 

def constant_time(items):
    print("Constant (O(1)):")
    print(items[3])  # Always takes the same amount of time regardless of input size
    print()

def logarithmic_time(n):
    print("Logarithmic (O(log n)):")
    count = 0
    while n > 1:
        n //= 2
        count += 1
    print(f"Steps: {count}")
    print()  # Halves the input repeatedly; grows slowly

def linear_time(items):
    print("Linear (O(n)):")
    total = 0
    for item in items:
        total += item
    print(f"Total: {total}")
    print()  # Processes each item once; time grows directly with input size

def linearithmic_time(items):
    print("Linearithmic (O(n log n)):")
    sorted_items = sorted(items)
    print(sorted_items[:5], "...")
    print()  # Sorting often involves dividing and merging; faster than O(n^2), slower than O(n)

def quadratic_time(items):
    print("Quadratic (O(n^2)):")
    count = 0
    for i in items:
        for j in items:
            count += 1
    print(f"Pairs counted: {count}")
    print()  # Compares every pair; time squares with input size

def exponential_time(n):
    print("Exponential (O(2^n)):")
    def fib(k):
        if k <= 1:
            return k
        return fib(k-1) + fib(k-2)
    
    result = fib(n)
    print(f"fib({n}) = {result}")
    print()  # Doubles with each step; impractical beyond small inputs

def main():
    items = list(range(100))
    constant_time(items)
    logarithmic_time(len(items))
    linear_time(items)
    linearithmic_time(items)
    quadratic_time(items[:20])  # Trimmed for time
    exponential_time(5)         # Avoid slow recursion

if __name__ == "__main__":
    main()
```
