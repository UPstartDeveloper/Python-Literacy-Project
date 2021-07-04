# Welcome to Python!

Hello reader, 

This document will jumpstart your understanding of Python. We will cover all the foundational aspects of the programming language, and provide you with examples of how to use each of them in practice. Whenever you get stuck on the exercises in this book, feel free to come back to this section as well - after all, even the most experienced programmers have to review the basics sometimes!

## Table of Contents

1. [Data Types](#data-types)
2. [Variables](#variables)
3. [Control Flow](#control-flow)
4. [Container Types](#container-types)
5. [Functions](#functions)
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
    **Note**: don't be intimidated by the syntax of the above statement - it is just another form of string formatting! The result is the program will display a message that says `'I am 29 years old.'`. Please look at the [Python documentation](https://docs.python.org/3/library/stdtypes.html#str.format) if you are curious to learn more.

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
While knowing how to store data is nice, it is even cooler to be able to write programs that can let the computer do certain tasks for us.

*Control flow* refers to how the computer figures out what to do with our data in a given situation. This is most often done through giving the computer specific conditions on what to do in a given scenario ahead of time.

For example, you may do this yourself when deciding what clothes to wear outside. You might decide whether to wear sunglasses or not, based on if the sun is shining. If we were to write *pseudocode* for this decision, it might look like the following:
```
if the sun_is_out,
    THEN, I will wear_sunglasses()!
```
This process can be almost exactly replicated in Python code - the first piece to making it possible is *comparison operators*!
### Comparison Operators
*Comparison operators* help our program decide whether or not a given piece data meets a given condition. 

Table 3 shows the comparison operators found in Python:
##### Table 3: Comparison Operators and What They Mean

| Operator | Meaning                  |
| -------- | ------------------------ |
| `==`     | Equal to                 |
| `!=`     | Not equal to             |
| `<`      | Less than                |
| `>`      | Greater Than             |
| `<=`     | Less than or Equal to    |
| `>=`     | Greater than or Equal to |

These operators evaluate to True or False depending on the values you give them. They all follow a syntax of `data <operator_goes_here> condition` (but you don't necessarily have to put the `data` on the left side and `condition` on the right).

**Note**: since the result of a comparison operation is only True or False, this means comparison operators *must* return Boolean(`bool`) values.

Here are a few examples of Boolean operations - can you tell if they evaluate to `True` or `False`?

1. With Numeric Data:
    ```python
    42 == 42  
    ```

    ```python
    40 == 42
    ```

    ```python
    42 == 42.0
    ```
2. With String Data:
    ```python
    'hello' == 'hello'
    ```

    ```python
    'dog' != 'cat'
    ```

    ```python
    42 == '42'
    ```
    **Note**: comparison operators are *case-sensitve* - that is, they will not judge two characters as equal if one is lower case and the other is upper case. The following code snippet demonstrates this:
    ```python
    'hello' == 'Hello'
    ```
### Boolean Operators

There are also operators specifically meant for working with `bool` values. Specifically, the four Boolean operators are `is`, `and`, `or`, and `not`.

Tables 4-7 show where each of these operators returns `True` or `False`:


##### Table 4: The *is* Operator’s *Truth* Table:

| Expression      | Evaluates to |
| --------------- | ------------ |
| True is True   | True         |
| True is False  | False        |
| False is True  | False        |
| False is False | True         |

##### Table 5: The *and* Operator’s *Truth* Table:

| Expression      | Evaluates to |
| --------------- | ------------ |
| True and True   | True         |
| True and False  | False        |
| False and True  | False        |
| False and False | False        |

##### Table 6: The *or* Operator’s *Truth* Table:

| Expression     | Evaluates to |
| -------------- | ------------ |
| True or True   | True         |
| True or False  | True         |
| False or True  | True         |
| False or False | False        |

##### Table 7: The *not* Operator’s *Truth* Table:

| Expression | Evaluates to |
| ---------- | ------------ |
| not True   | False        |
| not False  | True         |
### Boolean evaluation

By convention, Python programmers do not like to use the `==` or `!=` operators to evaluate `bool` values themselves. Instead, it is more popular to use the `is` or `is not` operators.

Examples of What NOT To Do: 

```python
True == True
```

```python
True != False
```

Do THIS Instead: 

```python
True is True
```

```python
True is not False
```

### Mixing Boolean and Comparison Operators
Just as we saw with mixing single and double quotes in strings, Python is not *totally* against us mixing Boolean and comparison operators. See if you can correctly identify the return value of each expression:

```python
(5 >= 7) and (5 < 6)  
```

```python
(1 == 2) or (2 == 2)
```
**Note**: although we are mixing Boolean and comparison operators here, notice how we use parentheses `()` to clearly show the how the Boolean operators `or` and `and` are only working with values that have already been evaluated to be `True` or `False`.

You can also use multiple Boolean operators in an expression, along with those comparison operators:

```python
(4 < 9) and not (-6 < 6) and (2 * 2 == 2 + 2)
```

### if Statements
The `if` statement takes the value computed by a Boolean evaluation, and if it is `True` we can run a specific piece of code to so our program does the appropiate thing in that scenario.

Going back to our sunglasses example above, we are one step closer to writing code that can tell our user when to put on sunglasses:

```python
if is_sun_out == True:
    print("You're going to need sunglasses today!")
```
Don't forget to tab over all the code you want to be run in case the `if` statement is `True`!

### else Statements
The `else` statement is a complement to the `if` statement - that is, if the condition in the `if` statement evaluates to `False`, then control flow in our program will go and execute the code found indented below our `else` keyword:

```python
if is_sun_out == True:
    print("You're going to need sunglasses today!")
else:  # the sun is NOT out
    print("You're all set :)")
```

### elif Statements
The `else` keyword is nice, but it cannot be given a condition to evaluate by itself - it *has* to be paired with an `if` statement. This is not a good situation for scenarios where our program needs to be able to do more than just 1 of 2 actions.

This is where the `elif` statement comes in handy - it is short for "else if". Like the `else` statement, it will be evaluated by control flow in our program, if the condition in our `if` statement is `False`. BUT, it can also be given a condition of its own, just like the `if` statement! to allow for writing more nuanced programs!

For example, let's say you usually greet your friends `Andre` and `Rediet` when you first come to school. We can make special greetings for both of our friends in Python, with code such as the following:

```python
name = 'Andre'

if name == 'Andre':
    print('Wassup, Andre!')
elif name == 'Rediet':
    print('Howdy Rediet')
```
To go one step further, we can use an `if`, `elif`, and `else` all together! In a given program, control flow will only go to the block of code whose condition evaluates to `True`. This lets us write even more nuanced programs, such as being able to greet anyone we meet as we come into school, even if we don't already know their name:

```python
if name == 'Andre':
    print('Wassup, Andre!')
elif name == 'Rediet':
    print('Howdy Rediet')
else:  # name does not have a value yet, for some reason
    print('Hey, nice to meet you!')
    name = input("What's your name?")
```

### Implicit Boolean Evaluation
It can be cumbersome to write out the full condition for an `if` or `elif` statement all the time - and that's why Python actually lets us take it out if we want:
```python
a = (2 + 2 == 4)

if a is True:
   pass
if a is not False:
   pass
if a: 
   pass
```
All of the `if` statements in the code above are equivalent - but that in the last `if` block above, we stopped right at `a`! This is an example of using *implicit boolean evaluation*. It is a great way to save yourself a few keystrokes, and if `a` has a `bool` data type, then this is still valid Python code! 

### while Loop Statements
The `while` loop is used just the `if` statement, except that it will exhaustively execute the code in its block. It will only stop once the condition it has evaluates to `False`:

```python
spam = 0

while spam < 5:
    print('Hello, world.')
    spam = spam + 1
```

### for Loops and the range() Function
Another kind of loop in Python is the `for` loop. Unlike the `while` loop, it doesn't need a condition - instead, `for` loops are used when we already know ahead of time how many *iterations*, or the number of times our code executes, that we want to have.

Therefore, the syntax of the `for` loop is only there to let the program know how many iterations to go through.

```python
print('My name is')
for i in range(5):
    print('Jimmy Five Times ({})'.format(str(i)))
```
If you run the code snippet above, you will see the following output:
```
'Jimmy Five Times (0)'
'Jimmy Five Times (1)'
'Jimmy Five Times (2)'
'Jimmy Five Times (3)'
'Jimmy Five Times (4)'
```
Why is this happening?

The `range()` function is commonly used in `for` loops, and it is a good one to remember - it essentially is used to set the value of `i` on each of the 5 iterations our `for` goes through. You may also read more about it on the [Python documentation](https://docs.python.org/3/library/stdtypes.html#range) as you wish.

The `range()` function can also be called with three arguments. The first two arguments will be the *start* and *stop* values, and the third will be the *step* argument. The step is the amount that the variable is increased by after each iteration.

Once the value of our *iterator* (in this case `i`) reaches or surpasses the value of the *stop* argument, our for loop terminates:

```python
for i in range(0, 10, 2):
   print(i)
```
**Note**: when we only the `range()` function with 1 argument, then that is the *stop* argument - the defaults for the *start* and *step* parameters are 0 and 1, respectively.

You can even use a negative number for the step argument to make the for loop count down instead of up.

```python
for i in range(5, -1, -1):
    print(i)
```

...and that's it for control flow! Being able to use conditional statements like `if`, `elif`, and `else`, as well as being able to write loops will enable us to work with larger and larger datasets using Python. Speaking of which, let's see how Python represents large collections of data the next section, which is all about using container data types! 

## Container Types

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

## Credits

This section would not be possible if not for the following sources:

1. *[Automate the Boring Stuff with Python](https://automatetheboringstuff.com/)*, a book by Al Sweigart under the [Creative Commons license](https://creativecommons.org/licenses/by-nc-sa/3.0/).
2. The [Python Cheatsheet](https://www.pythoncheatsheet.org/) website and [GitHub repository](https://github.com/wilfredinni/python-cheatsheet) by wilfredinni.