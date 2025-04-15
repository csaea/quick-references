# Big O Notation Reference 

Big O (Big Order) Notation is a way of estimating the time/space cost of an algorithm. Big O eye-balls the worst-case-scenario (aka upper bound) of an algorithm's time/space complexity relative to its input. With Big O, you don't have to be precise. Its purpose is to only estimate how slow or large an algorithm can become. So if an algorithm has code blocks with differing Big O complexities, always go with the slowest one. 

Below are four complexities considered to be 'reasonable time'. Common complexities considered to be 'unreasonable' are O(n2) or O(n!).

| Function       | Big O Notation |
|----------------|----------------|
| [Constant](#constant---o1)       | O(1)           |
| [Logarithmic](#logarithmic---olog-n)    | O(log n)       |
| [Linear](#linear---on)         | O(n)           |
| [Quadratic](#quadratic---n^2) | O(n2)

## Constant - O(1)

O of (1) algorithms are constant because no matter the input size, they always take the same amount of time.  

```python
items = list(range(100)) # items is an array [0...99]

def constant_time(items):
    print(items[23])  
```
## Logarithmic - O(log n)

O of (log N) algorithms consistantly shrink the amount of inputs with each step. Its time complexity grows slowly, making it effecient for large datasets.

```python
def logarithmic_time(n):
    while n > 1:
        print(f"n is now {n}")
        n = int(n / 2)
```

## Linear - O(n)

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

## Quadratic O(N^2)

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

