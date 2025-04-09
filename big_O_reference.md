# Big O Notation Reference 

Big O (Big Order) is a shorthand way of eye-balling the worst case scenario (upper bound) of an algorithm's time/space complexity relative to its input. With Big O, you don't have to be precise. Its purpose is to only estimate how slow or large an algorithm can become. So if an algorithm has code blocks with differing Big O complexities, always go with the slowest one. 


## Constant Complexity - O(1)

O of (1) algorithms always take the same amount of time, no matter the input size. 

```python
items = list(range(100)) # items is an array [0...99]

def constant_time(items):
    print(items[23])  
```
## Logarithmic Complexity - O(log n)

O of (log N) algorithms consistantly shrink the amount of inputs with each step. Its time complexity grows slowly, making it effecient for large datasets.

```python
def logarithmic_time(n):
    while n > 1:
        print(f"n is now {n}")
        n = int(n / 2)
```

## Linear Complexity O(n)

O of (n) algorithms take the same amount of time as the amount of inputs. Good for limited inputs. 

```python
def linear_time(items):
    arr = [...]
    for x in arr:
        print(x)
```

## 

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

