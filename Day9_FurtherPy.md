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

# Lambda → Map / Filter

## Lambda Functions

- A lambda function is a small anonymous function.
- It is created using the `lambda` keyword.
- Lambda functions are useful when we need a short function for a simple operation.
- A lambda function can take any number of arguments but can contain only one expression.

### Syntax

```python
lambda arguments: expression
```

### Example

```python
square = lambda x: x * x

print(square(5))

# Output:
# 25
```

### Example with Two Arguments

```python
add = lambda x, y: x + y

print(add(5, 3))

# Output:
# 8
```

---

## Map Function

- `map()` is used to apply a function to every item in an iterable.
- It is commonly used together with a lambda function.

### Syntax

```python
map(function, iterable)
```

### Example

```python
numbers = [1, 2, 3, 4, 5]

squares = map(lambda x: x * x, numbers)

print(list(squares))

# Output:
# [1, 4, 9, 16, 25]
```

### Another Example

```python
numbers = [1, 2, 3, 4]

result = map(lambda x: x + 10, numbers)

print(list(result))

# Output:
# [11, 12, 13, 14]
```

---

## Filter Function

- `filter()` is used to select items from an iterable based on a condition.
- It keeps the items for which the function returns `True`.
- It is also commonly used with a lambda function.

### Syntax

```python
filter(function, iterable)
```

### Example

```python
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = filter(lambda x: x % 2 == 0, numbers)

print(list(even_numbers))

# Output:
# [2, 4, 6]
```

### Map vs Filter

| Function | Purpose |
|---|---|
| `map()` | Changes or transforms every item |
| `filter()` | Selects items based on a condition |
| `lambda` | Creates a small anonymous function |

---

# OOP & POP

## Object-Oriented Programming / OOP

- Python is an object-oriented programming language.
- This means many things in Python are objects.
- Objects can have **attributes (properties)** and **methods (actions/functions)**.

### Example: Computer

My computer can be considered an object.

**Attributes:**
- Name
- Size
- CPU
- RAM

**Behaviors / Methods:**
- Running games
- Playing music
- Displaying text

### Everything is an Object

In Python, many values are objects.

For example:

```python
a = 4

print(type(a))

# Output:
# <class 'int'>
```

Here:
- `a` is an object.
- `int` is a class.

---

## POP — Procedural-Oriented Programming

- Procedural-Oriented Programming (POP) organizes a program around procedures or functions.
- The main focus is on the sequence of instructions and functions used to perform tasks.
- Data and functions are generally handled separately.

### OOP vs POP

| OOP | POP |
|---|---|
| Focuses on objects | Focuses on procedures/functions |
| Data and behavior are grouped together | Data and functions are generally separate |
| Uses classes and objects | Uses functions/procedures |
| Supports concepts such as inheritance and encapsulation | Mainly focuses on step-by-step procedures |

---

# Class & Objects

## Python Class

- A class is simply a place where we create an object's attributes and behaviors.
- It is like a template.
- A class is a **blueprint** for objects.

### Syntax

```python
class Computer:
    # Creating Attributes
    name = ""
    cpu = ""
```

- After creating the blueprint, we can create objects based on the class.
- In the example above, we created a `Computer` class and gave it the attributes `name` and `cpu`.
- Conventionally, class names start with a capital letter.

---

## Creating Objects

- We can create many objects based on one class.
- Example objects:
  - `Nathan_Computer`
  - `Alemayew_Computer`

### Syntax

```text
variable = ClassName()
variable.attribute = value
```

### Example

```python
class Computer:
    name = ""
    cpu = ""


# Creating an object based on the blueprint
Nathan_Computer = Computer()

Nathan_Computer.name = "HP Laptop"
Nathan_Computer.cpu = "Intel Core i5"


# Creating another object
Alemayew_Computer = Computer()

Alemayew_Computer.name = "Dell Desktop"
Alemayew_Computer.cpu = "Intel Core i3"


print(
    f"Nathan's Computer Name is called {Nathan_Computer.name}.\n"
    f"It is {Nathan_Computer.cpu}"
)

# Output:
# Nathan's Computer Name is called HP Laptop.
# It is Intel Core i5
```

Based on a `Flower` class, we can create different objects such as:
- Daisy
- Sunflower
- Lily

---

## Checking the Type of an Object

```python
class Computer:
    name = ""
    cpu = ""


Nathan_Computer = Computer()

print(type(Nathan_Computer))

# Output:
# <class '__main__.Computer'>
```

Compare this with:

```python
a = 4

print(type(a))

# Output:
# <class 'int'>
```

- `Nathan_Computer` and `a` are objects.
- `Computer` and `int` are classes.

---

## Giving Behaviors — Creating Methods

- Functions defined inside a class are called **methods**.
- Methods are used to give objects behaviors.
- Methods normally use `self` to refer to the current object.

### Example

```python
class Computer:
    # Creating Attributes
    name = ""
    cpu = ""

    # Creating Behavior
    def run(self):
        return "BIOS is Good!"


# Creating an object
Nathan_Computer = Computer()

Nathan_Computer.name = "HP Laptop"
Nathan_Computer.cpu = "Intel Core i5"

print(f"Running: {Nathan_Computer.run()}")

# Output:
# Running: BIOS is Good!
```

### What is `self`?

- `self` refers to the current object.
- It allows the method to access the object's attributes and other methods.

---

# Python Constructors

