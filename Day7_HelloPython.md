# Programming & Python Notes

## What is Programming Language?

* A programming language is a language that helps us communicate with computers.
* Computers cannot directly understand human languages such as English, French, Amharic, Arabic, etc.
* Humans have many languages:

  * English
  * French
  * Amharic
  * Arabic
* Computers also have many programming languages:

  * Assembly
  * C
  * C++
  * Java
  * JavaScript
  * Python
  * Ruby
  * Perl
  * Go
* A programming language helps us write **programs** that computers can understand and execute.

---

## What is a Program?

* A **program** is an algorithm expressed in a programming language.
* An **algorithm** is a detailed sequence of actions used to accomplish a specific task.
* The word algorithm is associated with the Persian mathematician **Al-Khwarizmi**.
* Technically, an algorithm must reach a result after a finite number of steps.
* A program uses these steps to perform a specific task correctly.

---

## Pseudocode

* **Pseudocode** is a simplified and structured way of writing programming logic in plain language.
* It does not follow the exact syntax of a specific programming language.
* It uses short and clear statements to describe each step of a program.
* Pseudocode is useful for:

  * Understanding algorithms
  * Planning programs
  * Explaining programming logic
  * Designing complex solutions before writing actual code
* You can use any informal language. The main goal is to break the process into clear steps.

### Example: Simple Login Process

```text
BEGIN
    PROMPT user for username
    PROMPT user for password

    IF username and password match
        DISPLAY "Login Successful"
    ELSE
        DISPLAY "Login Failed"
END
```

---

## Pseudocode Example: Adding Two Numbers

A program that accepts two numbers from the user and displays the result:

```text
BEGIN
    DISPLAY "Enter the first number:"
    INPUT number1

    DISPLAY "Enter the second number:"
    INPUT number2

    result = number1 + number2

    DISPLAY "The result is: ", result
END
```

---

## Advanced Pseudocode: Calculator

Adding multiple operations to create a simple calculator:

```text
BEGIN

    DISPLAY "Enter the first number:"
    INPUT number1

    DISPLAY "Enter the second number:"
    INPUT number2

    DISPLAY "Choose an operation (+, -, *, /):"
    INPUT operation

    IF operation is "+"
        result = number1 + number2
        DISPLAY "The result is: ", result

    ELSE IF operation is "-"
        result = number1 - number2
        DISPLAY "The result is: ", result

    ELSE IF operation is "*"
        result = number1 * number2
        DISPLAY "The result is: ", result

    ELSE IF operation is "/"
        IF number2 is not 0
            result = number1 / number2
            DISPLAY "The result is: ", result
        ELSE
            DISPLAY "Error: Division by zero is not allowed."

    ELSE
        DISPLAY "Invalid operation selected."

END
```

---

# Evolution of I/O (Input / Output)

* Early in the history of computing, programs were submitted using **punch cards** containing all the data they required.
* Programs were executed together with other programs that used the same libraries.
* Output was commonly produced using a **line printer**.
* Later, **interactive processing** was introduced.
* Interactive processing allowed users to provide data while the program was running.
* This normally took place using a **Question & Answer** format.

### Basic I/O Concept

```text
Input
  ↓
Processing
  ↓
Output
```

---

# Generations of Computers

## 1. First Generation

**Technology:** Vacuum Tubes

**Input/Output:**

* Punch cards
* Line printers

Characteristics:

* Very large computers
* Consumed a lot of electricity
* Generated significant heat
* Very expensive
* Programs took a long time to prepare
* A new program could take days or weeks to set up

---

## 2. Second Generation

**Technology:** Transistors

* Transistors replaced vacuum tubes.
* Programming became more practical.
* Assembly language became widely used.

### Transistor

A **transistor** is a small electronic device that can be used for switching and amplifying electrical signals.

The invention of the transistor was one of the most important developments in computing and electronics.

---

## 3. Third Generation

**Technology:** Integrated Circuits (ICs)

Programming languages included:

* BASIC
* COBOL
* Pascal
* FORTRAN
* C
* C++
* Perl
* Ada

Integrated circuits allowed many electronic components to be placed on a single chip.

---

## 4. Fourth Generation

**Technology:** Microprocessors

Examples of languages and technologies:

* Python
* SQL
* MATLAB

Microprocessors made it possible to build smaller, cheaper, and more powerful computers.

---

## 5. Fifth Generation

**Technology/Focus:** Artificial Intelligence

The fifth generation focuses heavily on:

