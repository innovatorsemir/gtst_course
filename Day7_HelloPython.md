# Programming Languages and Python Basics

## What Is a Programming Language?

A **programming language** is a language used to communicate instructions to a computer.

Humans use natural languages such as:

- English
- French
- Amharic
- Arabic
- Spanish

Computers, however, cannot directly understand human languages. At the lowest level, computers work with **binary instructions**, represented using `0` and `1`.

Programming languages allow humans to write instructions in a more understandable form.

Examples of programming languages include:

- Assembly
- C
- C++
- Java
- JavaScript
- Python
- Ruby
- Perl
- Go

Programming languages help us write **programs** that instruct computers to perform specific tasks.

---

# What Is a Program?

A **program** is a set of instructions written in a programming language that tells a computer how to perform a specific task.

A program is usually based on an **algorithm**.

## What Is an Algorithm?

An **algorithm** is a detailed, step-by-step sequence of instructions used to solve a problem or accomplish a task.

The word **algorithm** is historically associated with the name of the Persian mathematician **Muhammad ibn Musa al-Khwarizmi**.

A proper algorithm should:

- Have clear steps.
- Solve a specific problem.
- Reach a result after a finite number of steps.
- Produce the expected output when the instructions are followed correctly.

Example:

### Algorithm for Making Tea

```text
START

Boil water
Put tea into a cup
Pour hot water into the cup
Wait for a few minutes
Serve the tea

END
```

A program is essentially an algorithm expressed using a programming language.

---

# Pseudocode

**Pseudocode** is a simplified and structured way of writing program logic without following the exact syntax of a specific programming language.

It helps programmers:

- Understand the logic of a program.
- Plan solutions before writing actual code.
- Break complex problems into smaller steps.
- Focus on the algorithm instead of programming syntax.

Pseudocode can use simple English or another understandable language.

The main goal is to clearly describe the process.

---

## Example: Simple Login Process

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

# Example: Adding Two Numbers

The following pseudocode accepts two numbers and displays their sum.

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

# Advanced Calculator Pseudocode

The following example allows the user to perform multiple mathematical operations.

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

# Evolution of Input and Output

## Early Computing

During the early history of computing, programs and their input data were often submitted using **punch cards**.

A program could be prepared together with the data it needed and then processed by the computer.

Output was often produced using devices such as:

- Line printers
- Paper printers
- Punch cards

This process was usually called **batch processing**.

Users generally could not interact directly with the program while it was running.

---

## Interactive Processing

Later developments introduced **interactive processing**.

This allowed users to provide input while the program was running.

For example:

```text
Enter your username:
```

The user enters information:

```text
semir
```

Then the program continues:

```text
Enter your password:
```

This type of interaction is common in modern applications.

Examples include:

- Command-line programs.
- Login systems.
- Websites.
- Mobile applications.
- Desktop software.

---

# Generations of Computers

Computer history is commonly divided into generations based on major technological developments.

## 1. First Generation

### Main Technology

```text
Vacuum Tubes
```

Characteristics:

- Very large computers.
- Consumed large amounts of electricity.
- Generated significant heat.
- Programming was difficult.
- Punch cards were commonly used for input.

Programming was often done using machine-level instructions.

Computers were generally designed to perform limited tasks, and preparing programs could take a significant amount of time.

---

## 2. Second Generation

### Main Technology

```text
Transistors
```

Transistors replaced vacuum tubes.

Advantages included:

- Smaller size.
- Lower power consumption.
- Less heat.
- Greater reliability.
- Faster processing.

Assembly language became an important programming method during this era, while higher-level languages also began to develop and grow.

A **transistor** is a small electronic device that can control electrical signals and is one of the fundamental building blocks of modern electronics.

---

## 3. Third Generation

### Main Technology

```text
Integrated Circuits
```

An integrated circuit combines many electronic components into a small chip.

Computers became:

- Smaller.
- Faster.
- More reliable.
- More widely available.

Programming languages such as the following became widely used or continued to develop during the broader era of integrated-circuit computing:

- BASIC
- COBOL
- Pascal
- FORTRAN
- C
- Ada

---

## 4. Fourth Generation

### Main Technology

```text
Microprocessors
```

A microprocessor placed much of the computer's central processing capability onto a single integrated circuit.

This generation led to the growth of:

- Personal computers.
- Modern operating systems.
- Computer networking.
- Modern software development.

Languages and technologies such as Python, SQL, MATLAB, and many others became popular during the broader modern computing era.

---

## 5. Fifth Generation

The fifth generation is commonly associated with advanced computing technologies such as:

