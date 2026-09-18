# Introduction to BASH Scripting

## What is Bash

### What is Bash Script?

- Bash = **Bourne Again Shell**
- It is a shell that is used to interact with your kernel.
- A **script** is a file that contains shell commands in a simple and clear algorithm.
- The original is **sh - Bourne shell**.

## Use of Bash for Hackers

### Uses of Bash

- Script development
- Automating tasks
- Simplifying your Linux ability
- Developing hacking scripts

## Starting with Bash

- Bash files can have `.sh` extension, but you can have them without `.sh` too.
- The file has to have **executable permissions** when running it directly.
- You can use any text editor you need:
  - VIM
  - nano
  - VSCode
  - gedit
  - cherrytree

## Output

### Displaying Output

```bash
#!/bin/bash

echo "Hello World!"
```

### Shebang

The **shebang** tells the shell which interpreter is used to execute the script.

Common examples:

```bash
#!/bin/bash
```

```bash
#!/bin/sh
```

### `echo`

To display output in Bash:

```bash
echo "YOUR TEXT HERE"
```

### Running a Bash Script

```bash
/bin/bash hello.sh
```

To run it directly:

```bash
./hello.sh
```

Direct execution requires executable permission.

### File Permissions Example

```text
$ ls -l hello.sh
-rw-r--r-- 1 rexder rexder 34 Jan 2 04:00 hello.sh

$ /bin/bash hello.sh
Hello World!

$ chmod +x hello.sh

$ ls -l hello.sh
-rwxr-xr-x 1 rexder rexder 34 Jan 2 04:00 hello.sh
```

`chmod +x` adds executable permission.

## Examples

### Example 1

```bash
#!/bin/bash

echo "Welcome to BASH Scripting!"
```

Output:

```text
Welcome to BASH Scripting!
```

### Example 2

```bash
#!/bin/bash

echo "Welcome to BASH Scripting!"
echo "Bash is So simple ..."
```

Output:

```text
Welcome to BASH Scripting!
Bash is So simple ...
```

If you need to add new lines to your output, add another `echo`.

# Variables & Data Types

## Variables

Bash variables are similar to Python variables, with some exceptions.

### Syntax

```bash
VARIABLE_NAME=value
```

### Important Rules

- There must be **NO space** around the equal sign (`=`).

Incorrect:

```bash
NAME = "Semir"
```

Correct:

```bash
NAME="Semir"
```

- Never start a variable name with numbers.
- Use double quotes for text values.
- To use a variable, use `$` before the variable name.
- If you want to display a variable together with other text, use `${VARIABLE_NAME}`.
- Bash variables are strings by default.

### Example

```bash
#!/bin/bash

NAME="Semir"
SPORT="Foot"

echo "Your Name is $NAME and you love to play ${SPORT}ball"
```

Output:

```text
Your Name is Semir and you love to play Football
```

# Positional Parameters and `set`

The `set` command can be used to assign values to positional parameters.

```text
set nathan abebe sami miki jerry

$1      $2     $3    $4    $5
```

### Syntax

```bash
set value1 value2 value3 value4 value5
```

### Example 1

```bash
#!/bin/bash

set semir abebe sami miki jerry

echo $3 $2
```

Output:

```text
sami abebe
```

### Example 2

```bash
#!/bin/bash

set semir abebe sami miki jerry

echo $3 $2 $1
```

Output:

```text
sami abebe semir
```

# System Variables

- System variables are variables declared by the system.
- Examples:
  - `LANG`
  - `TERM`
  - `MAIL`
  - `EDITOR`
  - `USER`
  - `SHELL`
- `USER` displays the current computer user.

### Example

```bash
#!/bin/bash

echo $BASH
echo $BASH_VERSION
echo $PWD
echo $HOME
echo $PATH
```

Example output:

```text
/bin/bash
5.1.8(1)-release
/home/rexder/Desktop
/home/rexder
/usr/local/sbin:/usr/sbin:/sbin:/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/home/rexder/.dotnet/tools
```

# Data Types

Normal Bash variables create strings by default.

To create other data structures, we can use `declare`.

## Arrays