* Artificial Intelligence
* Machine Learning
* Natural Language Processing
* Intelligent systems
* Robotics

---

# Types of Programming Languages

Computers ultimately understand **machine code**, which is represented using binary values such as:

```text
0
1
```

Humans find machine code difficult to read and write.

Programming languages can therefore be classified based on how close they are to the hardware or to human language.

The two broad categories are:

1. Low-level programming languages
2. High-level programming languages

> Note: Being "lower level" does not automatically mean a language is always faster. Performance depends on the language, compiler/interpreter, implementation, hardware, and program.

---

# A) Low-Level Programming Languages

* Low-level languages are closer to the computer's hardware.
* They provide more direct control over hardware resources.
* They are generally more difficult for humans to read and write.
* Examples include:

  * Machine code
  * Assembly language

### Example

```text
LOAD r1,b
LOAD r2,h
MUL r1,r2
DIV r1,#2
RET
```

Possible machine code representation:

```text
0001001001000101
0010010011101100
10101101001...
```

---

# B) High-Level Programming Languages

* High-level languages are designed to be easier for humans to read and write.
* They hide many hardware-level details.
* Examples include:

  * Python
  * C++
  * Java
  * JavaScript
  * C#
  * Ruby
  * Go

### Example

```java
class Triangle {
    float surface() {
        return b * h / 2;
    }
}
```

The high-level program is eventually translated into lower-level instructions that the computer can execute.

---

# How Do High-Level Languages Work?

Computers ultimately execute machine instructions.

So, if we write programs using high-level languages such as Python, Java, or C++, how does the computer understand them?

There are several approaches, including:

1. Compilation
2. Interpretation
3. Hybrid approaches

---

## 1. Compiler

A **compiler** translates source code into another form that can be executed by a computer or runtime environment.

For example, Java source code can be compiled into Java bytecode.

```text
Source Code
    ↓
Hello.java
    ↓
Compile
    ↓
Bytecode
    ↓
Hello.class
    ↓
JVM executes bytecode
    ↓
Output
```

Examples of compiled languages include:

* C
* C++
* Rust
* Go

Java is commonly compiled to bytecode and then executed by the Java Virtual Machine (JVM).

---

## 2. Interpreter

An **interpreter** executes program instructions through a runtime system rather than requiring the same traditional native compilation process.

Python programs are commonly described as interpreted because Python source code is executed by the Python interpreter.

```text
Source Code
    ↓
Hello.py
    ↓
Python Interpreter
    ↓
Output
```

### Example

```python
print("Hello, world!")
```

Output:

```text
Hello, world!
```

> Modern language implementations can combine compilation, interpretation, bytecode, and runtime optimization. The simple "compiler vs interpreter" distinction is useful for beginners but does not describe every implementation detail.

---

# Uses of Programming Languages

Programming languages are used in many areas, including:

* Android application development
* Website development
* Machine learning
* Artificial Intelligence
* Game development
* Big data technologies
* Desktop software development
* Embedded systems
* Robotics
* Automation
* Cybersecurity tools
* Scientific computing
* Data analysis
* Cloud applications

---

# What is Python?

**Python** is a high-level, general-purpose programming language known for its readable syntax and large ecosystem.

Python is commonly used for:

* Web development
* Data analysis
* Data visualization
* Machine learning
* Artificial Intelligence
* Automation
* Scientific computing
* Scripting
* Cybersecurity
* Game development

Python is popular because its syntax is relatively simple and readable.

### Comparing Output Syntax

Python:

```python
print("Hello")
```

C++:

```cpp
cout << "Hello";
```

Java:

```java
System.out.println("Hello");
```

---

# History of Python

* Python was created by **Guido van Rossum**.
* Development began in the late 1980s.
* The first public release of Python was made in 1991.
* Python was influenced by several languages, including:

  * ABC
  * Modula-3
  * C
  * C++
  * ALGOL
  * Smalltalk
  * Unix shell languages
* Python later became an open-source project maintained by a large global community.
* Guido van Rossum played a major role in Python's development and served as its original creator and long-time leader.

---

# Why is Python Used in Cybersecurity?

Python is widely used in cybersecurity because it provides:

* Easy-to-read syntax
* Rapid development
* Networking libraries
* Automation capabilities
* File and system interaction
* Support for APIs
* Large numbers of third-party libraries
* Easy scripting for repetitive tasks

Python can be used for legitimate cybersecurity activities such as:

* Network analysis
* Log analysis
* Security automation
* Vulnerability testing
* Penetration testing
* Digital forensics
* Security tool development

