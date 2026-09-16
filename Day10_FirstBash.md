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

# Quick Summary

| Topic | Description |
|---|---|
| Bash | Bourne Again Shell |
| Bash Script | A file containing shell commands |
| Shebang | Tells the shell which interpreter to use |
| `echo` | Displays output |
| `chmod +x` | Adds executable permission |
| Variable | Stores a value |
| `$VARIABLE` | Accesses a variable |
| `${VARIABLE}` | Useful when combining a variable with text |
| `set` | Assigns values to positional parameters |
| System Variable | Variable provided by the system |
| Array | Stores multiple values |
| `${array[@]}` | Gets all array elements |
| `${!array[@]}` | Gets array indexes |
| `${#array[@]}` | Gets array length |
| `unset` | Removes an array element |

---

@innovatorsemir