- Arrays are similar to lists or tuples in Python.
- Arrays can store multiple values.

### Array Syntax

```bash
var=("list1" "list2" "list3" "list4")
```

### Accessing an Element

```bash
echo "${var[0]}"
```

### Getting All Elements

```bash
echo "${var[@]}"
```

### Getting the Indexes

```bash
echo "${!var[@]}"
```

### Getting the Length

```bash
echo "${#var[@]}"
```

### Adding an Element

```bash
var[4]="list5"
```

### Removing an Element

```bash
unset var[3]
```

## Array Example

```bash
os=('ubuntu' 'windows' 'kali')
os[6]='mac'

unset os[2]

echo "${os[@]}"
echo "${os[0]}"
echo "${!os[@]}"
echo "${#os[@]}"
```

Output:

```text
ubuntu windows mac
ubuntu
0 1 6
3
```

# Bash Input

On Bash, there are two main methods to accept input:

1. `read`
2. Arguments

## 1. Bash `read`

The `read` command is used to accept input while the script is running.

### Syntax

```bash
read -p "Text To Display" var
```

For hidden input such as a password:

```bash
read -sp "Password: " var
```

For accepting an array:

```bash
read -a var
```

### Basic Input Example

```bash
#!/bin/bash

echo "[?] WELCOME TO GTST"
read -p "[+] ENTER YOUR NAME: " NAME

echo "YOUR NAME IS $NAME"
```

Example:

```text
[?] WELCOME TO GTST
[+] ENTER YOUR NAME: Nathan
YOUR NAME IS Nathan
```

### Hidden Password Input

```bash
#!/bin/bash

echo "[?] GTST COMPANY LOGIN."

read -p "[+] Enter Username: " NAME
read -sp "[+] Enter Password: " PASS

echo
echo "Your Username is $NAME"
echo "Your Password is $PASS"
```

The `-s` option prevents the password from being displayed while it is entered.

### Array Input with `read -a`

```bash
#!/bin/bash

echo "[?] GTST COMPANY Names"

read -a NAMES

echo
echo "The 1st Worker name: ${NAMES[0]}"
echo "The 2nd Worker name: ${NAMES[1]}"
echo "The 3rd Worker name: ${NAMES[2]}"
```

Example input:

```text
Nathan Hailu Abebe
```

Output:

```text
The 1st Worker name: Nathan
The 2nd Worker name: Hailu
The 3rd Worker name: Abebe
```

---

# 2. Bash Arguments

Arguments provide input when starting the script.

### Positional Argument Syntax

Bash provides positional parameters such as:

```text
$0
$1
$2
$3
...
$9
```

- `$0` is the script name.
- `$1` is the first argument.
- `$2` is the second argument.

Example:

```bash
#!/bin/bash

echo "Your name is: $1"
echo "Your Father name is: $2"
```

Run:

```bash
/bin/bash hello.sh Semir Nesredin
```

Output:

```text
Your name is: Semir
Your Father name is: Nesredin
```

---

# Comments and Indentation

## Comments

Comments are used to explain code and are not executed.

### Single-Line Comments

In Bash, a comment starts with `#`.

```bash
#!/bin/bash

# This is a single line comment in Bash Script.
echo "Enter your name:"

read name

echo

# This is another single line comment.
echo "The current user name is $name"
```

### Multi-Line Comments

A common Bash technique for a multi-line comment is:

```bash
: << COMMENTS
This is the first comment
This is the second comment
This is the third comment
COMMENTS
```

Example:

```bash
#!/bin/bash

: << COMMENTS
This is the first comment
This is the second comment
This is the third comment
COMMENTS

echo "Hello World"
```

Output:

```text
Hello World
```

> Note: Bash does not require indentation in the same way Python does, but indentation is still useful for making scripts readable.

---

# Bash `sleep`

The `sleep` command pauses the script for a specified amount of time.

### Syntax

```bash
sleep NUMBERs
```

Example:

```bash
#!/bin/bash

echo "Your name is: $1"
sleep 2s
echo "Your Father name is $2"
```

Run:

```bash
/bin/bash hello.sh Nathan Hailu
```

Output:

```text
Your name is: Nathan
```