> Cybersecurity tools should only be used on systems and networks that you own or have explicit permission to test.

---

# Uses of Python

Python is used in many fields.

### 1. Data Visualization

Libraries include:

* Matplotlib
* Plotly
* Seaborn

### 2. Data Analysis

Libraries include:

* Pandas
* NumPy

### 3. Machine Learning

Libraries and frameworks include:

* Scikit-learn
* TensorFlow
* PyTorch

### 4. Artificial Intelligence

Python is widely used for:

* AI applications
* Natural Language Processing
* Computer Vision
* Machine Learning

### 5. Backend Web Development

Popular frameworks include:

* Django
* Flask
* FastAPI

### 6. Game Development

Libraries/frameworks include:

* Pygame

### 7. Automation

Python can automate repetitive tasks such as:

* File management
* Data processing
* System administration
* Web automation

### 8. Cybersecurity

Python can be used for:

* Security scripts
* Network analysis
* Automation
* Penetration testing
* Log analysis

---

# How to Install Python

## Windows

Download Python from the official Python website:

https://www.python.org/

After installation, verify it using:

```bash
python --version
```

or:

```bash
py --version
```

---

## Linux

Python 3 is commonly available on Linux systems.

Check whether Python is installed:

```bash
python3 --version
```

On Debian-based systems, Python 3 can be installed using:

```bash
sudo apt update
sudo apt install python3
```

---

# What is an IDE?

**IDE** stands for **Integrated Development Environment**.

An IDE is software that provides tools for writing, running, debugging, and managing programs.

An IDE may include:

* Code editor
* Compiler/interpreter integration
* Debugger
* Terminal
* Project management
* Code completion

Examples:

* PyCharm
* Visual Studio
* IntelliJ IDEA

---

# What is a Code Editor?

A **code editor** is software designed primarily for writing and editing source code.

Examples:

* Visual Studio Code
* Sublime Text
* Vim
* Neovim

Some code editors can be extended with:

* Compilers
* Interpreters
* Debuggers
* Linters
* Extensions

---

# Using VS Code on Linux

After installing Python:

1. Install Visual Studio Code.
2. Open VS Code.
3. Install the **Python extension**.
4. Create a Python file.
5. Save the file with the `.py` extension.
6. Run the program using the Run button or terminal.

Example:

```bash
python3 program.py
```

---

# Creating a Python Script File

Python files normally use the `.py` extension.

Example:

```text
hello.py
```

Inside the file:

```python
print("Hello, world!")
```

Run it from the terminal:

```bash
python3 hello.py
```

Output:

```text
Hello, world!
```

---

# Outputs and Comments

## Output

In Python, the `print()` function is used to display output.

### Syntax

```python
print(object, sep=' ', end='\n')
```

### Example

```python
print("Python is powerful")
```

Output:

```text
Python is powerful
```

---

## Printing Multiple Values

```python
name = "Semir"
age = 20

print("Name:", name)
print("Age:", age)
```

Output:

```text
Name: Semir
Age: 20
```

---

# The `end` Parameter

By default, `print()` ends with a newline.

Example:

```python
print("Good Morning!")
print("It is rainy today")
```

Output:

```text
Good Morning!
It is rainy today
```

We can change this behavior using `end`.

```python
print("Good Morning!", end=" ")
print("It is rainy today")
```

Output:

```text
Good Morning! It is rainy today
```

---

# New Line `\n`

`\n` represents a new line.

Example:

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

---

# Tab `\t`

`\t` represents a tab space.

Example:

```python
print("Name:\tSemir")
print("Age:\t20")
```

Output:

```text
Name:   Semir
Age:    20
```

---

# The `sep` Parameter

The `sep` parameter controls the separator between multiple values.

Example:

```python
print("New Year", 2023, "See you soon!", sep=".")
```

Output:

```text
New Year.2023.See you soon!
```

Another example:

```python
print("2026", "08", "29", sep="-")
```

Output:

```text
2026-08-29
```

---

# Comments

Comments are notes written inside source code.

They are useful for:

* Explaining code
* Remembering what a section does
* Making code easier for others to understand
* Temporarily disabling code

Comments are not executed as normal Python statements.

### Single-Line Comment

```python
# This is a comment
print("Hello")
```

### Example

```python
# Display the user's name
name = "Semir"
print(name)
```

---

# Taking User Input

Python uses the `input()` function to receive input from the user.

Example:

```python
num = input("Enter a number: ")

print("You entered:", num)
print("Data type of num:", type(num))
```

