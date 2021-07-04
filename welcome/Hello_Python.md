# Welcome to Python!

Hello reader, 

This document will jumpstart your understanding of Python. It will cover all the foundational aspects of the programming language, and provide examples of how to use each of them in practice. Whenever you get stuck on the exercises in this book, feel free to come back to this section as well - after all, even the most experienced programmers have to review the basics sometimes!

## Table of Contents
**[TODO]** put in links

1. [Data Types](#data-types)
2. [Control Flow]()
3. [Functions]()
4. [Container Types]()
5. [Credits](#credits) 

## Data Types

### Math Operators

From **Highest** to **Lowest** precedence:

| Operators | Operation        | Example         |
| --------- | ---------------- | --------------- |
| **        | Exponent         | `2 ** 3 = 8`    |
| %         | Modulus/Remainder | `22 % 8 = 6`    |
| //        | Integer division | `22 // 8 = 2`   |
| /         | Division         | `22 / 8 = 2.75` |
| *         | Multiplication   | `3 * 3 = 9`     |
| -         | Subtraction      | `5 - 2 = 3`     |
| +         | Addition         | `2 + 2 = 4`     |

Examples of expressions in the interactive shell:

```python
2 + 3 * 6
```

```python
(2 + 3) * 6
```

```python
2 ** 8
```

```python
23 // 7
```

```python
23 % 7
```

```python
(5 - 1) * ((7 + 1) / (3 - 1))
```

### Data Types

| Data Type              | Examples                                  |
| ---------------------- | ----------------------------------------- |
| Integers               | `-2, -1, 0, 1, 2, 3, 4, 5`                |
| Floating-point numbers | `-1.25, -1.0, --0.5, 0.0, 0.5, 1.0, 1.25` |
| Strings                | `'a', 'aa', 'aaa', 'Hello!', '11 cats'`   |

### String Concatenation and Replication

String concatenation:

```python
'Alice' 'Bob'
```

Note: Avoid `+` operator for string concatenation. Prefer string formatting.

String Replication:

```python
'Alice' * 5
```

### Variables

You can name a variable anything as long as it obeys the following rules:

1. It can be only one word.
2. It can use only letters, numbers, and the underscore (`_`) character.
3. It can’t begin with a number.
4. Variable name starting with an underscore (`_`) are considered as "unuseful`.

Example:

```python
spam = 'Hello'
```

```python
_spam = 'Hello'
```

`_spam` should not be used again in the code.

### Comments

Inline comment:

```python
# This is a comment
```

Multiline comment:

```Python
# This is a
# multiline comment
```

Code with a comment:

```python
a = 1  # initialization
```

Please note the two spaces in front of the comment.

Function docstring:

```python
def foo():
    """
    This is a function docstring
    You can also use:
    ''' Function Docstring '''
    """
```

### The print Function

```python
print('Hello world!')
```

```python
a = 1
print('Hello world!', a)
```

### The input Function

Example Code:

```python
myName = input('What is your name?') # ask for their name
print('It is good to meet you, {}'.format(myName))
```

### The len Function

Evaluates to the integer value of the number of characters in a string:

```python
len('hello')
```

Note: test of emptiness of strings, lists, dictionary, etc, should **not** use len, but prefer direct
boolean evaluation.

```python
a = [1, 2, 3]
if a:
    print("the list is not empty!")
```

### The str, int, and float Functions

Integer to String or Float:

```python
str(29)
```

```python
print('I am {} years old.'.format(str(29)))
```

```python
str(-3.14)
```

Float to Integer:

```python
int(7.7)
```

```python
int(7.7) + 1
```

## Credits

This section would not be possible if not for the following sources:

1. *[Automate the Boring Stuff with Python](https://automatetheboringstuff.com/)*, a book by Al Sweigart under the [Creative Commons license](https://creativecommons.org/licenses/by-nc-sa/3.0/).
2. The [Python Cheatsheet](https://www.pythoncheatsheet.org/) website and [GitHub repository](https://github.com/wilfredinni/python-cheatsheet) by wilfredinni.