# **Python Quick Reference**

Quick reference for Python fundamentals. 

For more detailed documentation, use the dictionary from [W3 Schools](https://www.w3schools.com/python/default.asp), the official [Python Tutorial](https://docs.python.org/3/tutorial/index.html), and/ or [TutorialsPoint](https://www.tutorialspoint.com/python/index.htm).

## Table of Contents
- [Data Types](#data-types)
- [Variables](#variables)
- [Built-in Functions](#built-in-functions)
- [Math Operators](#math-operators)
- [String Manipulation](#string-manipulation)
- [Boolean Operators](#boolean-operators)
- [Iteration](#iteration)
- [Lists](#lists)
- [Tuples](#tuples)
- [Sets](#sets)

## Data Types

Three common data types are strings, integers, and floats.

- **Strings** are sets of characters enclosed in quotation marks. Examples include:
  - `"Super!Password?123"`
  - `"Jane Doe"`
  - `"Once upon a time and a very good time it was there was a moocow coming down along the road."`

- **Integers** are whole numbers without quotation marks:
  - `1`, `-132`, `4358435789403`

- **Floats** are decimal numbers:
  - `3.4`, `5.34543`, `94948.2984758920`

- **Booleans** are True/False values, capitalized:
  - `True`, `False` 


## Variables

Variables store information for you to use repeatedly. To define a variable, use an `=` sign.

```python
my_variable = some_value
age = 7
name = "Heavy Robot"
weight = 324.2
```

Each example includes a **variable name** on the left, the **operator** (`=`), and its **value** on the right. Together, they form an **expression**.

## Functions

### Built-in Functions
Functions always have parentheses immediately after their names. Python includes many **built-in functions** that may be used for certain cases. Their names are reserved keywords. Note they won't work for *every* data type or structure. Here common ones:

- `print("x:",y)`: Prints to the console (but does not return anything).
- `input("x")`: Accepts user input.
- `max(x,y)`, `min(x,y)`: Returns maximum or minimum value from a list.
- `len(x)`: Returns the length of a string or list.
- `range(x)`: Returns a sequence of numbers.
- `count()`: Returns occurance of element.
- `enumerate()`: Returns both the index and the value of items in an iterable.
- `int()`, `str()`, `float()`: Converts to data type.
- `list()`: Converts a collection of items into a list.
- `keys()`, `values()`: Returns the key or value of a dictionary entry.
- `bin()`: Convert decimal to binary. 
- `ord()`: Returns Unicode/ASCII integer of character. 

Some functions can take in many **arguments** (denoted by x, y, z). Any values that goes inside the parentheses is called an **argument**. Multiple arguments are separated by a comma:

```python
length = len("Hello")  # One argument: a string.
# Returns the length of the string, which is 5.

print("Value:", 42)  # Two arguments: a string and a number.
# Displays "Value: 42" on the screen.

largest = max(4, 23, 8, 11, 2)  # Five arguments: a list of numbers.
# Returns the maximum value, which is 23.
```
### Custom Functions
When you create (i.e., define) a custom function, you can use any name that isn't already a built-in function, followed by `def` for "define". For example:

```python
def custom_adder(x,y):
    print(x + y) 

custom_adder(4,6) # Prints 10
custom_adder(2,2) # Prints 4
```

## Math Operators

Various mathematical operations use these common operators:

`+`: Addition. 3 + 2 returns 5
`-`: Subtraction. 5 - 2 returns 3
`*`: Multiplication. 4 * 3 returns 12
`/`: Division; 5 / 2 returns a float 2.5
`//`: Floor Division. 5 // 2 rounds down to 2
`%`: Modulus. 10 % 3 returns remainder 1
`**`: Exponentiation (Power). 2 ** 3 returns 8

And don't forget built-in libraries!

- **Random Library**: imports a PRNG (pseudorandom number generator) library with many built-in functions.

```python
import random

random_integer = random.randint(1, 10)  # Example: 7
random_float = random.random()  # Example: 0.456
random_float_range = random.uniform(1.0, 10.0)  # Example: 5.678
random_choice = random.choice(['apple', 'banana', 'cherry'])  # Example: 'banana'
my_list = [1, 2, 3, 4, 5]
random.shuffle(my_list)  # List might be shuffled to [3, 1, 5, 2, 4]
random.sample(my_list, k) # returns multiple (k) unique values from my_list.  
```

- **Math Library**: import built-in mathematical functions beyond basic operations.

```python
import math

square_root = math.sqrt(16)  # Returns 4.0
pi_value = math.pi  # Approximately 3.14159
square_root = math.sqrt(25)  # Returns 5.0
sine_value = math.sin(math.pi / 2)  # Returns 1.0
factorial_value = math.factorial(5)  # Returns 120

```
## String Manipulation 

### f-string Formatting 

F-strings are "formatted strings". Add the letter 'f' right before a string to let it take in dynamic variables or expressions, enclosed in braces `{}`. 

```python
food = "taco"
price = 5

print(f"This {food} costs {price} dollars!?")
# => This taco costs 5 dollars!?
```

### String Concatenation

Concatenate strings with a plus sign. 

```python
string1 = "Hello"
string2 = "World"

print(string1 + " " + string2 + "!!!")

# Prints Hello World!!! 
```

Note that the plus sign does not add strings together, even if they are numbers. 

```python
#integer data type:
2 + 2 + 6 = 10

#string data type: 
'2' + '2' + '6' = 226
'two' + 'two' + 'six' = twotwosix
```

### String Splicing 

String splicing uses bracks, and the start and end index to cut up (slice) strings. 

```python
string = "abcdefghijklmnopqrstuvwxyz"

substring = string[11:16]   # => "lmnop"
substring2 = string[:4]     # => "abcd"
substring3 = string[22:]    # => "wxyz"
substring4 = string[-3:]    # => "xyz"

substring5 = string[::2]    # => "acegikmoqsuwy" (every second character)
substring6 = string[::-1]   # => "zyxwvutsrqponmlkjihgfedcba" (reversed string)
substring7 = string[1:8:2]  # => "bdfh" (every second character from index 1 to 7)
```

### String Functions

Various functions used to manipulate strings (and occasionally other iterables, like lists and tuples). Look up documentation for various uses and options. 

- `capitalize()`: Capitalizes word in string.
- `count()`: Counts occurance.
- `lower()`: Converts entire string to lowercase.
- `upper()`: Converts entire string to uppercase.
- `len()`: Returns integer of the length of a string. 
- `find()`: Returns integer of index location of a searched substring. 
- `replace()`: Returns a sequence of numbers.

## Boolean Operators

### Comparison Operators

- `==`: Equal to  
- `!=`: Not equal to  
- `>`: Greater than  
- `<`: Less than  
- `>=`: Greater than or equal to  
- `<=`: Less than or equal to

### Logical Operators

- `and`: Returns `True` if both operands are true. Example: `x and y`
- `or`: Returns `True` if at least one operand is true. Example: `x or y`
- `not`: Returns `True` if the operand is false. Example: `not x`
- `in`: Checks if a value exists within an iterable (like a string or list). Example: `x in list`
- `is`: Compares the identity of two objects. Example: `x is y`

### Boolean Functions

- `isdigit()`: Returns `True` if all characters in the string are digits. Example: `"1234".isdigit()`
- `isalpha()`: Returns `True` if all characters in the string are alphabetic. Example: `"abcd".isalpha()`
- `isalnum()`: Checks if all characters in a string are alphanumeric (letters and numbers).
- `isupper()`: Returns `True` if all characters in the string are uppercase. Example: `"HELLO".isupper()`
- `islower()`: Returns `True` if all characters in the string are lowercase. Example: `"hello".islower()`

## Iteration 

Iteration is when you repeat a set of instructions or steps multiple times, which helps you go through lists of items or perform tasks without writing the same code over and over again.

### While Loops  

Loops over iterable as long as a condition is True. Stops when the condition becomes False. 

```python
counter = 0

while counter <= 5:
    counter += 1
    
print(counter)

# The while loop will run until the condition is False (when counter is not less than 5 anymore).
# Print statement returns 5 (not 4, since the counter increments until the condition becomes False).
```

### For Loops

Loops over iterable for a set number of times..

```python

numbers = [1, 2, 3]

for i in range(len(numbers)):
    print(f"Index: {i}, Value: {numbers[i]}")

# The for loop will run until it reaches the end of the list, printing each index and its corresponding value.
# Print statement returns:
# Index: 0, Value: 1
# Index: 1, Value: 2
# Index: 2, Value: 3
```

**Using range()**

It is common to use the range() built-in function to return the indexes of an iterable. 

```python
numbers = [1, 2, 3]

for i in range(len(numbers)):
    print(i)

# The for loop will run until it reaches the end of the list, printing each index.
# Print statement returns:
# 0
# 1
# 2
```

## Lists
A list is a mutable (changeable), ordered, iterable collection of data enclosed in square brackets `[]`, with elements separated by commas. Lists can contain numbers, strings, booleans, and even other lists (nested lists).

```python
letters = ["a", "z", "d"]

print(letters[2]) 
# Displays "d", which is located at index 2

for letter in letters:
    print(letter.upper())
# Permanently modifies original list:
# A
# Z
# D
```

### List Functions 

- `append()`: Adds value to end of the list.  
  ex. `letters.append("m")` => `["a", "z", "d", "m"]`
- `pop(index)`: Removes and returns value at last (or specified) index.  
  ex. `last_letter = letters.pop()` returns: `"m"` and list becomes `["a", "z", "d"]`
- `sort()`: Sorts a list in ascending order (modifies the list in place).  
  ex. `letters.sort()` => `["a", "d", "z"]`
- `sorted()`: Converts a non-list collection of items into a sorted list.
  ex. `sorted("b", "d", "c". "a")`
- `reverse()`: Reverses the order of the list in place.
  ex. `letters.reverse()` => `["z", "d", "a"]`
- `insert(index, value)`: Inserts a value at a specified index.  
  ex. `letters.insert(1, "b")` => `["a", "b", "z", "d"]`
- `index(value)`: Returns the index of the first occurrence of a specified value.  
  ex. `z_index = letters.index("z")` => `1`

### List Comprehension

Creates new list by applying an expression to each item in an iterable.

```python
whole_numbers = [n for n in range(5)]  # Results in: [0, 1, 2, 3, 4]
squared_numbers = [n ** 2 for n in range(5)]  # Creates a list of squares: [0, 1, 4, 9, 16]
even_squares = [n ** 2 for n in range(10) if n % 2 == 0]  # Results in: [0, 4, 16, 36, 64]
```

## Tuples 
A tuple is an immutable (non-changeable), iterable, ordered collection of data enclosed in parenthesis `()`, with elements separated by commas. Due to their immutability, tuples are more memory effecient, thus faster than lists. They may contain any data type, as well as nested tuples. 

```python
letters = ("a", "z", "d")

print(letters[2]) 
# Displays "d", which is located at index 2

letters.append(z) # ERROR
letters.pop() # ERRORR
```

### Tuple Functions

Tuples do not have functions that modify them, but you may use basic built-in functions for counting and iteraation:
- `tuple()`: convert a list into a tuple.
- `count()`: count elements in tuple.
- `index()`: return index of first occurance of an element.

They are iterable, so you may use loops. 

## Sets 
A set is a mutable (chaneable), iterable, unordered collection of data enclosed in curly braces `{}`, with elements separated by commas. Set will only include unique elements, and no duplicates. Lists can contain numbers, strings, booleans, but they cannot contain other sets or lists).

```python
my_set = {1, 2, 3.14, "hello", (1, 2)}
```

### Set Functions 
- `set()`: Convert an iterable into a unique set. Duplicates will be removed.
- `add()`: adds an element to the set. (Unless it's already there).
- `update()`: adds multiple elements to the set. This can be another set, list, tuple, or any iterable.
- `remove()`: removes element from a list (not index).
### Set Operations
- `union()`: compares multiple sets, returns new set of only unique elements. You can also use `|`.
```python
set1 = {"a", "b", "c"}
set2 = {"c", "d", "e"}
```
```python
result = set1.union(set2) # Alternative syntax: set1 | set2
print(result)  # Output: {"a", "b", "c", "d", "e"}
```
- `intersection()`:  compares multiple sets, returns new set of only shared elements. You can also use `&`.
```python
result = set1.intersection(set2) # Alternative syntax: set1 & set2
print(result)  # Output: {"c"}
```
- `difference()`: compares multiple sets, returns elements in first, but not second set. You can also use `-`.
```python
result = set1.difference(set2) Alternative syntax: set1 - set2
print(result)  # Output: {"a", "b"}
```


### More to come as we continue learning Python in class


*Created by Mr Harrell*