If the user enters:

```text
10
```

The output will be similar to:

```text
You entered: 10
Data type of num: <class 'str'>
```

This is because `input()` returns a **string** by default.

---

# Converting User Input

If we want a number, we can convert the input.

### Integer

```python
num = int(input("Enter a number: "))

print("You entered:", num)
print("Data type:", type(num))
```

### Float

```python
price = float(input("Enter the price: "))

print("Price:", price)
```

---

# Python Keywords

**Keywords** are reserved words that have special meanings in Python.

Examples include:

```text
False
None
True
and
as
assert
async
await
break
case
class
continue
def
del
elif
else
except
finally
for
from
global
if
import
in
is
lambda
match
nonlocal
not
or
pass
raise
return
try
while
with
yield
```

You can see Python's keywords using:

```python
import keyword

print(keyword.kwlist)
```

---

# Variables and Data Types

## Variables

A variable is a name that refers to a value stored by a program.

Example:

```python
number = 10
```

Here:

* `number` is the variable name.
* `10` is the value.

We can print the variable:

```python
number = 10

print(number)
```

Output:

```text
10
```

---

# Variable Assignment

The process of assigning a value to a variable is called **assignment**.

Example:

```python
age = 20
name = "Semir"
```

The variables now refer to the assigned values.

---

# Changing a Variable

Python variables can be reassigned.

```python
age = 10

print("You are", age, "years old!")

age = 22

print("You are", age, "years old!")
```

Output:

```text
You are 10 years old!
You are 22 years old!
```

---

# F-Strings

F-strings provide a convenient way to insert variables into strings.

### Syntax

```python
f"Your text {variable}"
```

Example:

```python
name = "Semir"

print(f"Your name is {name}.")
```

Output:

```text
Your name is Semir.
```

Another example:

```python
name = "Semir"
age = 20

print(f"My name is {name} and I am {age} years old.")
```

---

# Variable Naming Rules

When naming variables in Python:

### 1. Do not use spaces

Incorrect:

```python
my name = "Nathan"
```

Correct:

```python
my_name = "Nathan"
```

### 2. Do not start a variable name with a number

Incorrect:

```python
1name = "Nathan"
```

Correct:

```python
name1 = "Nathan"
```

### 3. Use meaningful names

Instead of:

```python
x = 20
```

Prefer:

```python
age = 20
```

### 4. Variable names are case-sensitive

These are different variables:

```python
name = "Semir"
Name = "Nathan"
```

---

# Python Data Types

A **data type** defines the kind of value stored or represented by a variable.

Common Python data types include:

| Category | Data Types                         |
| -------- | ---------------------------------- |
| Numeric  | `int`, `float`, `complex`          |
| Text     | `str`                              |
| Sequence | `list`, `tuple`, `range`           |
| Mapping  | `dict`                             |
| Boolean  | `bool`                             |
| Set      | `set`, `frozenset`                 |
| Binary   | `bytes`, `bytearray`, `memoryview` |
| None     | `NoneType`                         |

---

# A) Numeric Data Types

## Integer (`int`)

An integer is a whole number without a decimal point.

Examples:

```python
age = 20
year = 2026
temperature = -5
```

---

## Float (`float`)

A float represents a number with a decimal point.

Examples:

```python
price = 99.99
height = 1.75
temperature = -2.5
```

---

## Complex (`complex`)

Complex numbers contain a real part and an imaginary part.

Example:

```python
z = 3 + 4j

print(z)
```

Output:

```text
(3+4j)
```

---

# Checking the Data Type

Python provides the `type()` function to identify the type of a value.

```python
age = 20
name = "Semir"
price = 99.99

print(type(age))
print(type(name))
print(type(price))
```

Output:

```text
<class 'int'>
<class 'str'>
<class 'float'>
```

---

# B) String Data Type

A **string** is a sequence of characters.

Strings can be created using single or double quotes.

```python
name = "Semir"
country = 'Ethiopia'
```

You can also use triple quotes for multi-line strings:

```python
message = """Hello
Welcome to Python
Programming is fun!"""
```

---

# String Operations

### Concatenation

```python
first_name = "Semir"
last_name = "Nesredin"

full_name = first_name + " " + last_name

print(full_name)
```

Output:

```text
Semir Nesredin
```

### String Length

```python
name = "Python"

print(len(name))
```

Output:

```text
6
```

### Accessing Characters

Strings use zero-based indexing.

```python
language = "Python"

print(language[0])
print(language[1])
print(language[5])
```

