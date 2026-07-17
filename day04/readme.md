# 🐧 Day 04 - Basic Shell Scripting & Python for DevOps

## 📅 Date
17 July 2026

---

# 🚀 Introduction

Today, I started exploring automation concepts that are essential for DevOps engineers. I learned the basics of **Shell Scripting** for automating Linux tasks and started learning **Python for DevOps automation**.

Shell scripting helps automate repetitive system administration tasks, while Python provides a powerful and flexible way to build automation tools, scripts, and DevOps workflows.

---

# 📚 Topics Covered

- Introduction to Shell Scripting
- Creating Bash Scripts
- Executing Shell Scripts
- Variables in Bash
- Taking User Input
- Script Execution Permissions
- Writing Basic Automation Scripts
- Introduction to Python for DevOps
- Python Syntax and Structure
- Variables and Data Types
- Type Casting
- User Input
- Operators
- Conditional Statements

---

# 🖥️ Shell Scripting

Shell scripting is a way to automate Linux commands by writing them inside a script file.

Instead of manually executing multiple commands repeatedly, we can create scripts that perform tasks automatically.

Common uses of Shell Scripts:

- Server configuration
- Backup automation
- Application deployment
- System monitoring
- Log management

---

# 📝 Creating a Bash Script

Create a script file:

```bash
nano script.sh
```

Example:

```bash
#!/bin/bash

echo "Hello DevOps Engineer"
echo "Starting automation..."
```

The first line:

```bash
#!/bin/bash
```

is called a **shebang**. It tells Linux which interpreter should execute the script.

---

# ▶️ Executing Shell Scripts

Before running a script, we need to give execution permission.

Check permissions:

```bash
ls -l script.sh
```

Add execute permission:

```bash
chmod +x script.sh
```

Run the script:

```bash
./script.sh
```

---

# 📦 Variables in Shell Script

Variables are used to store values.

Example:

```bash
#!/bin/bash

name="DevOps"

echo "Welcome to $name"
```

Output:

```
Welcome to DevOps
```

---

# ⌨️ Reading User Input

Shell scripts can take input from users.

Example:

```bash
#!/bin/bash

echo "Enter your name:"
read username

echo "Hello $username"
```

Output:

```
Enter your name:
Ali

Hello Ali
```

---

# ⚙️ Basic Automation Script Example

Example: Creating a simple backup folder.

```bash
#!/bin/bash

mkdir backup

echo "Backup folder created successfully"
```

This script automatically creates a folder without manually typing the command.

---

# 🐍 Python for DevOps (Basics)

Python is one of the most commonly used programming languages in DevOps.

It is used for:

- Automation scripts
- Cloud management
- API integration
- Monitoring tools
- Configuration management

---

# 🏗️ Python Syntax & Structure

Python uses simple and readable syntax.

Example:

```python
print("Hello DevOps")
```

Output:

```
Hello DevOps
```

---

# 📦 Python Variables

Variables store data values.

Example:

```python
name = "DevOps Engineer"
age = 25

print(name)
print(age)
```

Output:

```
DevOps Engineer
25
```

---

# 🔢 Python Data Types

Common Python data types:

| Data Type | Example |
|-----------|---------|
| String | `"Linux"` |
| Integer | `100` |
| Float | `10.5` |
| Boolean | `True` / `False` |

Example:

```python
name = "Python"
number = 10
version = 3.12
status = True
```

---

# 🔄 Type Casting in Python

Type casting converts one data type into another.

Examples:

Convert string to integer:

```python
age = int("25")

print(age)
```

Convert integer to string:

```python
number = str(100)

print(number)
```

Convert integer to float:

```python
value = float(10)

print(value)
```

---

# ⌨️ Taking User Input

Python allows users to enter values using:

```python
input()
```

Example:

```python
name = input("Enter your name: ")

print("Hello", name)
```

Output:

```
Enter your name:
Ali

Hello Ali
```

---

# ➕ Python Operators

## Arithmetic Operators

Used for mathematical operations.

```python
a = 10
b = 5

print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

---

## Comparison Operators

Used to compare values.

Examples:

```python
x = 10

print(x > 5)
print(x == 10)
print(x != 20)
```

Output:

```
True
True
True
```

---

## Logical Operators

Used to combine conditions.

Operators:

- and
- or
- not

Example:

```python
age = 25

if age > 18 and age < 30:
    print("Allowed")
```

---

## Assignment Operators

Used to assign values.

Example:

```python
x = 10

x += 5

print(x)
```

Output:

```
15
```

---

# 🔀 Conditional Statements in Python

Conditional statements allow programs to make decisions.

---

## if Statement

Example:

```python
age = 20

if age >= 18:
    print("Adult")
```

---

## if-else Statement

Example:

```python
age = 15

if age >= 18:
    print("Allowed")
else:
    print("Not Allowed")
```

---

## if-elif-else Statement

Example:

```python
marks = 80

if marks >= 90:
    print("Grade A")

elif marks >= 70:
    print("Grade B")

else:
    print("Grade C")
```

---

# 💻 Practice

During today's practice, I created and tested simple automation scripts.

## Shell Scripting Practice

Implemented:

- Creating Bash scripts
- Using variables
- Taking user input
- Running scripts using permissions
- Automating basic Linux commands

---

## Python Practice

Practiced Python programs using:

- Variables
- Data types
- Type casting
- User input
- Print statements
- Arithmetic operations
- Comparison operators
- Logical operators
- Assignment operators
- if-else conditions

---

# 🎯 Key Takeaways

- Shell scripting is a powerful tool for automating repetitive Linux tasks.
- Bash scripts help DevOps engineers manage servers efficiently.
- Python provides a simple and readable syntax for automation.
- Variables and data types are the foundation of programming.
- Operators allow programs to perform calculations and comparisons.
- Conditional statements help create decision-based automation logic.

---

# 📈 Progress

- ✅ Day 01 - DevOps Roadmap
- ✅ Day 02 - Linux Fundamentals
- ✅ Day 03 - Advanced Linux, SSH & AWS Volume Management
- ✅ Day 04 - Basic Shell Scripting & Python for DevOps

**Completed:** 4 / 90 Days 🚀

---

# 💡 What's Next?

Next, I will continue Python for DevOps by learning:

- Loops (`for`, `while`)
- Functions
- Lists
- Tuples
- Dictionaries
- Sets
- File Handling
- Modules and Packages
- Exception Handling

---

⭐ Thank you for following my #90DaysOfDevOps journey!