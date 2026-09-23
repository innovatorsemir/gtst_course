# Bash Advanced Notes

## Table of Contents

* [Regular Expressions](#regular-expressions)
* [Bash Else If](#bash-else-if)
* [Loops](#loops)

  * [For Loop](#for-loop)
  * [While Loop](#while-loop)
  * [Until Loop](#until-loop)
  * [Select Loop](#select-loop)
  * [Break Statement](#break-statement)
  * [Continue Statement](#continue-statement)
* [Functions](#functions)
* [Bash and Linux Shell](#bash-and-linux-shell)
* [Interaction with Linux](#interaction-with-linux)

---

# Regular Expressions

## Introduction to Regular Expressions

Regular Expressions, commonly called **Regex**, are patterns used to search, match, and filter text.

### Why Do We Need Regex?

For example:

* How does a website know that an input is an email?
* How can a platform validate a username?
* How can Telegram or another platform detect links?
* How can a system filter specific words?

Many text filtering and validation tasks can be done using **Regular Expressions**.

> **Regex is a PATTERN!**

Regular expressions can be used for:

* Text filtering
* Input validation
* Finding specific patterns
* Filtering links
* Filtering words
* Searching text
* Working with spaces and tabs

Regex is commonly used with Linux tools such as:

* `grep`
* `awk`
* `sed`

---

## Testing Regex

To demonstrate regular expressions, we can simply use the **VS Code Search Tool**.

Turn on the **Regex** button in the search tool.

> The regex pattern is generally similar across programming languages, but the implementation and available features may differ.

---

# Regex Metacharacters

Metacharacters are special symbols used to create regex patterns.

Common regex metacharacters include:

```text
.
^
$
*
+
?
{ }
[ ]
( )
|
\
```

---

## Dot `.`

The dot is used to match almost any character except a newline.

### Syntax

```regex
.
```

It means:

> Match any character except a newline.

---

## Caret `^`

The caret is an **assertion** used to match the beginning of a line.

### Syntax

```regex
^hello
```

This matches lines that **start with `hello`**.

Example:

```text
hello world
hello semir
```

Both start with `hello`.

---

## Dollar Sign `$`

The dollar sign is an **assertion** used to match the end of a line.

### Syntax

```regex
hello$
```

This matches lines that **end with `hello`**.

---

## Plus `+`

The plus sign is a **quantity** operator.

It matches a pattern that occurs **one or more times**.

### Syntax

```regex
hellos+
```

This matches:

```text
hellos
helloss
hellosss
hellossss
```

The `s` must appear at least once.

---

## Asterisk `*`

The asterisk is a **quantity** operator.

It matches a pattern that occurs **zero or more times**.

### Syntax

```regex
hellos*
```

This can match:

```text
hello
hellos
helloss
hellosss
```

The `s` can occur zero or more times.

---

## Question Mark `?`

The question mark is a **quantity** operator.

It matches a pattern that occurs **zero or one time**.

### Syntax

```regex
hellos?
```

This can match:

```text
hello
hellos
```

---

# Combining Regex Patterns

Suppose we need text that:

* Starts with `n`
* Ends with `com`
* Has any text between them

### Start with `n`

```regex
^n
```

### End with `com`

```regex
com$
```

### Any characters between them

```regex
.*
```

Therefore, we can combine them:

```regex
^n.*com$
```

---

# Curly Brackets `{min,max}`

Curly brackets are used to specify how many times a pattern should occur.

### Syntax

```regex
hellos{1,3}
```

This means the `s` should occur between **1 and 3 times**.

### Equivalent forms

```regex
{1,}   # Similar to +
{0,}   # Similar to *
{0,1}  # Similar to ?
```

---

## Example with Character Range

Suppose we need text that:

* Starts with `n`
* Ends with `com`
* Has 7–13 characters between them

Start:

```regex
^n
```

End:

```regex
com$
```

7–13 characters:

```regex
.{7,13}
```

Combined:

```regex
^n.{7,13}com$
```

---

# `\w` — Alphanumeric Characters

`\w` is used to match word/alphanumeric characters.

### Syntax

```regex
\w
```

It generally matches:

```text
A-Z
a-z
0-9
_
```

---

# `\W` — Non-Word Characters

`\W` matches characters that are not word characters.

### Syntax

```regex
\W
```

---

# `\s` — Whitespace

`\s` is used to match whitespace.

### Syntax

```regex
\s
```

It can match:

* Spaces
* Tabs
* Newlines

---

# `\S` — Non-Whitespace

`\S` matches characters that are not whitespace.

### Syntax

```regex
\S
```

---

# `\d` — Digits

`\d` is used to match digits/numbers.

### Syntax

```regex
\d
```

It matches:

```text
0
1
2
3
...
9
```

---

# `\D` — Non-Digits

`\D` matches characters that are not digits.

### Syntax

```regex
\D
```

---

# Pipe `|` — OR

The pipe is used to search for different alternatives.

### Syntax

```regex
a|b
```

This means:

> Match either `a` OR `b`.

---

# Escape Character `\`

The backslash is used to escape special regex characters.

### Syntax

```regex
\sign
```

For example, if we want to search for a literal dot:

```regex
\.
```

---

# Square Brackets `[ ]`

Square brackets are used to create custom character patterns.

### Syntax

```regex
[pattern]
```

For example:

```regex
[abc]
```

This matches one character that is either:

```text
a
b
c
```

We can add multiple patterns inside the same brackets without spaces.

---

# Bash Regex

Regex can be used with Linux tools such as:

* `grep`
* `awk`
* `sed`

Bash itself also supports regex matching.

In Bash, we use the:

```bash
=~
```

operator for regex checking.

For conditional regex checks, we use **double square brackets**:

```bash
[[ expression =~ regex ]]
```

### Syntax

```bash
if [[ "$variable" =~ regex ]]
then
    echo "Match"
fi
```

---

## Bash Regex and Special Characters

On the Bash terminal, some characters have special meanings.

When necessary, regex metacharacters can be escaped using:

```text
\
```

---

# Regex Email Validation Example

### Task

Write a Bash script that:

1. Accepts an email from the user.
2. Checks whether the email follows an email pattern.
3. Displays whether the email is valid.

Example structure:

```bash
#!/bin/bash

read -p "Enter your email: " email

if [[ "$email" =~ ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$ ]]
then
    echo "Valid email"
else
    echo "Invalid email"
fi
```

> Regex patterns can vary depending on how strict the validation needs to be.

---

# Bash Else If

## `elif`

Bash uses `elif` when we need to perform more than one comparison.

It is similar to Python's:

```python
elif
```

### Syntax

```bash
if [ condition1 ]
then
    # body
elif [ condition2 ]
then
    # body
else
    # body
fi
```

### Example

```bash
#!/bin/bash

read -p "Enter your mark: " mark

if [ "$mark" -ge 90 ]
then
    echo "Grade A"
elif [ "$mark" -ge 75 ]
then
    echo "Grade B"
elif [ "$mark" -ge 65 ]
then
    echo "Grade C"
else
    echo "Below Grade C"
fi
```

---

# Loops

On Bash, there are four main types of loops:

1. `for` loop
2. `while` loop
3. `until` loop
4. `select` loop

---

# For Loop

## Basic Syntax

```bash
for variable in list
do
    body
done
```

---

## For Loop with Sequence

In Bash, we can use brace expansion to generate a sequence.

```bash
for num in {1..10}
do
    echo "$num"
done
```

### Output

```text
1
2
3
4
5
6
7
8
9
10
```

---

## For Loop with Words

A `for` loop can also work with words in a string.

```bash
text="Hello GTST this is Day11."

for i in $text
do
    echo "$i"
done
```

### Output

```text
Hello
GTST
this
is
Day11.
```

---

# C-Style For Loop

We can also write a `for` loop using three expressions:

```bash
for ((i=1; i<=10; i++))
do
    echo "$i"
done
```

The three parts are:

```text
START ; CONDITION ; INCREMENT
```

Example:

```bash
for ((i=1; i<=10; i++))
do
    echo "$i"
done
```

Output:

```text
1
2
3
4
5
6
7
8
9
10
```

---

## Increment and Decrement

In Bash:

```bash
i++
```

is similar to:

```bash
i+=1
```

And:

```bash
i--
```

is similar to:

```bash
i-=1
```

---

# For Loop with Step

Brace expansion can also use a step:

```bash
{start..stop..step}
```

Example:

```bash
for num in {1..10..2}
do
    echo "$num"
done
```

Output:

```text
1
3
5
7
9
```

---

## Counting Backwards

```bash
for num in {10..0..-1}
do
    echo "$num"
done
```

Output:

```text
10
9
8
7
6
5
4
3
2
1
0
```

---

# While Loop

A `while` loop continues running while the condition is true.

## Syntax

```bash
while [ expression ]
do
    body
done
```

---

## Example

```bash
#!/bin/bash

read -p "Enter starting number: " snum
read -p "Enter ending number: " enum

while [[ $snum -le $enum ]]
do
    echo "$snum"
    ((snum++))
done

echo "This is the sequence that you wanted."
```

Example:

```text
Enter starting number: 10
Enter ending number: 15
10
11
12
13
14
15
This is the sequence that you wanted.
```

---

# Infinite Loop

A loop can run forever if its condition never becomes false.

Example:

```bash
while :
do
    echo "Semir"
done
```

> Be careful when running infinite loops because they continue until interrupted.

---

# Break Statement

The `break` statement stops the loop immediately.

Example:

```bash
#!/bin/bash

echo "Countdown for Website Launching..."

i=10

while [ $i -ge 1 ]
do
    if [ $i -eq 2 ]
    then
        echo "Mission Aborted, Some Technical Error Found."
        break
    fi

    echo "$i"
    ((i--))
done
```

Output:

```text
Countdown for Website Launching...
10
9
8
7
6
5
4
3
Mission Aborted, Some Technical Error Found.
```

---

# Continue Statement

The `continue` statement skips the rest of the current iteration and starts the next iteration.

> In Python, `continue` also exists. It is not the same as Python's `pass`.

Example:

```bash
#!/bin/bash

i=0

while [ $i -le 10 ]
do
    ((i++))

    if [[ "$i" == 5 ]]
    then
        continue
    fi

    echo "Current Number: $i"
done

echo "Skipped number 5 using Continue Statement."
```

Output:

```text
Current Number: 1
Current Number: 2
Current Number: 3
Current Number: 4
Current Number: 6
Current Number: 7
Current Number: 8
Current Number: 9
Current Number: 10
Current Number: 11
Skipped number 5 using Continue Statement.
```

---

# Until Loop

The `until` loop is similar to a `while` loop, but it continues **until the condition becomes true**.

The word `until` means:

```text
እስከ
```

## Syntax

```bash
until [ expression ]
do
    body
done
```

---

## Example

```bash
i=1

until [ $i -gt 10 ]
do
    echo "$i"
    ((i++))
done
```

Output:

```text
1
2
3
4
5
6
7
8
9
10
```

---

## Comparing `while` and `until`

### While

```bash
i=0

while [ $i -lt 10 ]
do
    echo "$i"
    ((i++))
done
```

### Until

```bash
i=1

until [ $i -gt 10 ]
do
    echo "$i"
    ((i++))
done
```

---

# Select Loop

The `select` loop in Bash is a control-flow statement used for creating a simple menu from which the user can choose options.

## Syntax

```bash
select variable in list
do
    commands
done
```

The `PS3` variable sets the prompt for user input.

The `select` statement displays the available options.

The user's choice is assigned to the selected variable.

A `case` statement can then be used to handle the selection.

---

## Select Loop Example

```bash
PS3="Please select a fruit: "

select fruit in "Apple" "Banana" "Cherry" "Quit"
do
    case $fruit in
        "Apple")
            echo "You selected Apple."
            ;;

        "Banana")
            echo "You selected Banana."
            ;;

        "Cherry")
            echo "You selected Cherry."
            ;;

        "Quit")
            echo "Exiting the program."
            break
            ;;

        *)
            echo "Invalid selection. Please try again."
            ;;
    esac
done
```

---

# Functions

A Bash function is a reusable block of code.

## Creating a Function

### Syntax

```bash
function_name() {
    # body
}
```

### Calling the Function

```bash
function_name
```

---

## Function Example

```bash
print_it() {
    sum=$(($1 + $2))
    echo "The sum: $sum"
}

print_it 5 6
```

Output:

```text
The sum: 11
```

---

# Function Arguments

When a Bash function receives arguments, they are accessed using:

```text
$1
$2
$3
...
```

Example:

```bash
print_it() {
    echo "Your name is $1 and your father name is $2"
}

print_it Semir Nesredin
```

Output:

```text
Your name is Semir and your father name is Nesredin
```

---

# Function Return Value

In Bash, a function can use `return` to provide an **exit status**.

The special variable:

```bash
$?
```

contains the exit status of the most recently executed command or function.

Example:

```bash
print_it() {
    echo "Your name is $1 and your father name is $2"
    return 20
}

print_it Semir Nesredin

echo "Return status: $?"
```

Output:

```text
Your name is Semir and your father name is Nesredin
Return status: 20
```

> Bash function `return` is primarily for an exit status, normally an integer from `0` to `255`. To return a calculated string or larger value, use command substitution and `echo`.

---

## Function Returning a Calculation

Example:

```bash
print_it() {
    return $(($1 + $2))
}

print_it 5 6

echo "The sum: $?"
```

Output:

```text
The sum: 11
```

---

# Bash and Linux Shell

Bash can execute Linux commands.

This means we can run Linux commands directly inside Bash scripts.

Example:

```bash
#!/bin/bash

echo "I can run Linux commands in my Bash script"

ls
```

---

## Running Linux Commands

For example:

```bash
#!/bin/bash

echo "I can run apt commands in my Bash script"

apt update
```

Depending on the system and permissions, `apt update` may require administrative privileges.

---

# Running Bash Code in One Line

Bash commands can sometimes be written on one line using semicolons.

### Multi-line version

```bash
for i in {1..5}
do
    echo "Hello $i"
done
```

### One-line version

```bash
for i in {1..5}; do echo "Hello $i"; done
```

Output:

```text
Hello 1
Hello 2
Hello 3
Hello 4
Hello 5
```

---

# Accessing Files with `*`

The `*` wildcard can be used to match files and directories in the current directory.

Example:

```bash
#!/bin/bash

echo *
```

This displays the names of matching files and directories.

---

# Interaction with Linux

You can interact with the Linux terminal using Bash.

To start Bash:

```bash
/bin/bash
```

You can check your current shell with:

```bash
echo "$SHELL"
```

---

# For Loop Directly in the Terminal

The basic syntax for a one-line `for` loop is:

```bash
for command; do body; done
```

Example:

```bash
for i in *; do echo "$i"; done
```

This loops through files and directories in the current directory.

Example output:

```text
class.sh
Day4_MoreLinux.md
Desktop
Documents
Downloads
exe3.sh
gtst
hello.sh
InitProgramming
intro-linux.pdf
linux
Music
Perm.txt
Pictures
Public
requirements.txt
stderr.txt
stdout.txt
takeme1.txt
Templates
test.sh
Videos
```

---

# Quick Summary

| Topic              | Description                                |
| ------------------ | ------------------------------------------ |
| Regular Expression | A pattern used to search and filter text   |
| Metacharacter      | A special character used in regex patterns |
| `^`                | Matches the beginning of a line            |
| `$`                | Matches the end of a line                  |
| `.`                | Matches almost any character               |
| `*`                | Zero or more occurrences                   |
| `+`                | One or more occurrences                    |
| `?`                | Zero or one occurrence                     |
| `{min,max}`        | Specifies a quantity range                 |
| `\d`               | Digit                                      |
| `\w`               | Word character                             |
| `\s`               | Whitespace                                 |
| `\|`               | OR                                         |
| `\[` / `\]`        | Escaping special characters                |
| `=~`               | Bash regex matching operator               |
| `elif`             | Checks another condition                   |
| `for`              | Repeats commands over a list/sequence      |
| `while`            | Repeats while a condition is true          |
| `until`            | Repeats until a condition becomes true     |
| `select`           | Creates a simple Bash menu                 |
| `break`            | Stops a loop                               |
| `continue`         | Skips the current iteration                |
| Function           | Reusable block of Bash code                |
| `$1`, `$2`         | Function/script arguments                  |
| `$?`               | Previous command/function exit status      |
| `*`                | Wildcard for files/directories             |
| Bash               | Bourne Again Shell                         |
| Linux Shell        | Interface for interacting with Linux       |

---

@innovatorsemir