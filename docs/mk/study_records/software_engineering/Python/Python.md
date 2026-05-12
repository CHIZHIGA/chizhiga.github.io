# Python

## Variables

### Variable assignment

Python has built-in support for arithmetic expressions and so can be used as a calculator. When we evaluate an expression in Python, the result is displayed, but not necessarily stored anywhere.

If we want to access the result in subsequent code, we have to store it. We put it in a box, with a name on the box. This is a _variable_. In Python we _assign_ a value to a variable using the _assignment operator_ `=`

As well as numeric [literal values](https://en.wikipedia.org/wiki/Literal_(computer_programming)) Python also has built in support for representing textual data as sequences of characters, which in computer science terminology are termed [_strings_](https://en.wikipedia.org/wiki/String_(computer_science)). Strings in Python are indicated by enclosing their contents in either a pair of single quotation marks `'...'` or a pair of double quotation marks `"..."`, for example.

### Naming variables

It is good practice to give variables descriptive and meaningful names to help make code self-documenting. As most modern development environments (including Jupyter Lab!) offer _tab completion_ there is limited disadvantage from a keystroke perspective of using longer  names

### Variables and memory

We can now better understand our mental model of variables as labels and boxes: each box is a piece of space (an *address*) in computer memory. Each label (_variable_) is a reference to such a place and the data contained in the memory defines an _object_ in Python. Python objects come in different types - so far we have encountered both numeric (integer) and textual (string) types - more on this later.

When the number of labels on a box (_variables referencing an address_) gets down to zero, then the data in the box cannot be accessed any more. This will trigger Python's garbage collector, which will then 'empty' the box (_deallocated the memory at the address_), making it available again to store new data.

Lower-level languages such as C and Fortran do not have garbage collectors as a standard feature. So a memory address with no references to it and which has not been specifically marked as free remains unavailable for other usage, which can lead to difficult to fix [_memory leak_](https://en.wikipedia.org/wiki/Memory_leak) bugs.

When we execute

```
name = "Grace Hopper"
nom = name
nom = "Grace Brewster Murray Hopper"
name = "Admiral Hopper"
```

the following happens

1. A new text (_string_) object `"Grace Hopper"` is created at a free address in memory and the variable `name` is set to refer to that address
2. The variable `nom` is set to refer to the object at the address referenced by `name`
3. A new text (_string_) object `"Grace Brewster Murray Hopper"` is created at a free address in memory and the variable `nom` is set to refer to that address
4. A new text (_string_) object `"Admiral Hopper"` is created at a free address in memory, the variable `name` is set to refer to that address and the garbage collector deallocates the memory used to hold `"Grace Hopper"` as this memory is no longer referenced by any variables.

## Using Functions

### Calling functions in Python

Python provides a range of useful [built-in functions](https://docs.python.org/3/library/functions.html) for performing common tasks. For example the `len` function returns the length of a sequence object (such as a string) passed as input argument. To _call_ a function in Python we write the name of the function followed by a pair of parentheses `()`, with any arguments to the function being put inside the parentheses:

### Getting help on functions

The built-in `help` function, when passed a function, prints documentation for the function, which typically includes a description of the what arguments can be passed and what the function returns. For example

```
help(max)
```

In Jupyter notebooks and ipython consoles an alternative way of displaying the documentation for a function is to write the function names followed by a question mark character `?`

```
max?
```

### Positional and keyword arguments and default values

There are two ways of passing arguments to function in Python. In the examples so far the function arguments have only been identified by the position they appear in the argument list of the function. An alternative is to use named or _keyword_ arguments, by prefixing some or all of the arguments with the argument name followed by an equals sign.

### Functions are objects

A powerful feature of Python (and one that can take a little while to wrap your head around) is that functions are just a particular type of object and so can be for example assigned to variables or passed as arguments to other functions. We have in fact already seen examples of this when using the `help` function, with a function passed as the (only) argument to `help`. We can also assign functions to variables

```
my_print = print
my_print("Hello") --> Hello
```

## Types

We have so far encountered several different 'types' of Python object: 

- integer numbers, for example `42`, 
- real numbers, for example `3.14`,
- strings, for example `"abc"`,
- functions, for example `print`,
- the special 'null'-value `None`. 

The built-in function `type` when passed a single argument will return the type of the argument object. For example

### Converting between types

The Python type names such as `int` (integer numbers) and `str` (strings) can be used like functions to construct _instances_ of the type, typically by passing an object of another type which can be converted to the type being called. For example we can use `int` to convert a string of digits to an integer

### Floats and integers

Python has two core numeric types, `int` for integers, and `float` for real numbers.

Binary arithmetic operators applied to objects of `float` and `int` types will return a `float`

In Python there are two division operators `/` and `//` which implement different mathematical operations. The _true division_ (or just _division_) operator `/` implements what we usually think of by division, such that for two `float` values `x` and `y` `z = x / y` is another `float` values such that `y * z` is (to within machine precision) equal to `x`. The _floor division_ operator `//` instead implements the operation of dividing and rounding down to the nearest integer.

### Strings

Python built-in `string` type, supports many useful operators and methods. As we have seen already the addition operator can be used to concatenate strings

## Containers

Containers are a data type that _contains_ other objects.

### Lists

Python's basic **container** type is the `list`

### Tuples

A `tuple` is an immutable sequence. It is like a list, except it cannot be changed. It is defined with round brackets.

## Dictionaries and Sets

### The Python Dictionary

Python supports a container type called a dictionary.

This is also known as an "associative array", "map" or "hash" in other languages.

#### Keys and Values

The things we can use to look up with are called **keys**:

The things we can look up are called **values**:

#### Immutable Keys Only

The way in which dictionaries work is one of the coolest things in computer science:
the "hash table". This is way beyond the scope of this course, but it has a consequence:

You can only use **immutable** things as keys.

### Sets

A set is a `list` which cannot contain the same element twice.
We make one by calling `set()` on any sequence, e.g. a list or string.

## Structures

### Nested Lists and Dictionaries

In research programming, one of our most common tasks is building an appropriate *structure* to model our complicated
data. Later in the course, we'll see how we can define our own types, with their own attributes, properties, and methods. But probably the most common approach is to use nested structures of lists, dictionaries, and sets to model our data.

## 



