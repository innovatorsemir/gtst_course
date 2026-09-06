# Core Of Python — Indexing, Slicing, Operators, Conditions, Errors & Loops

## Indexing and Slicing `{start, stop, step}`

### Indexing

- Python sequences such as lists, tuples, and strings use index numbers to access individual elements.
- Indexing starts at **0**.

```python
languages = ["Python", "Swift", "C++"]

print(languages[0])  # Python
print(languages[1])  # Swift
print(languages[2])  # C++
```

```text
Value:       Python      Swift       C++
Index:          0          1          2
```

### Negative Indexing

- Python also supports negative indexing.
- `-1` means the last element, `-2` means the second-last element, and so on.

```text
Value:          Python      Swift       C++
Positive:          0          1          2
Negative:         -3         -2         -1
```

```python
languages = ["Python", "Swift", "C++"]

print(languages[-1])  # C++
print(languages[-2])  # Swift
print(languages[-3])  # Python
```

> **Note:** The first element of a Python sequence is always at index `0`.

Indexing also works with strings and tuples:

```python
name = ("hello", 23, 22)
print(name[2])
# Output: 22
```

```python
name = "Semir"
print(name[-2])
# Output: i
```

### Slicing

- Slicing accesses a section of a sequence rather than only one item.
- The slicing operator is `:`.
- General syntax:

```python
sequence[start:stop:step]
```

- `start` → index where slicing begins.
- `stop` → index where slicing stops; the stop index is **not included**.
- `step` → number of positions to move at a time.

Example:

```python
languages = ["Python", "Java", "C++", "JavaScript", "Go"]

print(languages[1:4])
# Output: ['Java', 'C++', 'JavaScript']
```

### Step

```python
numbers = [0, 1, 2, 3, 4, 5, 6]

print(numbers[0:7:2])
# Output: [0, 2, 4, 6]
```

### Default Step

- The default step is `1`, so it can be omitted.

```python
name = "No 1 is Semir"

print(name[8:13:1])
print(name[8:13])
# Output: Semir
# Output: Semir
```

### Omitting Start or Stop

```python
name = "Semir"

print(name[:3])  # Sem
print(name[2:])  # mir
print(name[:])   # Semir
```

### Negative Step

A negative step moves from right to left.

```python
name = "Semir"

print(name[::-1])
# Output: rimeS
```

---

# Input Handling

Python commonly receives input in two basic ways:

1. Using the `input()` function
2. Using command-line arguments

## 1. Input Function

Syntax:

```python
variable = input("Text to display: ")
```

- `input()` displays a prompt, waits for the user, and returns the entered value as a string.

```python
num = input("Enter a number: ")

print("You entered:", num)
print("Data type of num:", type(num))
```

### Converting User Input

Because `input()` returns a string, convert it when a number is needed:

```python
age = int(input("Enter your age: "))
price = float(input("Enter the price: "))
```

Example:

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))

print(f"Hello {name}!")
print(f"You are {age} years old.")
```

## 2. Command-Line Arguments

- Command-line arguments are values supplied when starting a program from a shell/terminal.

Example:

```bash
python gtst.py arg1 arg2 arg3
```

Python provides them through `sys.argv`:

```python
import sys

name = sys.argv[1]
print(f"Hello {name}!")
```

Run:

```bash
python greet.py Semir
```

Output:

```text
Hello Semir!
```

- `sys.argv[0]` is normally the script name.
- `sys.argv[1]` is the first argument.
- `sys.argv[2]` is the second argument, and so on.

Example:

```python
import sys