- Artificial Intelligence.
- Machine Learning.
- Natural Language Processing.
- Expert Systems.
- Robotics.
- Advanced parallel processing.

Modern AI systems are part of the continuing development of this generation.

---

# Types of Programming Languages

Computers ultimately execute instructions in machine-readable form.

Humans generally find binary instructions difficult to read.

Programming languages are often discussed based on their level of abstraction from the hardware.

Two broad categories are:

1. Low-level programming languages.
2. High-level programming languages.

---

# A) Low-Level Programming Languages

Low-level languages are closer to the computer's hardware and machine instructions.

Examples include:

- Machine language.
- Assembly language.

C is often considered a **low-level or middle-level language** because it provides relatively direct access to memory and hardware concepts while still offering high-level programming features.

Example of assembly-style instructions:

```text
LOAD r1, b
LOAD r2, h
MUL r1, r2
DIV r1, #2
RET
```

Machine code may look like:

```text
0001001001000101
0010010011101100
10101101001...
```

Advantages of low-level programming include:

- Greater control over hardware.
- Potentially high performance.
- Efficient use of system resources.

Disadvantages include:

- More difficult to write.
- More difficult to understand.
- More hardware-dependent.

---

# B) High-Level Programming Languages

High-level programming languages are designed to be easier for humans to read and write.

Examples include:

- Python
- Java
- JavaScript
- C++
- Ruby
- Go

Example:

```java
class Triangle {

    float surface() {
        return b * h / 2;
    }

}
```

The programmer does not need to directly write machine code.

High-level languages provide more abstraction from the underlying hardware.

Advantages include:

- Easier to learn.
- Easier to write.
- Easier to maintain.
- Usually more portable.

---

# How Do High-Level Languages Work?

Computers do not directly execute most high-level source code.

The source code must be translated or processed into instructions that the computer or another runtime environment can execute.

Two important approaches are:

1. Compilation.
2. Interpretation.

Some modern languages use a combination of both.

---

# 1. Compiler

A **compiler** translates source code into another form before execution.

Depending on the language, the output may be:

- Machine code.
- Object code.
- Bytecode.
- Another intermediate representation.

Examples of languages commonly associated with compilation include:

- C
- C++
- Rust

Java source code is compiled into **bytecode**, which is then executed by the Java Virtual Machine (JVM).

Example:

```text
Source Code

Hello.java

        |
        v

Compile

        |
        v

Bytecode

Hello.class

        |
        v

Java Virtual Machine

        |
        v

Output

Hello, World!
```

---

# 2. Interpreter

An **interpreter** executes or processes program instructions through a runtime environment.

Python is commonly described as an interpreted language, although modern Python implementations also compile source code into intermediate bytecode internally.

Conceptually:

```text
Source Code

Hello.py

        |
        v

Python Interpreter

        |
        v

Output

Hello, World!
```

---

# Compiler vs Interpreter

| Compiler | Interpreter |
|---|---|
| Translates code before execution | Executes code through an interpreter/runtime |
| Often produces compiled output | Usually runs source code through a runtime |
| Example: C, C++ | Example: Python |
| Errors may be detected during compilation | Errors may appear while executing specific code |

Modern programming environments can combine compilation and interpretation.

For example:

- Java compiles source code into bytecode and runs it on the JVM.
- Python source code may be compiled into bytecode and executed by the Python interpreter.

---

# Uses of Programming Languages

Programming languages are used in many areas of technology.

Examples include:

## Android Application Development

Programming languages can be used to build Android applications.

Examples:

- Kotlin
- Java

---

## Website Development

Programming languages are used to create:

- Websites.
- Web applications.
- APIs.
- Backend systems.

Examples:

- HTML
- CSS
- JavaScript
- Python
- PHP
- Java
- Node.js

---

## Machine Learning

Programming languages can be used to create systems that learn patterns from data.

Common languages include:

- Python
- R
- Julia

---

## Artificial Intelligence

Programming languages are used to develop:

- AI assistants.
- Computer vision systems.
- Natural language processing.
- Recommendation systems.
- Robotics.

Python is widely used in AI development.

---

## Game Development

Programming languages are used to create games.

Examples include:

- C++
- C#
- Java
- Python

---

## Big Data

Programming languages are used for:

- Data processing.
- Data analysis.
- Distributed computing.
- Database management.

Examples include:

- Python
- Java
- Scala
- SQL

---

## Desktop Software Development

Programming languages can be used to create desktop applications.

Examples include:

- Python
- C#
- Java
- C++
- Electron with JavaScript

---

## Cybersecurity and Security Tool Development