- A constructor is a special method that is called whenever a new object is created.
- In Python, the constructor method is `__init__()`.
- It is commonly used to initialize object attributes.

### Example

```python
class Bike:

    def __init__(self, name=""):
        self.name = name


bike1 = Bike()

print(bike1.name)

# Output:
#
```

We can also provide a value while creating the object:

```python
class Bike:

    def __init__(self, name=""):
        self.name = name


bike1 = Bike("Mountain Bike")

print(bike1.name)

# Output:
# Mountain Bike
```

---

## Constructor with Multiple Attributes

```python
class Computer:

    def __init__(self, name, cpu):
        self.name = name
        self.cpu = cpu

    # Creating Behavior
    def run(self):
        return "BIOS is Good!"


Nathan_Computer = Computer("HP Laptop", "Intel i5")

Alemayew_Computer = Computer(
    "Dell Desktop",
    "Intel Core i3"
)


print(
    f"Nathan's Computer Name is called "
    f"{Nathan_Computer.name}.\n"
    f"It is {Nathan_Computer.cpu}"
)

# Output:
# Nathan's Computer Name is called HP Laptop.
# It is Intel i5
```

---

# Python Inheritance

- Inheritance is a way of creating a new class with some properties and behaviors of an existing class.
- The existing class is called the **base class** or **parent class**.
- The new class is called the **derived class** or **child class**.

### Syntax

```python
class NewClass(OldClass):
    # ...
```

### Example

```python
# Base class
class Animal:

    def eat(self):
        print("I can eat!")

    def sleep(self):
        print("I can sleep!")


# Derived class
class Dog(Animal):

    def bark(self):
        print("I can bark! Woof woof!")


# Create object of the Dog class
dog1 = Dog()

# Calling members of the base class
dog1.eat()
dog1.sleep()

# Calling member of the derived class
dog1.bark()

# Output:
# I can eat!
# I can sleep!
# I can bark! Woof woof!
```

The `Dog` class inherits the methods of the `Animal` class and can also have its own methods.

---

# Python Encapsulation

- Encapsulation is a feature of OOP.
- It refers to bundling attributes and methods inside a single class.
- Encapsulation allows for better control and protection of data.
- Data can be accessed and modified through specified methods.

### Example

```python
class Computer:

    def __init__(self, name, cpu):
        self.name = name
        self.cpu = cpu
        self.price = 1000

    # Creating Behavior
    def run(self):
        return "BIOS is Good!"

    def setprice(self, birr):
        self.price = birr


# Creating objects
Nathan_Computer = Computer("HP Laptop", "Intel i5")

Alemayew_Computer = Computer(
    "Dell Desktop",
    "Intel Core i3"
)


print(
    f"Nathan Computer price is: "
    f"{Nathan_Computer.price} birr."
)

# Change the price
Nathan_Computer.setprice(2000)

print(
    f"Nathan Computer price is: "
    f"{Nathan_Computer.price} birr."
)

# Output:
# Nathan Computer price is: 1000 birr.
# Nathan Computer price is: 2000 birr.
```

---

# User-built Module

- A module is a Python file containing code that can be reused in another Python program.
- We can create our own modules instead of putting all code into one file.
- User-built modules help organize programs and make code reusable.

## Creating a User-built Module

Suppose we create a file called:

```text
calculator.py
```

Inside `calculator.py`:

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b
```

Now create another file:

```text
main.py
```

We can import our module:

```python
import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))

# Output:
# 15
# 5
```

---

## Importing Specific Functions

Instead of importing the entire module, we can import specific functions.

```python
from calculator import add

print(add(10, 5))

# Output:
# 15
```

We can also import multiple functions:

```python
from calculator import add, subtract

print(add(10, 5))
print(subtract(10, 5))
```

---

## Using an Alias

We can give a module a shorter name using `as`.

```python
import calculator as calc

print(calc.add(10, 5))
```

---

# Package Installing

- As we have seen package installing in the Linux tutorial, we use `pip` to install Python packages.
- On the terminal:

```bash
pip install package_name
```

Example:

```bash
pip install requests
```

---

# Package Using

- Python has many packages that we can use in our programs.
- We use `import` to bring a package or module into our program.

Example:

```python
import sys

a = sys.argv[1]

print(a)
```

Here:
- We imported the `sys` module.
- From the `sys` module, we used `argv`.
- `argv` is used to access command-line arguments.

### Command-line Example

```bash
python gtst.py Semir
```

Example program:

```python
import sys

name = sys.argv[1]

print(f"Hello {name}!")
```

Output:

```text
Hello Semir!
```

- Each package can have its own classes, functions, and methods.
- We need to study the documentation and structure of each package to use it correctly.
- Examples of Python packages/frameworks used in different areas include Django, Flask, pandas, and NumPy.

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
| Lambda | A small anonymous function |
| `map()` | Applies a function to every item |
| `filter()` | Selects items based on a condition |
| OOP | Object-Oriented Programming |
| POP | Procedural-Oriented Programming |
| Class | A blueprint for creating objects |
| Object | An instance created from a class |
| Attribute | A property/data belonging to an object |
| Method | A function defined inside a class |
| `self` | Refers to the current object |
| Constructor | `__init__()` method used to initialize objects |
| Inheritance | Creating a new class from an existing class |
| Encapsulation | Bundling data and methods inside a class |
| Module | A Python file containing reusable code |
| `import` | Used to import a module or package |
| `pip` | Tool used to install Python packages |

---

@innovatorsemir