print(sys.argv)
```

---

# Operations and Operators

- Operators are special symbols or keywords that perform operations on values and variables.

Example:

```python
print(5 + 6)
# Output: 11
```

Main Python operator categories:

- Arithmetic operators
- Assignment operators
- Comparison operators
- Logical operators
- Bitwise operators
- Identity operators
- Membership operators

## A) Arithmetic Operators

Arithmetic operators perform mathematical operations.

| Operator | Operation | Example | Result |
|---|---|---:|---:|
| `+` | Addition | `5 + 2` | `7` |
| `-` | Subtraction | `5 - 2` | `3` |
| `*` | Multiplication | `5 * 2` | `10` |
| `/` | Division | `5 / 2` | `2.5` |
| `//` | Floor division | `5 // 2` | `2` |
| `%` | Modulus | `5 % 2` | `1` |
| `**` | Exponentiation | `5 ** 2` | `25` |

Example:

```python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** b)
```

## B) Assignment Operators

Assignment operators assign or update values in variables.

| Operator | Example | Equivalent |
|---|---|---|
| `=` | `x = 5` | `x = 5` |
| `+=` | `x += 2` | `x = x + 2` |
| `-=` | `x -= 2` | `x = x - 2` |
| `*=` | `x *= 2` | `x = x * 2` |
| `/=` | `x /= 2` | `x = x / 2` |
| `//=` | `x //= 2` | `x = x // 2` |
| `%=` | `x %= 2` | `x = x % 2` |
| `**=` | `x **= 2` | `x = x ** 2` |

Example:

```python
x = 10

x += 5
print(x)  # 15

x *= 2
print(x)  # 30
```

## C) Comparison Operators

- Comparison operators compare values and return a Boolean result: `True` or `False`.

| Operator | Meaning |
|---|---|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

Example:

```python
x = 10
y = 5

print(x == y)  # False
print(x != y)  # True
print(x > y)   # True
print(x < y)   # False
print(x >= y)  # True
print(x <= y)  # False
```

## D) Logical Operators

Python uses:

- `and`
- `or`
- `not`

### AND

`and` is `True` only when both operands are true.

```python
print(True and True)    # True
print(True and False)   # False
print(False and True)   # False
print(False and False)  # False
```

### OR

`or` is `True` when at least one operand is true.

```python
print(True or True)    # True
print(True or False)   # True
print(False or True)   # True
print(False or False)  # False
```

### NOT

`not` reverses a Boolean value.

```python
print(not True)   # False
print(not False)  # True
```

> **Important:** Python uses `and`, `or`, and `not` for logical operations. `&&` and `||` are not Python logical operators.

## E) Bitwise Operators

- Computers represent integer values using binary bits.
- Python's `bin()` function can display an integer in binary.

```python
print("3 in binary is:", bin(3))
print("11 in decimal is:", int("11", 2))

# Output:
# 3 in binary is: 0b11
# 11 in decimal is: 3
```

Bitwise operators:

- `~` → NOT / complement
- `&` → AND
- `|` → OR
- `^` → XOR
- `<<` → Left shift
- `>>` → Right shift

### Bitwise NOT (`~`)

For Python integers:

```text
~x == -(x + 1)
```

Example:

```python
print(~2)
# Output: -3
```

```text
~2 = -(2 + 1) = -3
```

Another example:

```python
print(~-4)
# Output: 3
```

### Bitwise AND (`&`)

```text
10 = 1010
 7 = 0111
------------
    = 0010
```

```python
print(10 & 7)
# Output: 2
```

### Bitwise OR (`|`)

```text
10 = 1010
 7 = 0111
------------
    = 1111
```

```python
print(10 | 7)
# Output: 15
```

### Bitwise XOR (`^`)

XOR produces `1` when the two bits are different.

```text
1 ^ 1 = 0
0 ^ 0 = 0
1 ^ 0 = 1
0 ^ 1 = 1
```

Example:

```text
10 = 1010
 7 = 0111
------------
    = 1101
```

```python
print(10 ^ 7)
# Output: 13
```

### Left Shift (`<<`)

A left shift moves bits to the left.

```python
print(10 << 2)
# Output: 40
```

```text
10 = 1010

1010 << 2
101000 = 40
```