Programming languages are used to create:

- Security automation tools.
- Network analysis tools.
- Vulnerability testing tools.
- Log analysis tools.
- Educational security scripts.

Common languages include:

- Python
- Bash
- Go
- C
- C++
- Ruby

---

# What Is Python Programming?

Python is a **high-level, general-purpose programming language**.

It is known for:

- Simple syntax.
- Readability.
- Large ecosystem.
- Beginner-friendly design.
- Support for multiple programming styles.

Python is commonly described as an interpreted language because Python programs are executed by a Python interpreter or runtime environment.

Python is used in many areas, including:

- Web development.
- Artificial Intelligence.
- Machine Learning.
- Automation.
- Data analysis.
- Scientific computing.
- Cybersecurity tools.
- Scripting.

---

# Python Syntax Example

Python makes simple tasks easy to write.

```python
print("Hello, World!")
```

---

# Comparing Output in Different Languages

## Python

```python
print("Hello, World!")
```

## C++

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

## Java

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

Python is known for requiring less code for many common tasks.

---

# History of Python

Python was created by **Guido van Rossum**.

Development began in the late 1980s, and Python was first released in 1991.

Python was developed at the **Centrum Wiskunde & Informatica (CWI)** in the Netherlands.

Python was influenced by several programming languages and ideas, including:

- ABC
- Modula-3
- C
- C++
- Algol
- Smalltalk
- Unix shell scripting

Python is now developed and maintained by a global open-source community.

The **Python Software Foundation (PSF)** supports the growth and development of the Python ecosystem.

---

# Why Is Python Popular?

Python is popular because it is:

- Easy to read.
- Easy to learn.
- Powerful.
- Flexible.
- Cross-platform.
- Supported by a large community.
- Supported by many libraries and frameworks.

Python can be used for both simple scripts and large software systems.

---

# Why Python Is Commonly Used in Cybersecurity

Python is widely used for cybersecurity automation and security research because it allows developers to quickly create programs and automate repetitive tasks.

Examples include:

- Automating repetitive tasks.
- Processing logs.
- Working with files.
- Network programming.
- API interaction.
- Data analysis.
- Security testing in authorized environments.

Python's large ecosystem makes it useful for building security tools and automation scripts.

---

# Uses of Python

Python can be used for many purposes.

## 1. Data Visualization

Python can create:

- Charts.
- Graphs.
- Dashboards.
- Data reports.

Popular libraries include:

- Matplotlib
- Plotly

---

## 2. Data Analysis

Python is widely used for analyzing data.

Popular libraries include:

- Pandas
- NumPy

---

## 3. Machine Learning

Python is one of the most widely used languages for machine learning.

Popular libraries include:

- Scikit-learn
- TensorFlow
- PyTorch

---

## 4. Artificial Intelligence

Python can be used for:

- Natural language processing.
- Computer vision.
- AI models.
- Automation.
- Intelligent applications.

---

## 5. Backend Web Development

Python provides several web frameworks.

Examples include:

- Django
- Flask
- FastAPI

---

## 6. Game Development

Python can be used to create simple games and prototypes.

A popular library is:

```text
Pygame
```

---

## 7. Automation and Scripting

Python is excellent for automating repetitive tasks.

Example:

```python
for i in range(5):
    print("Task completed")
```

---

## 8. Security Tool Development

Python can be used to create scripts for authorized activities such as:

- Network administration.
- Security automation.
- Log analysis.
- File analysis.
- Security testing.

---

# How to Install Python

## Installing Python on Windows

Python can be downloaded from the official Python website:

:contentReference[oaicite:0]{index=0}

After installation, verify Python using:

```bash
python --version
```

On some systems:

```bash
py --version
```

---

# Installing Python on Linux

Many Linux distributions already include Python.

Check the version:

```bash
python3 --version
```

If Python is not installed on a Debian-based Linux distribution:

```bash
sudo apt update
sudo apt install python3
```

Check again:

```bash
python3 --version
```

---

# What Is an IDE?

**IDE** stands for:

```text
Integrated Development Environment
```

An IDE is software that provides multiple tools for software development in one environment.

An IDE may include:

- Code editor.
- Compiler or interpreter integration.
- Debugger.
- Terminal.
- File explorer.
- Code completion.
- Project management tools.

Examples include:

- PyCharm
- IntelliJ IDEA
- Visual Studio
- Eclipse

---

# What Is a Code Editor?

A **code editor** is software used to write and edit source code.

Code editors are often more lightweight than full IDEs.

Many code editors can support multiple programming languages through:

- Extensions.
- Plugins.
- Language servers.
- Compilers.
- Interpreters.

