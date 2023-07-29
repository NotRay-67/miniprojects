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
output : `2`

The `any() `function returns `True` if any item in an iterable are true, otherwise it returns `False`.

If the iterable object is empty, the `any()`function will return `False`.

Example:
Implement a function that reproduces this behaviour, returning a list of booleans corresponding to whether the corresponding element is greater than n.
```python
def elementwise_greater_than(L, thresh):
    res = []
    for ele in L:
        res.append(ele > thresh)
    return res
```
And here's the list comprehension version:
```python
def elementwise_greater_than(L, thresh):
    return [ele > thresh for ele in L]
```

## 6. Strings and Dictionaries

One place where the Python language really shines is in the manipulation of strings. This section will cover some of Python's built-in string methods and formatting operations.

Such string manipulation patterns come up often in the context of data science work.


**Double quotes are convenient** if your string contains a single quote character (e.g. representing an apostrophe).

Similarly, it's easy to create a string that contains double-quotes if you wrap it in single quotes:

```python
print("Pluto's a planet!")
print('My dog is named "Pluto"')
# we can also fix this by using a backlash
print('Pluto\'s a planet!')
```
In addition, **Python's triple quote syntax** for strings lets us include newlines literally (i.e. by just hitting 'Enter' on our keyboard, rather than using the special '\n' sequence). 

We've already seen this in the docstrings we use to document our functions, but we can use them anywhere we want to define a string.

```python
triplequoted_hello = """hello
world"""
print(triplequoted_hello)
triplequoted_hello == hello
```

```python
# and, we can even loop over them
[char+'! ' for char in planet]
```
output: `['P! ', 'l! ', 'u! ', 't! ', 'o! ']`

`str.join()` takes us in the other direction of split function **sewing a list of strings up into one long string,** using the string it was called on as a separator.

```python
'/'.join([month, day, year])

# Yes, we can put unicode characters right in our string literals :)
' 👏 '.join([word.upper() for word in words])
```
output : 
`'01/31/1956'`

'PLUTO 👏 IS 👏 A 👏 PLANET!'

We call `.format()` on a "format string", where the Python values we want to insert are represented with `{}` placeholders.

Notice how we didn't even have to call str() to convert position from an int. format() takes care of that for us.

If that was all that format() did, it would still be incredibly useful. But as it turns out, it can do a lot more. Here's just a taste:
```python
pluto_mass = 1.303 * 10**22
earth_mass = 5.9722 * 10**24
population = 52910390
#         2 decimal points   3 decimal points, format as percent     separate with commas
"{} weighs about {:.2} kilograms ({:.3%} of Earth's mass). It is home to {:,} Plutonians.".format(
    planet, pluto_mass, pluto_mass / earth_mass, population,
)
```
output : `"Pluto weighs about 1.3e+22 kilograms (0.218% of Earth's mass). It is home to 52,910,390 Plutonians."`

```python
# Referring to format() arguments by index, starting from 0
s = """Pluto's a {0}.
No, it's a {1}.
{0}!
{1}!""".format('planet', 'dwarf planet')
print(s)
```
output : `Pluto's a planet.
No, it's a dwarf planet.
planet!
dwarf planet!`

### Dictionaries
Dictionaries are a built-in Python data structure for mapping keys to values.
```python
numbers = {'one':1, 'two':2, 'three':3}
```
In this case 'one', 'two', and 'three' are the keys, and 1, 2 and 3 are their corresponding values.

Values are accessed via square bracket syntax similar to indexing into lists and strings.

Python has dictionary comprehensions with a syntax similar to the list comprehensions we saw in the previous tutorial.

```python
planets = ['Mercury', 'Venus', 'Earth', 'Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']
planet_to_initial = {planet: planet[0] for planet in planets}
planet_to_initial
```
output : 
`{'Mercury': 'M',
 'Venus': 'V',
 'Earth': 'E',
 'Mars': 'M',
 'Jupiter': 'J',
 'Saturn': 'S',
 'Uranus': 'U',
 'Neptune': 'N'}`

The in operator tells us whether something is a key in the dictionary

The very useful dict.items() method lets us iterate over the keys and values of a dictionary simultaneously. (In Python jargon, an item refers to a key, value pair)

