# Welcome to Python!

Hello reader, 

This document will jumpstart your understanding of Python. We will cover all the foundational aspects of the programming language, and provide you with examples of how to use each of them in practice. Whenever you get stuck on the exercises in this book, feel free to come back to this section as well - after all, even the most experienced programmers have to review the basics sometimes!

## Table of Contents

1. [Data Types](#data-types)
2. [Variables](#variables)
3. [Control Flow](#control-flow)
4. [Functions](#functions)
5. [Container Types](#container-types)
6. [Credits](#credits) 

## Data Types
Programming languages give us an easy way to manipulate data in the computer - but first, the computer has to understand what kind of data we're dealing with!

Here are some examples of the kinds of data you can work with in the Python programming language:

#### Table 1: Data Types in Python

| Data Type              | Examples                                  |
| ---------------------- | ----------------------------------------- |
| Integers               | `-3, -2, -1, 0, 1, 2, 3`                |
| Floating-point numbers | `-1.25, -1.0, --0.5, 0.0, 0.5, 1.0, 1.25` |
| Strings                | `'a', 'Hello World!', "C-3PO", "bbb"`   |
| Boolean               | `True, False`

Integers and floating-point numbers are also called *numeric types*. We shall cover these more in depth now.

### Numeric Types
Numbers are everywhere! In Python, we have 3 kinds of data types to represent numerical data:

- `int` - whole numbers 
- `float` - floating-point (aka fractional) numbers

Between the `int` and `float` types, Python 3 lets you store any kind of real number in a variable. 

**Note**: there is also a `complex` data type in Python - you may read about it in the [documentation](https://docs.python.org/3/library/functions.html?#complex).

The numeric types are useful for when you are doing mathematical operations - which we will discuss next!

#### Math Operations

Python supports a lot of these! Table 2 describes which operator you can use for each of them, along with examples.
##### Table 2: Mathematical Operators (for Each Operation)

| Operator | Operation        | Example         |
| --------- | ---------------- | --------------- |
| **        | Exponent        | `3 ** 3 = 27`    |
| %         | Modulus/Remainder Division - *returns only the remainder* | `30 % 8 = 6`    |
| //        | Integer division - *truncates any floating-point values in the quotient* | `30 // 8 = 3`   |
| /         | Division - *always returns a `float`*         | `30 / 8 = 3.75` |
| *         | Multiplication   | `2 * 3 = 6`     |
| -         | Subtraction      | `7 - 2 = 5`     |
| +         | Addition         | `9 + 2 = 11`     |

**Note**: all the operators above will return:
- a `float`, if the two operands are 1) both floating-point OR 2) they have different types
- an `int`, if 1) both operands are integers AND 2) it is not the division (`/`) operator

#### Order of Operations
Python prioritzes some operations over others. This means that it follows a *precedence order* that decides which operation to compute first, when there are several of them together in a given expression.

The operators in Table 2 are listed from **highest** to **lowest** precedence, for your reference.

Here are some examples of how the order of operations can impact the result computed by Python code - feel free to run these in a Python shell to check the results (given in the inline comments).

```python 
5 + 3 * 6  # result: 23
```

```python
(5 + 3) * 6  # result: 48
```

```python
2 ** 8  # result: 256
```

```python
23 // 7  # result: 3
```

```python
23 % 7  # result: 2
```

```python
 ((7 + 5) / (4 - 1)) * (5 + 1)  # result: 24.0
```

The next data type we will cover are strings, which are also known as a *text sequence type*.

### Strings
Strings in Python are used to represent any sequence of characters. Basically, anything that can be typed on a computer between a pair of quotes is a string!
#### Common String Operations

1. **String concatenation**:

    *Concatenation* is when one string is added onto the end of another string. A quick and easy way to do this is by using the addition (`+`) operator, just like we did for numbers!

    For example, let's say we wanted a string that said `'Alice met Allison on Tuesday'` - then the code could look like the following:

    ```python
    'Alice met ' + 'Allison on Tuesday'
    ```
    **Note**: although using addition works, it is far from perfect. In practice we prefer 1) *string formatting*, which will be discussed later in this book, or 2) the `str.join()` function, which you may read about in the [Python documentation](https://docs.python.org/3/library/stdtypes.html?#str.join).

2. **String Replication**:

    *Replication* is when we repeat a given string over and over again in a new, longer `str` object. 
    
    Incidently, Python makes this easier for us through the `*` operator. Now, can you guess what the output of the following code will be?

    ```python
    'Alice' * 5
    ```

3. **Displaying Messages using `print()`**
    You will most often see strings where a program needs to tell the user some kind of message - this is exactly what the `print()` function will do:

    ```python
    print('Hello world!')
    ```

4.  **Gathering User Responses using `input()`**

    Another common task is for a computer program to ask the user for their information - this can be done in Python via the `input()` function. 

    In the example below the user will first be prompted to enter their name, because that is what has been passed to the `input()` function. 

    ```python
    name = input('What is your name?') # ask for their name
    ```
    The user's response is then stored in the variable called `name`. 

5. **Measuring Length using `len()`**

    We can also calculate valuates thenumber of characters in a string:

    ```python
    len('hello')  # result: 5
    ```
    Note that the `len()` function is also applicable to all of Python's "container" data types, which are used to store multiple pieces of data at the same time (like lists, sets, and dictionaries) - all of these will be covered below!

**Common Mistakes**:

Strings have such a wide definition, that it is easy to make mistakes when working with them. Here are some things to watch out for:
1. Not enclosing them in single quotes (e.g. `'Hello'`) or double quotes (e.g. `"World"`)
2. Although Python treats single and double quotes the same, you *cannot* combine the two (e.g. do NOT do `"Hello, World!'`)
#### Quotes in Strings

This doesn't mean that you are not allowed to mix double quotes and single quotes. As long as you enclose each pair of quotes, they can in fact be very useful to use together - such as when a string includes a quote!

For example, the following is how you should NOT include quotes in a string together:

```python
print("I said "hello."")  # ERROR!
```
In the above code snippet, the `'hello'` ends up not being enclosed by any pair of quotes. 

So how to remedy this? One option is to enclose the whole string in a pair of *single quotes*, so we can let the *double quotes* in the sentence enclose the `'hello'` properly:
```python
print('I said "hello."')  # all good :)
```

Next, let's take a look at the Boolean data type!
### Boolean Types
The Boolean data type, represented as `bool` in Python, needs no overthinking - it simply represents whether `True` or `False`. 

As you might imagine, they are especially useful for writing code that answers yes/no questions - we will discuss this more in-depth when we talk about [Control Flow](#control-flow).

### The str, int, and float Functions
Python's data types are not necessarily set in stone. In some scenarios (shown below) we can convert, or *cast*, a given value in one data type to another, by calling the desired data type like a function! More technically, this is also called *explicit type conversion*.

Here are examples of when we can interchange values between the `int`, `float`, and `str` types:

1. Integer to String or Float:

    ```python
    str(29)
    ```

    ```python
    print('I am {} years old.'.format(str(29)))
    ```

    ```python
    str(-3.14)
    ```

2. Float to Integer:

    ```python
    int(7.7)
    ```

    ```python
    int(7.7) + 1
    ```
Additionally, if you are ever unsure about what the data type of a given value currently is, you can check using the built-in `type()` function:

```python
type(555)  # result: <class: 'int'>
```

## Variables
The data in our program can change not only in its **type**. In addition, it is even more common for our data to change in its **value**. A *variable* in programming is how we represent some piece of data whose value can be many different things. 

Now, from math class you might be used to variable names like `x`, `y`, `z`, etc. - but in programming, it is actually preferable to use much more descriptive names!

You can name a variable anything as long as it obeys the following rules:

1. It can be only one word.
2. It can use only letters, numbers, and the underscore (`_`) character.
3. It can’t begin with a number.
4. Variable name starting with an underscore (`_`) are considered as "unuseful`.

Example 1:

```python
spam = 'Hello'
```
Example 2:

```python
_spam = 'Hello'
```

Because of how `_spam` is named, we know it is not a variable we should use again in the code.

## Control Flow

## Functions

Function docstring:

```python
def foo():
    """
    This is a function docstring
    You can also use:
    ''' Function Docstring '''
    """
```

## Container Types

## Credits

This section would not be possible if not for the following sources:

1. *[Automate the Boring Stuff with Python](https://automatetheboringstuff.com/)*, a book by Al Sweigart under the [Creative Commons license](https://creativecommons.org/licenses/by-nc-sa/3.0/).
2. The [Python Cheatsheet](https://www.pythoncheatsheet.org/) website and [GitHub repository](https://github.com/wilfredinni/python-cheatsheet) by wilfredinni.