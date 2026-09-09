# Further on Python

## Functions, Recursion

### Functions

- A function is a block of code that performs a specific task.
- Dividing a complex problem into smaller chunks makes our program easy to understand and reuse.

### Types of Functions

There are two types of functions in Python programming:

#### 1. Standard Library / Built-in Functions

- These are functions that are already available in Python and can be used directly.
- Examples: `print()`, `len()`, `input()`

#### 2. User-defined Functions

- We can create our own functions based on our requirements.
- User-defined functions are created using the `def` keyword.

---

### Creating Functions

#### Syntax

```python
def function_name(arguments):
    # function body
```

A function has a body, just like `if`, `else`, and other blocks in Python.

#### Example

```python
def greet():
    print("Hello World!")

# Call the function
greet()
```

### Example with Multiple Functions

```python
def gtst():
    print("Learn.")
    print("Do exercise.")
    print("Ask questions.")


def Semir():
    print("Teach.")
    print("Answer Questions.")
    print("Prepare modules.")


Semir()
gtst()

# Output:
# Teach.
# Answer Questions.
# Prepare modules.
# Learn.
# Do exercise.
# Ask questions.
```

---

## Function Arguments

- Function arguments are used to take values while calling a function and insert those values inside the function.
- Arguments allow us to make functions more flexible and reusable.

### Example

```python
def add_numbers(num1, num2):
    total = num1 + num2
    print("Sum:", total)


add_numbers(5, 4)

# Output:
# Sum: 9
```

### Example with First Name and Last Name

```python
def users(fname, lname):
    print(f"Hello {fname}!, your father name is: {lname}")


users("Semir", "Nesredin")

# Output:
# Hello Semir!, your father name is: Nesredin
```

### Example with User Input

```python
def display(number1):
    print(f"The value you entered is: {number1}")


user_input = input("Enter number: ")
display(user_input)

# Output:
# Enter number: 23
# The value you entered is: 23
```

---

## Return Statement

- A Python function may or may not return a value.
- If we want our function to return some value to the function call, we use the `return` statement.

### Example

```python
def add(number1, number2):
    return number1 + number2


add(2, 3)

# Output:
# Nothing
```

The function returns a value, but because we did not print or store the returned value, nothing is displayed.

### Printing the Returned Value

```python
def add(number1, number2):
    return number1 + number2


print(add(2, 3))

# Output:
# 5
```

### Storing the Returned Value

```python
def add(number1, number2):
    return number1 + number2


total = add(2, 3)
print(total)

# Output:
# 5
```

### Returning a String

```python
def display(number1):
    return f"The value you entered is: {number1}"


user_input = input("Enter number: ")
print(display(user_input))
```

---

## Functions Calling Other Functions

- Many things we use in Python are functions.
- `print()` is a function.
- `input()` is a function.
- `len()` is a function.
- When we write `print(hello)`, we are calling the `print()` function and giving it an argument.

---

## Default Arguments

- You can give default values to function arguments.
- If no value is provided when calling the function, the default value is used.

```python
def display(number1=100):
    print(f"The value you entered is: {number1}")


display()

# Output:
# The value you entered is: 100
```

---

# Recursion

- Recursion is the process of defining something in terms of itself.
- In Python, a function can call other functions.
- It is also possible for a function to call itself.
- A function that calls itself is called a **recursive function**.

### Basic Structure

```python
def recurse():
    # ...
    recurse()
```

The function calls itself repeatedly until a condition tells it to stop.

---

## Recursive Function Example: Factorial

A factorial of a positive integer `n` is:

```text
n! = n × (n - 1) × (n - 2) × ... × 1
```

For example:

```text
3! = 3 × 2 × 1
   = 6
```

### Python Example

```python
def factorial(x):
    """This is a recursive function
    to find the factorial of an integer.
    """

    if x == 1:
        return 1
    else:
        return x * factorial(x - 1)


num = 3
print("The factorial of", num, "is", factorial(num))

# Output:
# The factorial of 3 is 6
```

---

## How the Recursive Factorial Works

For `factorial(3)`:

```text
factorial(3)             # 1st call with 3
3 * factorial(2)         # 2nd call with 2
3 * 2 * factorial(1)     # 3rd call with 1
3 * 2 * 1                # return from 3rd call
3 * 2                    # return from 2nd call
6                        # return from 1st call
```

The recursive calls continue until the **base condition** is reached:

```python
if x == 1:
    return 1
```

The function then returns the values back through the previous calls.

---

## Advantages of Recursion

1. Recursive functions can make code look clean and elegant.
2. A complex task can be broken down into simpler sub-problems using recursion.
3. Sequence generation can be easier with recursion than using some nested iteration.

## Disadvantages of Recursion

1. Sometimes the logic behind recursion is hard to follow.
2. Recursive calls can be expensive because they use additional memory and time.
3. Recursive functions can be harder to debug.

---

# Quick Summary

| Topic | Description |
|---|---|
| Function | A block of code that performs a specific task |
| Built-in Function | A function already provided by Python |
| User-defined Function | A function created by the programmer |
| `def` | Keyword used to define a function |
| Argument | A value passed to a function |
| `return` | Sends a value back from a function |
| Default Argument | An argument with a predefined value |
| Recursion | A function calling itself |
| Base Condition | The condition that stops recursion |