Output:

```text
P
y
n
```

---

# C) Sequence Data Types

Python has several sequence types:

* List
* Tuple
* Range
* String

---

# 1. List

A **list** is an ordered and mutable collection of items.

Lists are created using square brackets `[]`.

Example:

```python
languages = ["Swift", "Java", "Python"]
```

A list can contain different data types:

```python
items = ["Semir", 20, 99.5, True]
```

---

## Accessing List Elements

List indexing starts at `0`.

```python
languages = ["Swift", "Java", "Python"]

print(languages[0])
print(languages[2])
```

Output:

```text
Swift
Python
```

---

## Printing the Entire List

```python
languages = ["Swift", "Java", "Python"]

print(languages)
```

Output:

```text
['Swift', 'Java', 'Python']
```

---

## Adding an Item to a List

The `append()` method adds an item to the end of a list.

```python
languages = ["Swift", "Java", "Python"]

languages.append("Amharic")

print(languages)
```

Output:

```text
['Swift', 'Java', 'Python', 'Amharic']
```

---

## Modifying a List Element

```python
languages = ["Swift", "Java", "Python"]

languages[0] = "C++"

print(languages)
```

Output:

```text
['C++', 'Java', 'Python']
```

---

## Removing an Item

```python
languages = ["Swift", "Java", "Python"]

languages.remove("Java")

print(languages)
```

Output:

```text
['Swift', 'Python']
```

---

# 2. Tuple

A **tuple** is an ordered collection of items.

The main difference between a list and a tuple is that a tuple is **immutable**.

Once a tuple is created, its elements cannot normally be changed.

Tuples use parentheses `()`.

Example:

```python
product = ("Microsoft", "Xbox", 499.99)
```

---

## Accessing Tuple Elements

```python
product = ("Microsoft", "Xbox", 499.99)

print(product[0])
print(product[1])
print(product[2])
```

Output:

```text
Microsoft
Xbox
499.99
```

---

## Tuple Immutability

This will cause an error:

```python
product = ("Microsoft", "Xbox", 499.99)

product[1] = "PlayStation"
```

Tuples do not support changing individual elements after creation.

---

# List vs Tuple

| Feature             | List                   | Tuple             |
| ------------------- | ---------------------- | ----------------- |
| Syntax              | `[]`                   | `()`              |
| Ordered             | Yes                    | Yes               |
| Mutable             | Yes                    | No                |
| Can modify elements | Yes                    | No                |
| Common use          | Changeable collections | Fixed collections |

---

# 3. Range

A `range` represents a sequence of numbers.

Example:

```python
numbers = range(5)

print(list(numbers))
```

Output:

```text
[0, 1, 2, 3, 4]
```

Another example:

```python
numbers = range(1, 6)

print(list(numbers))
```

Output:

```text
[1, 2, 3, 4, 5]
```

---

# D) Dictionary Data Type

A **dictionary** stores data in **key-value pairs**.

Dictionaries are created using curly braces `{}`.

Example:

```python
capital_city = {
    "Nepal": "Kathmandu",
    "Italy": "Rome",
    "England": "London"
}
```

Here:

* `"Nepal"` is a key.
* `"Kathmandu"` is its value.
* `"Italy"` is a key.
* `"Rome"` is its value.
* `"England"` is a key.
* `"London"` is its value.

---

# Accessing Dictionary Values

We use a key to retrieve its corresponding value.

```python
capital_city = {
    "Nepal": "Kathmandu",
    "Italy": "Rome",
    "England": "London"
}

print(capital_city["Nepal"])
```

Output:

```text
Kathmandu
```

---

## Invalid Dictionary Key

This will produce a `KeyError` because `"Kathmandu"` is a value, not a key:

```python
capital_city = {
    "Nepal": "Kathmandu",
    "Italy": "Rome",
    "England": "London"
}

print(capital_city["Kathmandu"])
```

---

# Adding Data to a Dictionary

```python
fruits = {
    "apple": 10,
    "banana": 15,
    "pineapple": 20
}

fruits["orange"] = 25

print(fruits)
```

---

# Modifying Dictionary Data

```python
fruits = {
    "apple": 10,
    "banana": 15,
    "pineapple": 20
}

fruits["apple"] = 20

print(fruits)
```

---

# Removing Dictionary Data

```python
fruits = {
    "apple": 10,
    "banana": 15,
    "pineapple": 20
}

del fruits["banana"]

print(fruits)
```

---

# E) Boolean Data Type

