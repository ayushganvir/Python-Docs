# Python Docs

> Some important things about python 3

### Contents

- [List Comprehension](#list-comprehesion)
- [Permutations and Combinations](#permutations-and-combinations)
- [Copy a List](#copy-a-list)
- [Dictionary](#Dictionary)
- [Map](#map)
- [Filter](#filter)
- [Reduce](#reduce)
- [Accumulate](#accumulate)
- [.join](#join)
- [Generators](#generators)
- [Enumerate](#enumerate)
- [from collections import Counter](#from-collections-import-counter)
- [Sort in list of list](#sort-in-list-of-list)


# List Comprehension

> ## List comprehension is a way to make a list which can take another list as an input and apply Filter & Map on it.

> ## The list comprehension follows the order of first Filter the map.

- ## Mapping
- ## Filter and Mapping
## Map in comprehension
```python
list = [1, 2, 3, 4, 5, 6]
double_list = [num * 2 for num in list]
```

The value will be:

```python
double_list =[2, 4, 6, 8, 10, 12]
```

> ## This is just the example of map, in this case it is doubled
> ## The map can be done over the list and any function, lambda or callable(int, str etc) can be used to do that.


## Filter And Map
> ## This will first filter then map the list and give a new one.
> ## This can only take one if condtion
> ## if conditon can have any conditions
Sample code

```python
list = [1, 2, 3, 4, 5, 6, 7, 8]
even_list = [num for num in list if num % 2 == 0]
```

even list will have:

```python 
even_list = [2, 4, 6, 8]
```
# Permutations and Combinations
> ## Gives a Permutation/Combination interable Object. To iterate over that, make that a list. list()
# Permutations
```python
# A Python program to print all 
# permutations of given length 
from itertools import permutations 

# Get all permutations of length 2 
# and length 2 
perm = permutations([1, 2, 3], 2) 

# Print the obtained permutations 
for i in list(perm): 
	print i 

```
## Output 

```python
(1, 2)
(1, 3)
(2, 1)
(2, 3)
(3, 1)
(3, 2)
```
## Same Process for combinations as well


# Copy a List

> ## The copy() method returns a shallow copy of the list.

### A list can be copied using the = operator. The problem with copying lists in this way is that if you modify new_list, old_list is also modified.

```python
my_list = ['cat', 0, 6.7]

# copying a list
new_list = my_list.copy()

print('Copied List:', new_list)
```
### Output will be:

```python
Copied List: ['cat', 0, 6.7]
```

# Dictionary

> ## A dictionary is a collection which is unordered, changable, and indexed

```python
D={'Maharashtra': 'Mumbai', 'Rajasthan': 'Jaipur', 'Karnataka': 'Bengaluru'}
```

## Access any value to any key in dictionary

```python
print(D['Maharashtra'])
>>> 'Mumbai'
```

## To get all the keys and values in any dictionary

```python
print(D.keys())
print(D.values())
```

## Looping through the Dictionary

## Use Dictionary.items() to iterate over a dictionary

```python
 for k,v in D.items():
    print(k,v)
>>>
Maharashtra Mumbai
Rajasthan Jaipur
Karnataka Bengaluru
```

# Map

## Example of code

```python
lst =[1,2,3,4,6,7,9,0]
print(list((map(lambda x : x * 2, lst))))
```

### Output will be:

```python
[2, 4, 6, 8, 12, 14, 18, 0]
```

### General Syntax

```python
map(fun, iter)
```

> ## fun : It is a function to which map passes each element of given iterable.

> ## iter : It is a iterable which is to be mapped.

## Map() function returns an iterable map object, which can be made list or tuple

> ## It has a function to map through and lambda

```python
def addition(n): 
    return n + n 
  
# We double all numbers using map() 
numbers = (1, 2, 3, 4) 
result = map(addition, numbers) 
print(list(result))
```

### Output will be:

```python
[2, 4, 6, 8]
```

# Filter

## Example of Code:

```python
lst =[1,2,3,4,6,7,9]
print(list(filter(lambda x : x >= 4, lst)))
```

### Output will be:

```python
[4, 6, 7, 9]
```

### General Syntax

```python
map(func, *iterables)
```

> ## Where func is the function on which each element in iterables (as many as they are) would be applied on.

> ## Iterables can be lists, tuples etc.

> ## Filter can also have Functions

```python
lst =[1,2,3,4,6,7,9]
def more_than_four(x):
    if x >= 4: 
        return x 
print(list(filter(more_than_four, lst)))
```

#### Output Will be:

```python 
[4, 6, 7, 9]
```

> ## We can Map and Filter together.

```python
lst =[1,2,3,4,6,7,9]
def more_than_four(x):
    if x >= 4: 
        return x 
print(list(map(str,filter(more_than_four, lst))))
```

#### Output Will be:

```python
['4', '6', '7', '9']
```
# Reduce

## Example Of Code:

```python
import functools 
lis = [ 1 , 3, 5, 6, 2] 
# Calculate Sum 
print (functools.reduce(lambda a,b : a+b,lis)) 
```

### Ouput will be:

```python
17
```

> ## This can also have functions, lambda.

# Accumulate

## Example Of Code:

```python
import itertools
lis = [ 1, 3, 4, 10, 4 ]
print (list(itertools.accumulate(lis,lambda x,y : x+y))) 
```
Output will be:
```python
[1, 4, 8, 18, 22]
```

> ## Difference between Accumulate and reduce is that reduce will give you a single data type (int), but accumulate will give a list which will be done like mapping

# .join

### Example Code:


```python
names_list = ['Ayush', 'Ira', 'Dev']
print(", ".join(names_list))
```

#### output will be:

```python
Ayush, Ira, Dev
```

> ## Join method provides a method to make a string from iterables(list, str, dict, tuples etc)

## General Syntax:

```python
string.join(iterable)
```

# Generators

> ## Python generators can create iterators, without taking actual space

> ## Generators create a generator class, which is an iterator.

> # Generators are like normal functions but they 'yield' instead of 'return'

> # A generator can have multiple yield

> ## The difference is that while a return statement terminates a function entirely, yield statement pauses the function saving all its states and later continues from there on successive calls.

## Comprehension form of generator:

```python
xyz =(i for i in range(5))
```
## Example of how generators work:

```python
# A simple generator function
def my_gen():
    n = 1
    print('This is printed first')
    # Generator function contains yield statements
    yield n

    n += 1
    print('This is printed second')
    yield n

    n += 1
    print('This is printed at last')
    yield n
```

### Command line:

```python
>>> # It returns an object but does not start execution immediately.
>>> a = my_gen()

>>> # We can iterate through the items using next().
>>> next(a)
This is printed first
1
>>> # Once the function yields, the function is paused and the control is transferred to the caller.

>>> # Local variables and theirs states are remembered between successive calls.
>>> next(a)
This is printed second
2

>>> next(a)
This is printed at last
3

>>> # Finally, when the function terminates, StopIteration is raised automatically on further calls.
>>> next(a)
Traceback (most recent call last):
...
StopIteration
>>> next(a)
Traceback (most recent call last):
...
StopIteration
```

### You can also make generator by list comprehension
```python
# Initialize the list
my_list = [1, 3, 6, 10]

# square each term using list comprehension
list_ = [x**2 for x in my_list]

# same thing can be done using a generator expression
# generator expressions are surrounded by parenthesis ()
generator = (x**2 for x in my_list)

print(list_)
print(generator)
```

### Output:
```python
[1, 9, 36, 100]
<generator object <genexpr> at 0x7fbf10746510>
```

### You can iterate over this generator objects by using 'for' loop.

### next() in generator
#### Sample Code:
```python
# Initialize the list
my_list = [1, 3, 6, 10]

a = (x**2 for x in my_list)
print(next(a))

print(next(a))

print(next(a))

print(next(a))

next(a)
```

#### Output:
```python
1
9
36
100
Traceback (most recent call last):
  File "<string>", line 13, in <module>
StopIteration
```

# enumerate()

## Syntax:
```python
enumerate(iterable, start=0)
```

### Example:
```python
l1 = ["eat","sleep","repeat"] 
print(list(enumerate(l1)))
```

### Output:
```python
>>> [(0, 'eat'), (1, 'sleep'), (2, 'repeat')]
```
# from collections import Counter
## This will count the number of times(occurance)

```python
from collections import Counter

list1 = [1,2,3,4,5,5,3,2,3,4,2,4,2,4,1,1,2,3,3,1]
c = Counter(list1)
print(c.items())
```
### Output:

```python
dict_items([(1, 4), (2, 5), (3, 5), (4, 4), (5, 2)])
```

> ## If you are using Counter(list), to get the output as list of list use c  = Counter(list), then c.items()


# Sort in list of list
> ## This could be used for Tuples, dictionary etc

## Given list

```python
list1 = [4,6,3,6,3,6,7,7,3,6,8]
v = list(enumerate(list1))
print(v
```
### Output will be:

```python
[(0, 4),
 (1, 6),
 (2, 3),
 (3, 6),
 (4, 3),
 (5, 6),
 (6, 7),
 (7, 7),
 (8, 3),
 (9, 6),
 (10, 8)]
 ```

### If we want to sort the given list of tuples by [0] or [1] element of the tuples, we can use lambda functions to map to that index.
```python
v.sort(key = lambda x : x[1])
print(v)
```
### Output will be:

```python
[(3, 3),
 (5, 3),
 (9, 3),
 (1, 4),
 (2, 6),
 (4, 6),
 (6, 6),
 (10, 6),
 (7, 7),
 (8, 7),
 (11, 8)]
 ```