For non-negative integers, shifting left by `n` positions is equivalent to multiplying by `2**n`.

### Right Shift (`>>`)

A right shift moves bits to the right.

```python
print(10 >> 2)
# Output: 2
```

```text
10 = 1010

1010 >> 2
10 = 2
```

For non-negative integers, shifting right by `n` positions is equivalent to floor division by `2**n`.

> Bitwise operations are useful in areas such as networking, embedded systems, cryptography, compression, systems programming, and cybersecurity.

## F) Identity Operators

Identity operators check whether two variables refer to the same object.

- `is`
- `is not`

```python
a = [1, 2, 3]
b = a
c = [1, 2, 3]

print(a is b)  # True
print(a is c)  # False
print(a == c)  # True
```

- `==` compares values.
- `is` checks object identity.

## G) Membership Operators

Membership operators check whether a value exists in a collection.

- `in`
- `not in`

```python
languages = ["Python", "Java", "C++"]

print("Python" in languages)      # True
print("Ruby" in languages)        # False
print("Ruby" not in languages)   # True
```

---

# Indentation

- Indentation means whitespace at the beginning of a line.
- Python uses indentation to define blocks of code.
- The common convention is **4 spaces** per indentation level.
- Incorrect indentation can cause an `IndentationError` or change program logic.

Correct:

```python
if True:
    print("This is inside the if block")
```

Incorrect:

```python
if True:
print("This is incorrectly indented")
```

### Nested Indentation

```python
age = 20

if age >= 18:
    if age >= 21:
        print("Age is 21 or above")
    else:
        print("Age is between 18 and 20")
```

---

# If / Else Conditions

Conditional statements allow a program to make decisions.

Python commonly uses:

1. `if`
2. `if ... else`
3. `if ... elif ... else`
4. Nested `if`

## If Statement

- The `if` statement executes a block when its condition is `True`.

Syntax:

```python
if condition:
    # body of if statement
```

Example:

```python
number = 10

if number > 0:
    print("Number is positive.")

print("The if statement is easy")
```

Output:

```text
Number is positive.
The if statement is easy
```

If the condition is false, the block is skipped:

```python
number = -5

if number > 0:
    print("Number is positive.")

print("This statement is always executed")
```

## If ... Else Statement

Syntax:

```python
if condition:
    # code if condition is True
else:
    # code if condition is False
```

Example:

```python
number = 10

if number > 0:
    print("Positive number")
else:
    print("Negative number")

print("This statement is always executed")
```

## If ... Elif ... Else Statement

- `elif` means "else if".
- Conditions are checked from top to bottom.
- Once a condition is `True`, its block is executed and the remaining `elif`/`else` blocks are skipped.

```python
number = 0

if number > 0:
    print("Positive number")
elif number == 0:
    print("Zero")
else:
    print("Negative number")
```

### Grade Example

```python
percentage = 85

if percentage >= 90:
    grade = "A"
elif percentage >= 75:
    grade = "B"
elif percentage >= 65:
    grade = "C"
else:
    grade = "D"

print("Grade:", grade)
```

## Nested If Statement

- An `if` statement can be placed inside another `if` statement.

```python
number = 5

if number >= 0:
    if number == 0:
        print("Number is 0")
    else:
        print("Number is positive")
else:
    print("Number is negative")
```

Output:

```text
Number is positive
```

---

# Errors and Exceptions

Errors are problems that prevent a program from working as intended.

Common categories include:

1. Syntax errors
2. Runtime errors / exceptions
3. Logical errors

## 1. Syntax Error

A syntax error occurs when Python cannot understand the structure of the code.

Example:

```python
if True
    print("Hello")
```

The `:` is missing.

Correct:

```python
if True:
    print("Hello")
```

## 2. Runtime Errors / Exceptions

A program can have valid syntax but encounter a problem while running.

Example:

```python
number = 10
result = number / 0
```

This raises:

```text
ZeroDivisionError
```

Another example:

```python
numbers = [1, 2, 3]
print(numbers[10])
```

This raises:

```text
IndexError
```

## Common Python Exceptions

| Exception | Example cause |
|---|---|
| `ValueError` | Invalid value, such as `int("abc")` |
| `TypeError` | Incompatible types or operation |
| `NameError` | Using an undefined variable |
| `IndexError` | Invalid sequence index |
| `KeyError` | Missing dictionary key |
| `ZeroDivisionError` | Division by zero |
| `FileNotFoundError` | File does not exist |
| `AttributeError` | Object does not have requested attribute |
| `ModuleNotFoundError` | Requested module cannot be found |

## 3. Logical Errors

A logical error occurs when the program runs but produces the wrong result.

Example:

```python
length = 10
width = 5

area = length + width

print(area)
```

The code runs, but the formula for rectangle area should be:

```python
area = length * width
```

---

# Error Handling

Python provides exception-handling statements such as:

- `try`
- `except`
- `else`
- `finally`
- `raise`

## Basic `try` / `except`

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print(result)
except ValueError:
    print("Please enter a valid number.")
except ZeroDivisionError:
    print("You cannot divide by zero.")
```

## `else`

- The `else` block executes when the `try` block completes without an exception.

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid input.")
else:
    print("You entered:", number)
```

## `finally`

- The `finally` block runs whether an exception occurs or not.
- It is useful for cleanup operations such as closing resources.

```python
try:
    number = int(input("Enter a number: "))
    print(10 / number)
except ZeroDivisionError:
    print("Cannot divide by zero.")
finally:
    print("Program finished.")
```

## Raising an Exception

- Use `raise` to intentionally generate an exception when a condition is invalid.

```python
age = -1

if age < 0:
    raise ValueError("Age cannot be negative")
```

## Catching a General Exception

You can catch a general exception, although specific exceptions are usually preferred.

```python
try:
    result = 10 / 0
except Exception as error:
    print("An error occurred:", error)
```

> Avoid using a broad `except Exception` when you can handle a specific exception. Specific exception handling makes programs easier to debug and maintain.

---

# Loops

Loops allow a program to repeat a block of code.

Python mainly provides:

1. `for` loops
2. `while` loops

Loop-control statements include:

- `break`
- `continue`
- `pass`

# For Loop

A `for` loop iterates over items in an iterable such as a list, tuple, string, dictionary, or `range()`.

Syntax:

```python
for variable in iterable:
    # code
```

Example:

```python
languages = ["Python", "Java", "C++"]

for language in languages:
    print(language)
```

Output:

```text
Python
Java
C++
```

## Using `range()`

`range()` generates a sequence of integers.

```python
for number in range(5):
    print(number)
```

Output:

```text
0
1
2
3
4
```

### Start and Stop

```python
for number in range(1, 6):
    print(number)
```

Output:

```text
1
2
3
4
5
```

### Start, Stop, Step

```python
for number in range(0, 10, 2):
    print(number)
```

Output:

```text
0
2
4
6
8
```

### Reverse Range

```python
for number in range(5, 0, -1):
    print(number)
```

Output:

```text
5
4
3
2
1
```

# While Loop

A `while` loop repeats while its condition remains `True`.

Syntax:

```python
while condition:
    # code
```

Example:

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

Output:

```text
1
2
3
4
5
```

## Avoiding Infinite Loops

Always make sure the loop condition can eventually become false.

Bad example:

```python
number = 1

while number <= 5:
    print(number)
```

`number` never changes, so the loop does not terminate normally.

Correct:

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

# Break

- `break` immediately terminates the nearest loop.

```python
for number in range(1, 10):
    if number == 5:
        break

    print(number)
```

Output:

```text
1
2
3
4
```

# Continue

- `continue` skips the current iteration and continues with the next iteration.

```python
for number in range(1, 6):
    if number == 3:
        continue

    print(number)
```

