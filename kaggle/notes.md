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

## 4. Lists


**Interlude: objects**

I've used the term 'object' a lot so far - you may have even read that everything in Python is an object. What does that mean?

In short, objects carry some things around with them. You access that stuff using Python's dot syntax.

For example, numbers in Python carry around an associated variable called imag representing their imaginary part. (You'll probably never need to use this unless you're doing some very weird math.)

```python
x = 12
# x is a real number, so its imaginary part is 0.
print(x.imag)
# Here's how to make a complex number, in case you've ever been curious:
c = 12 + 3j
print(c.imag)
```
`0`

`3.0`

The things an object carries around can also include functions. A function attached to an object is called a method. (Non-function things attached to an object, such as imag, are called attributes).

For example, numbers have a method called bit_length. Again


`list.pop()` function removes and returns the last object


instead of using `list.index()` function we can use `in` opetator

```python

# planets is list filled with all the plants
"Earth" in planets
```
output : `True`

**Tuples**

Tuples are often used for functions that have multiple return values.

For example, the as_integer_ratio() method of float objects returns a numerator and a denominator in the form of a tuple

```python
x = 0.125
x.as_integer_ratio()
```
output : `(1, 8)`

## 5. Loops and list comprehensions

List comprehensions are one of Python's most beloved and unique features. The easiest way to understand them is probably to just look at a few examples:

```python
squares = [n**2 for n in range(10)]
squares
```
output : `[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]`

We can also add an if condition:
```python
short_planets = [planet for planet in planets if len(planet) < 6]
short_planets
```
output : `['Venus', 'Earth', 'Mars']`

***List comprehensions combined with functions like min, max, and sum can lead to impressive one-line solutions for problems that would otherwise require several lines of code.***

```python
def count_negatives(nums):
    """Return the number of negative numbers in the given list.
    
    >>> count_negatives([5, -1, -2, 0, 3])
    2
    """
    n_negative = 0
    for num in nums:
        if num < 0:
            n_negative = n_negative + 1
    return n_negative
```
output : 