Examples include:

- Visual Studio Code
- Sublime Text
- Vim
- Neovim

---

# IDE vs Code Editor

| IDE | Code Editor |
|---|---|
| Full development environment | Mainly focused on editing code |
| Usually includes debugging tools | Features can be extended with plugins |
| Often specialized for development workflows | Usually supports many languages |
| Can be heavier | Often more lightweight |

---

# Using Python with Visual Studio Code on Linux

After installing Python, you can configure Visual Studio Code to run Python programs.

## Step 1: Install Python

Check whether Python is installed:

```bash
python3 --version
```

If it is not installed:

```bash
sudo apt update
sudo apt install python3
```

---

## Step 2: Install Visual Studio Code

Install Visual Studio Code using your preferred installation method for your Linux distribution.

After installation, open VS Code.

---

## Step 3: Install the Python Extension

Inside VS Code:

1. Open the **Extensions** panel.
2. Search for:

```text
Python
```

3. Install the official Python extension.

This provides useful features such as:

- Python syntax support.
- Code completion.
- Debugging.
- Formatting support.
- Python interpreter selection.

---

## Step 4: Create a Python File

Create a new file:

```text
hello.py
```

Add the following code:

```python
print("Hello, World!")
```

Save the file.

---

## Step 5: Select the Python Interpreter

Open the Command Palette:

```text
Ctrl + Shift + P
```

Search for:

```text
Python: Select Interpreter
```

Select the Python interpreter installed on your system.

For example:

```text
Python 3.x
```

---

## Step 6: Run the Python Program

You can run the program using the VS Code terminal.

Open the terminal:

```text
Ctrl + `
```

Then run:

```bash
python3 hello.py
```

Output:

```text
Hello, World!
```

You can also use the Python extension's run options when available.

---

# Creating Your First Python Program

Create a file called:

```text
hello.py
```

Write:

```python
print("Hello, World!")
```

Run it:

```bash
python3 hello.py
```

Output:

```text
Hello, World!
```

Congratulations! You have created and executed your first Python program.

---

# Summary

## Programming Concepts

| Term | Meaning |
|---|---|
| Programming Language | A language used to write instructions for computers |
| Program | A set of instructions that performs a task |
| Algorithm | A finite sequence of steps used to solve a problem |
| Pseudocode | Informal representation of program logic |
| Source Code | Human-readable code written by programmers |
| Machine Code | Low-level instructions executed by the CPU |
| Compiler | Translates source code into another executable or intermediate form |
| Interpreter | Executes code through an interpreter or runtime environment |

---

## Computer Generations

| Generation | Main Technology |
|---|---|
| First Generation | Vacuum Tubes |
| Second Generation | Transistors |
| Third Generation | Integrated Circuits |
| Fourth Generation | Microprocessors |
| Fifth Generation | Advanced Computing and AI Concepts |

---

## Programming Language Levels

### Low-Level Languages

Examples:

- Machine Code
- Assembly

Characteristics:

- Close to hardware.
- More difficult to write.
- Greater hardware control.

### High-Level Languages

Examples:

- Python
- Java
- JavaScript
- C++
- Ruby
- Go

Characteristics:

- Easier to read.
- Easier to write.
- More abstracted from hardware.

---

## Python

Python is:

- High-level.
- General-purpose.
- Readable.
- Cross-platform.
- Supported by a large ecosystem.

Common uses:

- Artificial Intelligence.
- Machine Learning.
- Data Analysis.
- Data Visualization.
- Web Development.
- Automation.
- Game Development.
- Security Tool Development.

---

## Useful Python Commands

Check Python version:

```bash
python3 --version
```

Install Python on Debian-based Linux:

```bash
sudo apt update
sudo apt install python3
```

Run a Python program:

```bash
python3 filename.py
```

Example:

```bash
python3 hello.py
```

---

## Useful Visual Studio Code Steps

1. Install Python.
2. Install Visual Studio Code.
3. Install the Python extension.
4. Create a `.py` file.
5. Select the Python interpreter.
6. Run the program.

---

# Final Notes

Programming is the process of creating instructions that tell computers how to perform tasks.

The basic problem-solving process can be summarized as:

```text
Problem

   |
   v

Algorithm

   |
   v

Pseudocode

   |
   v

Programming Language

   |
   v

Source Code

   |
   v

Compiler / Interpreter

   |
   v

Program Execution

   |
   v

Output
```

Understanding algorithms, pseudocode, programming languages, and how programs are executed provides a strong foundation for learning Python and other programming languages.

---

**@innovatorsemir**