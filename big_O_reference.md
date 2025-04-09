# Big O Examples and Notation

Big O (aka Big Order) is a shorthand way of describing the worst case scenario (or upper bound) of an algorithm's time and space complexity, relative to its input size. With Big O, you don't have to be precise, as its purpose is to only describe how bad it can get. 

For each example below, the input will be a list of 100 numbers, 1 to 100, called `items`.

## Constant Time - O(1)

Algorithm always takes the same amount of time regardless of input size. Fastest possible speed. 

```python
def constant_time(items):
    print(items[3])  
    print()
```
## Logarithmic Time O(log n)

Algorithm halves the input repeatedly. Grows slowly. 

```python
def logarithmic_time(n):
    count = 0
    while n > 1:
        n //= 2
        count += 1
    print(f"Steps: {count}")
    print()  
```

```python
def linear_time(items):
    print("Linear (O(n)):")
    total = 0
    for item in items:
        total += item
    print(f"Total: {total}")
    print()  # Processes each item once; time grows directly with input size
```

```python
def linearithmic_time(items):
    print("Linearithmic (O(n log n)):")
    sorted_items = sorted(items)
    print(sorted_items[:5], "...")
    print()  # Sorting often involves dividing and merging; faster than O(n^2), slower than O(n)
```

```python
def quadratic_time(items):
    print("Quadratic (O(n^2)):")
    count = 0
    for i in items:
        for j in items:
            count += 1
    print(f"Pairs counted: {count}")
    print()  # Compares every pair; time squares with input size
```

```python
def exponential_time(n):
    print("Exponential (O(2^n)):")
    def fib(k):
        if k <= 1:
            return k
        return fib(k-1) + fib(k-2)
    result = fib(n)
    print(f"fib({n}) = {result}")
    print()  # Doubles with each step; impractical beyond small inputs
```