```python
for planet, initial in planet_to_initial.items():
    print("{} begins with \"{}\"".format(planet.rjust(10), initial))
```
`   Mercury begins with "M" 
     Venus begins with "V"
     Earth begins with "E"
      Mars begins with "M"
   Jupiter begins with "J"
    Saturn begins with "S"
    Uranus begins with "U"
   Neptune begins with "N"`

**Enumerate() in Python**

Often, when dealing with iterators, we also get need to keep a count of iterations. Python eases the programmers’ task by providing a built-in function enumerate() for this task. `Enumerate()` method adds a counter to an iterable and returns it in a form of enumerating object. This enumerated object can then be used directly for loops or converted into a list of tuples using the list() function.
```python
# Python program to illustrate
# enumerate function
l1 = ["eat", "sleep", "repeat"]
s1 = "geek"
  
# creating enumerate objects
obj1 = enumerate(l1)
obj2 = enumerate(s1)
  
print ("Return type:", type(obj1))
print (list(enumerate(l1)))
  
# changing start index to 2 from 0
print (list(enumerate(s1, 2)))
```
output : `[(0, 'eat'), (1, 'sleep'), (2, 'repeat')]
[(2, 'g'), (3, 'e'), (4, 'e'), (5, 'k')]`

## 7. Working with external libraries

### Imports

So far we've talked about types and functions which are built-in to the language.

But one of the best things about Python (especially if you're a data scientist) is the vast number of high-quality custom libraries that have been written for it.

A module is just a collection of variables (a namespace, if you like) defined by someone else. We can see all the names in math using the built-in function `dir()`.

import * makes all the module's variables directly accessible to you (without any dotted prefix).

```python
from math import *
print(pi, log(32, 2))
```
```python
from math import *
from numpy import *
print(pi, log(32, 2))

---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
/tmp/ipykernel_19/3018510453.py in <module>
      1 from math import *
      2 from numpy import *
----> 3 print(pi, log(32, 2))

TypeError: return arrays must be of ArrayType

```


What has happened? It worked before!

These kinds of "star imports" can occasionally lead to weird, difficult-to-debug situations.

The problem in this case is that the math and numpy modules both have functions called log, but they have different semantics. Because we import from numpy second, its log overwrites (or "shadows") the log variable we imported from math.

A good compromise is to import only the specific things we'll need from each module:

```python
from math import log, pi
from numpy import asarray
```

### Submodules

We've seen that modules contain variables which can refer to functions or values. Something to be aware of is that they can also have variables referring to other modules.

```python
import numpy
print("numpy.random is a", type(numpy.random))
print("it contains names such as...",
      dir(numpy.random)[-15:]
     )
```
`numpy.random is a <class 'module'>
it contains names such as... ['seed', 'set_state', 'shuffle', 'standard_cauchy', 'standard_exponential', 'standard_gamma', 'standard_normal', 'standard_t', 'test', 'triangular', 'uniform', 'vonmises', 'wald', 'weibull', 'zipf']`


**So if we import numpy as above,** then calling a function in the random "submodule" will require two dots

```python
# Roll 10 dice
rolls = numpy.random.randint(low=1, high=6, size=10)
rolls
```

### Three tools for understanding strange objects

In the cell above, we saw that calling a numpy function gave us an "array". We've never seen anything like this before (not in this course anyways). But don't panic: we have three familiar builtin functions to help us here.

1. type()
2. dir()
3. help()

### Operator overloading

We might think that Python strictly polices how pieces of its core syntax behave such as +, <, in, ==, or square brackets for indexing and slicing. But in fact, it takes a very hands-off approach. When you define a new type, you can choose how addition works for it, or what it means for an object of that type to be equal to something else.

The designers of lists decided that adding them to numbers wasn't allowed. The designers of numpy arrays went a different way (adding the number to each element of the array).

```python
xlist = [[1,2,3],[2,4,6],]
# Create a 2-dimensional array
x = numpy.asarray(xlist)
print("xlist = {}\nx =\n{}".format(xlist, x))
```
output : 

```
xlist = [[1, 2, 3], [2, 4, 6]]
x =
[[1 2 3]
 [2 4 6]]

```
numpy's ndarray type is specialized for working with multi-dimensional data, so it defines its own logic for indexing, allowing us to index by a tuple to specify the index at each dimension.