Output:

```text
1
2
4
5
```

# Pass

- `pass` does nothing.
- It is useful as a placeholder when a statement is syntactically required but the implementation is not ready.

```python
for number in range(5):
    pass
```

Example:

```python
def future_function():
    pass
```

# Nested Loops

A loop can contain another loop.

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

### Multiplication Table Example

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i * j, end=" ")
    print()
```

Output:

```text
1 2 3
2 4 6
3 6 9
```

# Looping Through Strings

```python
name = "Semir"

for character in name:
    print(character)
```

Output:

```text
S
e
m
i
r
```

# Looping Through Dictionaries

```python
student = {
    "name": "Semir",
    "age": 20,
    "department": "ECE"
}
```

### Loop Through Keys

```python
for key in student:
    print(key)
```

### Loop Through Values

```python
for value in student.values():
    print(value)
```

### Loop Through Keys and Values

```python
for key, value in student.items():
    print(key, ":", value)
```

---

# Useful Built-in Functions

## `len()`

Returns the number of items in a collection or characters in a string.

```python
languages = ["Python", "Java", "C++"]
print(len(languages))
# Output: 3
```

## `sum()`

Adds numeric values.

```python
numbers = [1, 2, 3, 4]
print(sum(numbers))
# Output: 10
```

## `max()` and `min()`

```python
numbers = [10, 20, 5, 30]

print(max(numbers))  # 30
print(min(numbers))  # 5
```

## `sorted()`

Returns a sorted list without changing the original iterable.

```python
numbers = [5, 2, 8, 1]
print(sorted(numbers))
# Output: [1, 2, 5, 8]
```

## `enumerate()`

Useful when both the index and value are needed.

```python
languages = ["Python", "Java", "C++"]

for index, language in enumerate(languages):
    print(index, language)
```

Output:

```text
0 Python
1 Java
2 C++
```

---

# Practice Programs

Try creating these programs to practice the topics in this file:

1. Print the first, last, and middle item of a list using indexing.
2. Reverse a string using slicing.
3. Print every second element of a list using `step`.
4. Create a program that accepts two numbers using `input()` and performs arithmetic operations.
5. Create a program that reads a name from `sys.argv`.
6. Create an even/odd checker using `%`.
7. Create a positive/negative/zero checker using `if`, `elif`, and `else`.
8. Create a grade calculator.
9. Create a calculator with `try`/`except` error handling.
10. Print numbers from 1 to 100 using a `for` loop.
11. Print numbers from 100 down to 1 using `range()`.
12. Create a multiplication table using nested loops.
13. Create a number guessing game using a `while` loop.
14. Use `break` to stop a loop when the user enters `q`.
15. Use `continue` to skip odd numbers and print only even numbers.

---

# Quick Summary

| Topic | Main idea |
|---|---|
| Indexing | Access one item using an index |
| Negative indexing | Access items from the end using negative indexes |
| Slicing | Extract a section using `start:stop:step` |
| `input()` | Receive input from the user |
| `sys.argv` | Receive command-line arguments |
| Arithmetic | Perform mathematical operations |
| Assignment | Assign/update variable values |
| Comparison | Compare values and return Boolean results |
| Logical | Combine conditions using `and`, `or`, `not` |
| Bitwise | Operate on integer bits |
| Identity | Check whether objects are the same object |
| Membership | Check whether a value exists in a collection |
| Indentation | Defines Python code blocks |
| `if` | Execute code when a condition is true |
| `elif` | Check another condition |
| `else` | Execute code when previous conditions are false |
| Exceptions | Problems encountered while a program runs |
| `try/except` | Handle exceptions |
| `for` | Iterate over an iterable |
| `while` | Repeat while a condition is true |
| `break` | Stop a loop |
| `continue` | Skip the current iteration |
| `pass` | Placeholder that does nothing |
'''

---

@innovatorsemir