The Boolean data type represents one of two values:

```python
True
False
```

Example:

```python
is_student = True
is_graduated = False

print(is_student)
print(is_graduated)
```

Output:

```text
True
False
```

Booleans are commonly used with conditions.

```python
age = 20

is_adult = age >= 18

print(is_adult)
```

Output:

```text
True
```

---

# F) Set Data Type

A **set** is an unordered collection of unique values.

Sets are created using `{}`.

Example:

```python
numbers = {1, 2, 3, 4, 5}

print(numbers)
```

A set automatically removes duplicate values:

```python
numbers = {1, 2, 2, 3, 3, 4}

print(numbers)
```

The result contains only unique values.

---

# Frozenset

A `frozenset` is an immutable version of a set.

Example:

```python
numbers = frozenset([1, 2, 3, 4])

print(numbers)
```

Unlike a normal set, a frozenset cannot be modified.

---

# None

Python has a special value called `None`.

It represents the absence of a value.

Example:

```python
result = None

print(result)
```

Output:

```text
None
```

---

# Basic Python Data Type Summary

```text
int       → Whole numbers
float     → Decimal numbers
complex   → Complex numbers
str       → Text
list      → Ordered, mutable collection
tuple     → Ordered, immutable collection
range     → Sequence of numbers
dict      → Key-value pairs
bool      → True or False
set       → Unique unordered collection
frozenset → Immutable set
None      → No value
```

---

# Basic Python Example

Here is a small program that combines several concepts:

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))

print()
print("Hello,", name)
print(f"You are {age} years old.")

if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```

---

# Important Python Concepts to Learn Next

After variables and basic data types, the next important Python topics are:

1. Operators
2. Type conversion
3. Conditional statements
4. `if`, `elif`, and `else`
5. Comparison operators
6. Logical operators
7. Loops
8. `for` loops
9. `while` loops
10. `break`
11. `continue`
12. Functions
13. Parameters and arguments
14. Return values
15. Lists and list methods
16. Tuples
17. Sets
18. Dictionaries
19. String methods
20. Exception handling
21. File handling
22. Modules and packages
23. Object-Oriented Programming
24. Classes and objects
25. Inheritance
26. Encapsulation
27. Polymorphism
28. Virtual environments
29. External libraries
30. Projects and practical applications

---

# Quick Revision

### Programming Language

A language used to communicate instructions to a computer.

### Program

An algorithm implemented using a programming language.

### Algorithm

A finite sequence of steps used to solve a problem.

### Pseudocode

A simple way to describe programming logic without following a specific programming language's syntax.

### Low-Level Language

A language close to computer hardware.

Examples:

* Machine code
* Assembly

### High-Level Language

A language designed to be easier for humans to understand.

Examples:

* Python
* Java
* C++
* JavaScript

### Python

A high-level, general-purpose programming language known for its readable syntax and broad range of applications.

### Variable

A name that refers to a value.

### Data Type

Describes the kind of value being represented.

### List

An ordered and mutable collection.

### Tuple

An ordered and immutable collection.

### Dictionary

A collection of key-value pairs.

### Set

A collection of unique values.

### Boolean

A value that is either `True` or `False`.

---

# Practice

## Exercise 1: Variables

Create variables for:

* Your name
* Your age
* Your university
* Your department

Then print them.

---

## Exercise 2: User Input

Write a program that asks the user for:

* Name
* Age
* Country

Then display the information.

---

## Exercise 3: Calculator

Write a Python program that:

1. Takes two numbers from the user.
2. Asks for an operation.
3. Performs:

   * Addition
   * Subtraction
   * Multiplication
   * Division
4. Displays the result.
5. Prevents division by zero.

---

## Exercise 4: Lists

Create a list containing five programming languages.

Then:

* Print the entire list.
* Print the first language.
* Print the last language.
* Add another language.
* Remove one language.

---

## Exercise 5: Dictionary

Create a dictionary containing:

```text
name
age
university
department
```

Then print each value using its key.

---

# End of Notes

These notes cover the fundamentals of:

* Programming languages
* Programs
* Algorithms
* Pseudocode
* Computer generations
* Low-level and high-level languages
* Compilers and interpreters
* Python
* Python history
* Python installation
* IDEs and code editors
* Python scripts
* Output
* Comments
* User input
* Keywords
* Variables
* Variable naming
* Data types
* Strings
* Lists
* Tuples
* Dictionaries
* Sets
* Booleans
* `None`
* Basic Python practice

---

@innovatorsemir