After two seconds:

```text
Your Father name is Hailu
```

---

# Arithmetic Operations

To perform arithmetic operations in Bash, use:

```bash
$((expression))
```

The `let` keyword can also be used for arithmetic assignment.

## Arithmetic Operators

| Operation | Operator | Example |
|---|---|---|
| Addition | `+` | `$((a + b))` |
| Subtraction | `-` | `$((a - b))` |
| Multiplication | `*` | `$((a * b))` |
| Division | `/` | `$((a / b))` |
| Exponentiation | `**` | `$((a ** b))` |
| Modulo | `%` | `$((a % b))` |

Example:

```bash
#!/bin/bash

a=22
b=22

echo "The sum is: $((a+b))"
```

Output:

```text
The sum is: 44
```

## Assignment Operations

Examples:

```bash
let a+=3
let a-=3
let a*=3
let a/=3
```

These can be used to increment, decrement, multiply, or divide the value of a variable.

---

# Comparison Operations

Bash provides comparison operators for numeric comparisons.

| Meaning | Numeric Operator | Symbol Form |
|---|---|---|
| Greater than | `-gt` | `>` |
| Less than | `-lt` | `<` |
| Greater than or equal | `-ge` | `>=` |
| Less than or equal | `-le` | `<=` |
| Equal | `-eq` | `=` |
| Not equal | `-ne` | `!=` |

For numeric comparisons, operators such as `-gt`, `-lt`, `-ge`, `-le`, `-eq`, and `-ne` are commonly used inside `[ ]`.

---

# If-Else Conditions

## Syntax

```bash
#!/bin/bash

if [ condition ]
then
    # body
else
    # body
fi
```

Bash uses `fi` to mark the end of an `if` statement.

### Using `[ condition ]`

Example:

```bash
#!/bin/bash

if [ 2 -gt 1 ]
then
    echo "he"
else
    echo "bye"
fi
```

Output:

```text
he
```

### Using Arithmetic Conditions

Arithmetic conditions can also be written using `(( ))`:

```bash
#!/bin/bash

if (( 2 > 1 ))
then
    echo "he"
else
    echo "bye"
fi
```

Output:

```text
he
```

---

# Nested If

A nested `if` means using an `if` statement inside another `if` statement.

Example:

```bash
#!/bin/bash

if [ "$1" -gt 50 ]
then
    echo "Number is greater than 50."

    if (( $1 % 2 == 0 ))
    then
        echo "and it is an even number."
    fi
fi
```

Run:

```bash
/bin/bash hello.sh 60
```

Output:

```text
Number is greater than 50.
and it is an even number.
```

---

# Logical Conditions

Bash can combine conditions using logical operators.

Common logical operators include:

- `&&` — AND
- `||` — OR
- `!` — NOT

Example:

```bash
#!/bin/bash

if [[ 10 -eq 10 && 5 -gt 4 || 3 -eq 4 || 3 -lt 6 ]]
then
    echo "Condition is true."
fi
```

The logic can be understood as:

```text
True && True || False || True
True    ||     True
       True
```

Output:

```text
Condition is true.
```

---

# Quick Summary

| Topic | Description |
|---|---|
| Bash | Bourne Again Shell |
| Shell | Interface used to interact with the operating system/kernel |
| Script | File containing commands executed by a shell |
| Shebang | Specifies the interpreter used to execute a script |
| `echo` | Displays output |
| Variable | Stores a value |
| `$VARIABLE` | Accesses a variable |
| `${VARIABLE}` | Accesses a variable when attaching text |
| `set` | Assigns positional parameters |
| `$1`, `$2` | Positional arguments |
| `read` | Accepts input while a script is running |
| `read -s` | Accepts hidden input |
| `read -a` | Accepts input into an array |
| `#` | Single-line comment |
| `sleep` | Pauses script execution |
| `$(( ))` | Performs arithmetic |
| `if` | Tests a condition |
| `else` | Runs when the `if` condition is false |
| `fi` | Ends an `if` statement |
| `&&` | Logical AND |
| `||` | Logical OR |
| `!` | Logical NOT |
| Array | Stores multiple values |

---

@innovatorsemir