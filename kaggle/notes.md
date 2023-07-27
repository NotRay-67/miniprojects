# Python tutorials
 7 lessons
 

1. Hello, Python
A quick introduction to Python syntax, variable assignment, and numbers

2. Functions and Getting Help
 Calling functions and defining our own, and using Python's builtin documentation

3. Booleans and Conditionals
Using booleans for branching logic

4. Lists
Lists and the things you can do with them. Includes indexing, slicing and mutating

5. Loops and List Comprehensions
For and while loops, and a much-loved Python feature: list comprehensions

6. Strings and Dictionaries
Working with strings and dictionaries, two fundamental Python data types

7. Working with External Libraries
Imports, operator overloading, and survival tips for venturing into the world of external libraries


## 2.functions and getting help

Python isn't smart enough to read my code and turn it into a nice English description. However, when I write a function, I can provide a description in what's called the **docstring**

```python
def least_difference(a, b, c):
    """Return the smallest difference between any two numbers
    among a, b and c.
    
    >>> least_difference(1, 5, -5)
    4
    """
    diff1 = abs(a - b)
    diff2 = abs(b - c)
    diff3 = abs(a - c)
    return min(diff1, diff2, diff3)
```

 the **print** function has several optional arguments. For example, we can specify a value for sep to put some special string in between our printed arguments:
 
 
 
```python
 print(1, 2, 3, sep=' < ')
```

` 1 < 2 < 3 `


for adding a optional arguement in func

```python
def to_smash(total_candies, n_friends=3):
    return total_candies % n_friends
```

## 3. Booleans and conditionals

when the condition is pretty complicated to express using just and, or and not, then use boolean-to-integer conversion that will  gives us the solution 

for example:

```python
return (int(ketchup) + int(mustard) + int(onion)) == 1
#or
return (ketchup + mustard + onion) == 1

```

Fun fact: we don't technically need to call int on the arguments. Just by doing addition with booleans, Python implicitly does the integer conversion. So we could also write...