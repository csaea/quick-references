# Big O Examples and Notation

Big O (aka Big Order) is a shorthand way of measuring the worst case scenario (or upper bound) of an algorithm's time and space complexity, based on its input size. With Big O, you don't have to be precise, as its purpose is to only describe how bad it can get. That is, if an algorithm has code blocks with differing Big O complexities, always go with the slowest one. 

For each example below, the input will be a list of 100 numbers, 1 to 100, named `items`.

## Constant Complexity - O(1)

O(1) algorithms always take the same amount of time, no matter the input size. 

```python
def constant_time(items):
    print(items[23])  
```
## Logarithmic Complexity O(log n)

O(log N) algorithms halve the input repeatedly. Grows slowly. Good for large amount of inputs

```python
def logarithmic_time(n):
    count = 0
    while n > 1:
        n //= 2
        count += 1
    print(count)
```
## Linear Complexity O(n)

O(log n) algorithms take the same amount of time as the amount of inputs. Good for reasonable amount of inputs. 

```python
def linear_time(items):
    arr = [...]
    for x in arr:
        print(x)
```

```python
def linearithmic_time(items):
    print("Linearithmic (O(n log n)):")
    sorted_items = sorted(items)
    print(sorted_items[:5], "...")
    print()  # Sorting often involves dividing and merging; faster than O(n^2), slower than O(n)
```

## Quadratic Complexity O(N^2)

O(N^2) algorithm has exponential growth for each input.

```python
def quadratic_time(items):
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

