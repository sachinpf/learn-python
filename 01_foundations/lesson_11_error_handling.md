# Lesson 11: Error Handling in Python

## Catching Bugs Like a Pro Detective!

---

## What Are Errors (Bugs)?

**First, the most important thing about errors:** they are NOT bad. They are not punishment. They are not signs that you're a bad programmer.

**Errors are information.** They are Python's way of telling you, in plain English, exactly what went wrong and where. The more comfortable you get reading errors, the faster you become at fixing them. Every professional programmer, no matter how senior, runs into errors every single day.

In programming, **errors** (त्रुटी — कोडमधील चूक जी Python ओळखतो) — also called **bugs** (बग — अनपेक्षित चुकीचे वर्तन घडवणारी कोडमधील चूक) — are messages Python shows you when something goes wrong with your code.

The word "bug" comes from an actual bug! In 1947, engineers found a real moth stuck inside a computer that was causing problems. They taped it into their logbook and wrote "First actual case of bug being found." And the name stuck!

**There are three main types of errors, and an important thing to notice is *when* each one happens:**

1. **Syntax Errors** — Python can't even *start* running your code. It found a typing mistake (like missing a `:` or `)`) and refuses to run *anything*. This happens **before** your program runs.
2. **Runtime Errors** — Python started running your code, but hit a problem partway through (like dividing by zero, or asking for an item that doesn't exist). This happens **during** the run — earlier lines may have worked fine!
3. **Logic Errors** — Your code runs without crashing, but gives the wrong answer. Python has no idea anything is wrong — only *you* can spot these. (Example: you wrote `+` when you meant `-`.)

> **How to read an error message:** Look at the **last line** first — it usually has the error name and a short explanation in English. Then look at the **line number** Python points to. That's where the problem is (or very close to it). Don't panic — read.

---

## Common Error Types in Python

Let's look at each error type with examples. Don't be scared — errors are your friends! They tell you exactly what went wrong.

---

### 1. SyntaxError — You Broke Python's Grammar Rules

A **SyntaxError** (सिंटॅक्स त्रुटी — कोड लिखाणाच्या नियमांची चूक) means Python can't even understand your code. It's like writing a sentence without proper grammar.

```python
# Missing colon after if statement
if True
    print("Hello")
```

**Error:**
```
  File "example.py", line 1
    if True
          ^
SyntaxError: expected ':'
```

```python
# Mismatched parentheses
print("Hello"
```

**Error:**
```
  File "example.py", line 1
    print("Hello"
         ^
SyntaxError: '(' was never closed
```

```python
# Forgetting quotes around a string
print(Hello World)
```

**Error:**
```
SyntaxError: invalid syntax
```

**How to fix:** Read the error message carefully — Python tells you the line number and points to where the problem is!

---

### 2. NameError — Using a Variable That Doesn't Exist

A **NameError** happens when you use a name that Python doesn't recognize — like calling someone by the wrong name.

```python
# Typo in variable name
message = "Hello"
print(mesage)  # Oops! "mesage" instead of "message"
```

**Error:**
```
NameError: name 'mesage' is not defined
```

```python
# Using a variable before creating it
print(score)
score = 100
```

**Error:**
```
NameError: name 'score' is not defined
```

```python
# Forgetting to define a function
greet("Alice")  # We never defined greet()!
```

**Error:**
```
NameError: name 'greet' is not defined
```

**How to fix:** Check your spelling! Make sure the variable or function is defined before you use it.

---

### 3. TypeError — Using the Wrong Type

A **TypeError** happens when you try to do something with the wrong type of data — like trying to eat a book or read a sandwich.

```python
# Adding a string and a number
result = "Age: " + 25
```

**Error:**
```
TypeError: can only concatenate str (not "int") to str
```

```python
# Calling something that isn't a function
x = 42
x()  # 42 is a number, not a function!
```

**Error:**
```
TypeError: 'int' object is not callable
```

```python
# Passing wrong number of arguments
def greet(name):
    print(f"Hello, {name}!")

greet("Alice", "Bob")  # Too many arguments!
```

**Error:**
```
TypeError: greet() takes 1 positional argument but 2 were given
```

**How to fix:** Make sure you're using the right types. Convert with `str()`, `int()`, or `float()` when needed.

---

### 4. ValueError — Right Type, Wrong Value

A **ValueError** happens when a function gets the right type but the value doesn't make sense — like asking someone to "eat the number 7."

```python
# Trying to convert a word to a number
number = int("hello")
```

**Error:**
```
ValueError: invalid literal for int() with base 10: 'hello'
```

```python
# Trying to convert an invalid number
number = int("3.14")  # int() can't handle decimals in string form
```

**Error:**
```
ValueError: invalid literal for int() with base 10: '3.14'
```

```python
# Unpacking the wrong number of values
a, b = [1, 2, 3]  # 3 values but only 2 variables
```

**Error:**
```
ValueError: too many values to unpack (expected 2)
```

**How to fix:** Make sure the values you're passing actually make sense for what you're trying to do.

---

### 5. IndexError — List Index Out of Range

An **IndexError** happens when you try to access a position in a list that doesn't exist — like looking for seat 10 in a row that only has 5 seats.

```python
# Accessing an index that's too big
fruits = ["apple", "banana", "cherry"]
print(fruits[5])  # Only indices 0, 1, 2 exist!
```

**Error:**
```
IndexError: list index out of range
```

```python
# Common mistake: off by one
colors = ["red", "blue", "green"]
print(colors[3])  # Index 3 doesn't exist! (0, 1, 2 are valid)
```

**Error:**
```
IndexError: list index out of range
```

```python
# Accessing from empty list
empty_list = []
print(empty_list[0])
```

**Error:**
```
IndexError: list index out of range
```

**How to fix:** Check the length of your list with `len()` before accessing by index. Remember, indices start at 0!

---

### 6. KeyError — Dictionary Key Not Found

A **KeyError** happens when you try to access a dictionary key that doesn't exist — like looking for a word in the dictionary that isn't there.

```python
# Accessing a key that doesn't exist
student = {"name": "Alice", "age": 15}
print(student["grade"])  # "grade" key doesn't exist!
```

**Error:**
```
KeyError: 'grade'
```

```python
# Typo in key name
scores = {"math": 95, "science": 88}
print(scores["Math"])  # Capital M — keys are case-sensitive!
```

**Error:**
```
KeyError: 'Math'
```

**How to fix:** Use `.get()` for safe access, or check with `if "key" in dictionary:` first.

```python
# Safe way to access dictionary keys
print(student.get("grade", "Not assigned"))  # Returns "Not assigned" instead of crashing
```

---

### 7. ZeroDivisionError — Dividing by Zero

A **ZeroDivisionError** happens when you try to divide by zero — which is mathematically impossible!

```python
# Direct division by zero
result = 10 / 0
```

**Error:**
```
ZeroDivisionError: division by zero
```

```python
# Division by zero from a variable
total = 100
count = 0
average = total / count  # Boom!
```

**Error:**
```
ZeroDivisionError: division by zero
```

```python
# Even modulo (%) by zero causes this
remainder = 10 % 0
```

**Error:**
```
ZeroDivisionError: integer modulo by zero
```

**How to fix:** Always check if the divisor is zero before dividing!

```python
if count != 0:
    average = total / count
else:
    print("Can't calculate average — no items!")
```

---

### 8. FileNotFoundError — File Doesn't Exist

A **FileNotFoundError** happens when you try to open a file that doesn't exist.

```python
# Trying to read a file that doesn't exist
with open("unicorn_data.txt", "r") as file:
    content = file.read()
```

**Error:**
```
FileNotFoundError: [Errno 2] No such file or directory: 'unicorn_data.txt'
```

```python
# Typo in filename
with open("daata.txt", "r") as file:  # Should be "data.txt"
    content = file.read()
```

**Error:**
```
FileNotFoundError: [Errno 2] No such file or directory: 'daata.txt'
```

**How to fix:** Double-check the file name and path. Use `try-except` to handle the case gracefully.

---

## try-except Blocks — Catching Errors

Instead of letting errors **crash** (क्रॅश होणे — कार्यक्रम अकस्मात थांबणे) your program, you can **catch** them and handle them gracefully! When Python "raises" an error, programmers also call that error an **exception** (अपवाद — कोड चालत असताना उद्भवलेली त्रुटी) — because it's an exception to the normal flow of your program.

Think of `try-except` (try / except — अपवाद पकडून कार्यक्रम क्रॅश न होऊ देणारी रचना) as a **safety net** under a tightrope walker. If they fall, the net catches them.

> **When should you use `try-except`?** Not for *every* error! Use it for **expected** problems you can't prevent — like bad user input, missing files, or a network being down. Don't use it to hide bugs in your own code. If your variable name is misspelled, fix the typo — don't wrap it in `try-except`!

```python
# Without try-except (program CRASHES):
number = int(input("Enter a number: "))  # What if they type "abc"?
print(f"You entered: {number}")
# If user types "abc" → CRASH! ValueError!

# With try-except (program handles it gracefully):
try:
    number = int(input("Enter a number: "))
    print(f"You entered: {number}")
except ValueError:
    print("That's not a valid number! Please try again.")
```

### How It Works

```python
try:
    # Put the "risky" code here — code that MIGHT cause an error
    risky_operation()
except ErrorType:
    # This runs ONLY if that specific error happens
    handle_the_error()
```

### Example: Safe Division

```python
try:
    a = int(input("Enter a number: "))
    b = int(input("Divide by: "))
    result = a / b
    print(f"{a} / {b} = {result}")
except ZeroDivisionError:
    print("You can't divide by zero!")
except ValueError:
    print("Please enter valid numbers!")
```

### Catching Multiple Errors

```python
# Method 1: Separate except blocks
try:
    num = int(input("Enter a number: "))
    result = 100 / num
    print(f"100 / {num} = {result}")
except ValueError:
    print("That's not a number!")
except ZeroDivisionError:
    print("Can't divide by zero!")

# Method 2: Catch multiple errors in one block
try:
    num = int(input("Enter a number: "))
    result = 100 / num
except (ValueError, ZeroDivisionError):
    print("Invalid input! Enter a non-zero number.")
```

### Catching ANY Error

```python
# Catch any error (use sparingly — it's better to be specific)
try:
    # Some risky code
    result = int("hello") / 0
except Exception as e:
    print(f"Something went wrong: {e}")
```

The variable `e` holds the error message, so you can see what happened.

---

## try-except-else — Do Something Extra When There's No Error

The `else` block runs **only if no error occurred** in the `try` block.

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("That's not a valid number!")
else:
    # This only runs if NO error happened
    print(f"Great! You entered {number}")
    print(f"Double that is {number * 2}")
```

Think of it like this:
- `try` — "Let me TRY this..."
- `except` — "Oops, something went wrong!"
- `else` — "Everything went fine!"

### Example: Safe File Reader

```python
filename = input("Enter filename: ")

try:
    with open(filename, "r") as file:
        content = file.read()
except FileNotFoundError:
    print(f"Sorry, '{filename}' doesn't exist!")
else:
    # Only runs if the file was opened successfully
    print(f"File '{filename}' has {len(content)} characters.")
    print("Here's the content:")
    print(content)
```

---

## try-except-finally — Always Do This, No Matter What

The `finally` block runs **no matter what** — whether an error happened or not. It's like cleaning up after yourself.

```python
try:
    number = int(input("Enter a number: "))
    result = 100 / number
except ValueError:
    print("That's not a number!")
except ZeroDivisionError:
    print("Can't divide by zero!")
else:
    print(f"Result: {result}")
finally:
    # This ALWAYS runs, error or no error
    print("Thank you for using the calculator!")
```

**Output (no error):**
```
Enter a number: 5
Result: 20.0
Thank you for using the calculator!
```

**Output (with error):**
```
Enter a number: 0
Can't divide by zero!
Thank you for using the calculator!
```

### When is `finally` useful?

- **Closing files** (though `with` handles this for us)
- **Closing database connections**
- **Cleaning up temporary data**
- **Showing a final message**

### The Complete Structure

```python
try:
    # Risky code goes here
    pass
except SpecificError:
    # Runs if SpecificError occurs
    pass
except AnotherError:
    # Runs if AnotherError occurs
    pass
else:
    # Runs only if NO error occurred
    pass
finally:
    # ALWAYS runs, no matter what
    pass
```

---

## Catching Specific Exceptions — Being Precise

Always try to catch **specific** exceptions rather than using a generic `except`. It's like a doctor diagnosing the exact illness rather than saying "you're sick."

```python
# BAD — Too vague! This catches EVERYTHING, even bugs you want to know about
try:
    result = calculate_something()
except:
    print("Something went wrong")

# BETTER — Catches only the expected error
try:
    result = int(user_input)
except ValueError:
    print("Please enter a valid number")

# BEST — Catches specific errors with helpful messages
try:
    result = int(user_input)
except ValueError:
    print(f"'{user_input}' is not a valid number. Please enter digits only.")
```

### Getting Error Details

```python
try:
    number = int("hello")
except ValueError as e:
    print(f"Error type: ValueError")
    print(f"Error message: {e}")
    # Output: Error message: invalid literal for int() with base 10: 'hello'
```

---

## Raising Exceptions with `raise`

Sometimes YOU want to create an error on purpose. This is useful when someone uses your function incorrectly.

Think of it like a referee blowing a whistle — you're saying "Hey, that's not allowed!"

```python
# Raise an error when age is negative
def set_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative!")
    if age > 150:
        raise ValueError("Age seems unrealistic!")
    print(f"Age set to {age}")

# Using the function
try:
    set_age(25)    # Works fine
    set_age(-5)    # Raises ValueError!
except ValueError as e:
    print(f"Invalid age: {e}")
```

**Output:**
```
Age set to 25
Invalid age: Age cannot be negative!
```

### More Examples

```python
def divide(a, b):
    """Divide a by b, but don't allow zero."""
    if b == 0:
        raise ZeroDivisionError("You passed zero as the divisor!")
    return a / b

def get_grade(score):
    """Convert a score to a letter grade."""
    if not isinstance(score, (int, float)):
        raise TypeError("Score must be a number!")
    if score < 0 or score > 100:
        raise ValueError("Score must be between 0 and 100!")

    if score >= 90:
        return "A"
    elif score >= 80:
        return "B"
    elif score >= 70:
        return "C"
    elif score >= 60:
        return "D"
    else:
        return "F"

# Test it
try:
    print(get_grade(95))     # A
    print(get_grade(150))    # Raises ValueError
except ValueError as e:
    print(f"Error: {e}")
```

---

## Common Debugging Tips

Debugging (डीबग — बग शोधून दूर करणे) is like being a detective — you're looking for clues to find the bug!

### Tip 1: Read the Error Message Carefully

Error messages are your BEST friend. They tell you:
- **What** went wrong (the error type)
- **Where** it happened (the file and line number)
- **Why** it happened (the error message)

```
Traceback (most recent call last):
  File "game.py", line 15, in <module>     ← WHERE
    score = int(user_input)                 ← WHAT LINE
ValueError: invalid literal for int()      ← WHY
```

### Tip 2: Use print() to Track Values

```python
# Sprinkle print statements to see what's happening
def calculate_average(numbers):
    print(f"DEBUG: numbers = {numbers}")        # What did we receive?
    print(f"DEBUG: len = {len(numbers)}")        # How many items?

    total = sum(numbers)
    print(f"DEBUG: total = {total}")             # What's the total?

    average = total / len(numbers)
    print(f"DEBUG: average = {average}")         # What's the average?

    return average
```

### Tip 3: Check Your Assumptions

```python
# Before risky operations, verify your data
def process_list(items):
    # Check: is it actually a list?
    print(f"Type of items: {type(items)}")

    # Check: is it empty?
    print(f"Length: {len(items)}")

    # Check: what's inside?
    print(f"Contents: {items}")
```

### Tip 4: Simplify the Problem

If your code is long and has a bug, try:
1. **Comment out** sections of code to narrow down where the bug is
2. **Test small pieces** separately
3. **Use simple test data** first, then try complex data

### Tip 5: Rubber Duck Debugging

Explain your code line by line to a rubber duck (or stuffed animal, or friend). Often, just explaining the code out loud helps you spot the bug!

### Tip 6: Common Mistakes to Watch For

```python
# Mistake 1: = vs == (assignment vs comparison)
x = 5        # This ASSIGNS the value 5 to x
x == 5       # This CHECKS if x equals 5

# Mistake 2: Off-by-one errors
for i in range(5):     # Goes 0, 1, 2, 3, 4 (NOT 5!)
    print(i)

# Mistake 3: Modifying a list while looping over it
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    if num % 2 == 0:
        numbers.remove(num)    # DANGEROUS! Can skip items

# Mistake 4: Forgetting to return a value
def add(a, b):
    result = a + b
    # Oops! Forgot: return result

# Mistake 5: Indentation errors
if True:
print("This will cause an error!")  # Not indented!
```

---

## Using PyCharm's Debugger (Quick Intro)

While `print()` debugging works, PyCharm has a built-in **debugger** that's like having X-ray vision for your code!

### What is a Debugger?

A debugger lets you:
- **Pause** your program at any line (using **breakpoints**)
- **Step through** your code one line at a time
- **Watch** the values of variables as they change
- **See** exactly what's happening inside loops and functions

### Setting Breakpoints

1. Click on the **left margin** (the gray area next to the line numbers) in PyCharm
2. A **red dot** appears — that's a breakpoint!
3. Your program will **pause** at that line when you run the debugger

```python
# Example: Put a breakpoint on line 3 to see what happens
name = "Alice"           # Line 1
age = 15                 # Line 2
message = f"Hi, {name}"  # Line 3 ← PUT BREAKPOINT HERE
print(message)           # Line 4
```

### Running the Debugger

1. Instead of clicking the green **Run** button, click the green **Bug** button (or press Shift+F9)
2. Your program runs until it hits a breakpoint
3. At the bottom, you'll see a **Debugger panel** showing all variable values

### Stepping Through Code

Once paused at a breakpoint, you can:
- **Step Over (F8)** — Run the current line and move to the next one
- **Step Into (F7)** — If the line calls a function, go INSIDE that function
- **Step Out (Shift+F8)** — Finish the current function and go back
- **Resume (F9)** — Continue running until the next breakpoint

### The Variables Panel

When paused, look at the **Variables** panel at the bottom. It shows you the current value of every variable. This is incredibly useful for finding bugs!

### Quick Example

```python
# Try debugging this with breakpoints!
def mystery_function(numbers):
    total = 0                    # Breakpoint here
    for num in numbers:          # Step through each iteration
        if num > 0:
            total += num         # Watch 'total' change
    return total

result = mystery_function([3, -1, 5, -2, 8])
print(result)  # What do you expect? Use debugger to verify!
```

**Tip:** Start with `print()` debugging for simple bugs. Use PyCharm's debugger for tricky bugs that are hard to figure out.

---

## Exercises

### Exercise 1: Safe Calculator

Create a calculator that handles ALL possible errors gracefully. It should:
- Ask for two numbers and an operator (+, -, *, /)
- Handle invalid numbers, division by zero, and invalid operators
- Keep running until the user types "quit"

<details>
<summary>Click to see the solution</summary>

```python
# ===== SAFE CALCULATOR =====
# A calculator that NEVER crashes, no matter what the user types!

def calculate(num1, num2, operator):
    """Perform a calculation. Raises ValueError for invalid operators."""
    if operator == "+":
        return num1 + num2
    elif operator == "-":
        return num1 - num2
    elif operator == "*":
        return num1 * num2
    elif operator == "/":
        if num2 == 0:
            raise ZeroDivisionError("Cannot divide by zero!")
        return num1 / num2
    else:
        raise ValueError(f"Unknown operator: '{operator}'. Use +, -, *, or /")

print("===== Safe Calculator =====")
print("Type 'quit' to exit.\n")

while True:
    # Get the first number
    input1 = input("Enter first number: ")
    if input1.lower() == "quit":
        break

    # Get the operator
    operator = input("Enter operator (+, -, *, /): ")
    if operator.lower() == "quit":
        break

    # Get the second number
    input2 = input("Enter second number: ")
    if input2.lower() == "quit":
        break

    # Try to perform the calculation
    try:
        # Convert inputs to numbers
        num1 = float(input1)
        num2 = float(input2)

        # Perform the calculation
        result = calculate(num1, num2, operator)

        # Display the result
        print(f"\n  {num1} {operator} {num2} = {result}\n")

    except ValueError as e:
        # Handles: invalid number input OR invalid operator
        print(f"\n  Error: {e}")
        print("  Please enter valid numbers and operators.\n")

    except ZeroDivisionError as e:
        # Handles: division by zero
        print(f"\n  Error: {e}")
        print("  Try a different divisor.\n")

print("Thanks for calculating! Goodbye!")
```
</details>

---

### Exercise 2: Robust Input Function

Write a function called `get_integer(prompt)` that keeps asking the user for input until they enter a valid integer. Then use it to get the user's age.

<details>
<summary>Click to see the solution</summary>

```python
# ===== ROBUST INPUT FUNCTION =====
# This function is SO patient — it keeps asking until you give a valid number!

def get_integer(prompt, min_val=None, max_val=None):
    """
    Keep asking until the user enters a valid integer.

    Parameters:
        prompt: The message to show the user
        min_val: Minimum acceptable value (optional)
        max_val: Maximum acceptable value (optional)

    Returns:
        A valid integer
    """
    while True:
        try:
            # Try to convert the input to an integer
            value = int(input(prompt))

            # Check if it's within the acceptable range
            if min_val is not None and value < min_val:
                print(f"  Please enter a number of at least {min_val}.")
                continue

            if max_val is not None and value > max_val:
                print(f"  Please enter a number no more than {max_val}.")
                continue

            # If we get here, the input is valid!
            return value

        except ValueError:
            print("  That's not a valid integer! Try again.")

def get_float(prompt):
    """Keep asking until the user enters a valid float."""
    while True:
        try:
            value = float(input(prompt))
            return value
        except ValueError:
            print("  That's not a valid number! Try again.")

# Test the functions
print("===== User Registration =====\n")

name = input("Enter your name: ")
age = get_integer("Enter your age: ", min_val=1, max_val=150)
grade = get_integer("Enter your grade (1-12): ", min_val=1, max_val=12)
height = get_float("Enter your height in cm: ")

print(f"\n===== Registration Complete =====")
print(f"  Name:   {name}")
print(f"  Age:    {age}")
print(f"  Grade:  {grade}")
print(f"  Height: {height} cm")
```
</details>

---

### Exercise 3: File Reader with Error Handling

Write a program that:
1. Asks the user for a filename
2. Handles the case where the file doesn't exist
3. Displays the file contents with line numbers
4. Shows the total number of lines and words

<details>
<summary>Click to see the solution</summary>

```python
# ===== SAFE FILE READER =====
# Reads a file safely, handling all possible errors!

def read_file_safely(filename):
    """
    Read a file with full error handling.
    Returns the content as a list of lines, or None if there's an error.
    """
    try:
        with open(filename, "r") as file:
            lines = file.readlines()
            return lines

    except FileNotFoundError:
        print(f"  Error: The file '{filename}' was not found.")
        print(f"  Make sure the file exists and the name is spelled correctly.")
        return None

    except PermissionError:
        print(f"  Error: You don't have permission to read '{filename}'.")
        return None

    except IsADirectoryError:
        print(f"  Error: '{filename}' is a directory, not a file.")
        return None

    except Exception as e:
        print(f"  Unexpected error: {e}")
        return None

def display_file(lines, filename):
    """Display file contents with line numbers and statistics."""
    print(f"\n===== Contents of '{filename}' =====\n")

    total_words = 0
    total_chars = 0

    for i, line in enumerate(lines, 1):
        clean_line = line.rstrip("\n")  # Remove newline but keep other spaces
        words_in_line = len(clean_line.split())
        total_words += words_in_line
        total_chars += len(clean_line)
        print(f"  {i:4d} | {clean_line}")

    print(f"\n===== Statistics =====")
    print(f"  Total lines:      {len(lines)}")
    print(f"  Total words:      {total_words}")
    print(f"  Total characters: {total_chars}")
    print(f"========================\n")

# Main program
print("===== Safe File Reader =====\n")

while True:
    filename = input("Enter filename to read (or 'quit'): ")

    if filename.lower() == "quit":
        print("Goodbye!")
        break

    lines = read_file_safely(filename)

    if lines is not None:
        if len(lines) == 0:
            print(f"  The file '{filename}' is empty.\n")
        else:
            display_file(lines, filename)
```
</details>

---

### Exercise 4: Safe List Access

Write a function that safely accesses a list by index, returning a default value if the index is out of range. Then test it.

<details>
<summary>Click to see the solution</summary>

```python
# ===== SAFE LIST ACCESS =====

def safe_get(lst, index, default=None):
    """
    Safely get an item from a list by index.
    Returns 'default' if the index is out of range.
    """
    try:
        return lst[index]
    except IndexError:
        return default
    except TypeError:
        print(f"  Warning: Index must be a number, not {type(index).__name__}")
        return default

# Test the function
fruits = ["apple", "banana", "cherry"]

print("Fruits list:", fruits)
print()

# Valid access
print(f"Index 0: {safe_get(fruits, 0)}")           # apple
print(f"Index 2: {safe_get(fruits, 2)}")           # cherry

# Invalid access — doesn't crash!
print(f"Index 5: {safe_get(fruits, 5)}")           # None
print(f"Index 5: {safe_get(fruits, 5, 'unknown')}") # unknown
print(f"Index -10: {safe_get(fruits, -10, 'N/A')}") # N/A

# Even handles wrong type for index
print(f"Index 'abc': {safe_get(fruits, 'abc', 'error')}")

print("\n===== Interactive Test =====")
while True:
    user_input = input("Enter an index (or 'quit'): ")
    if user_input.lower() == "quit":
        break

    try:
        index = int(user_input)
        result = safe_get(fruits, index, "NOT FOUND")
        print(f"  fruits[{index}] = {result}")
    except ValueError:
        print("  Please enter a valid number!")
```
</details>

---

### Exercise 5: Password Validator

Write a function that validates a password. It should raise specific exceptions for different problems:
- Too short (less than 8 characters)
- No numbers
- No uppercase letters

<details>
<summary>Click to see the solution</summary>

```python
# ===== PASSWORD VALIDATOR =====

def validate_password(password):
    """
    Validate a password against multiple rules.
    Raises ValueError with a specific message if any rule fails.
    """
    errors = []  # Collect all errors instead of stopping at the first one

    # Rule 1: Minimum length
    if len(password) < 8:
        errors.append("Password must be at least 8 characters long")

    # Rule 2: Must contain a number
    has_number = False
    for char in password:
        if char.isdigit():
            has_number = True
            break
    if not has_number:
        errors.append("Password must contain at least one number")

    # Rule 3: Must contain an uppercase letter
    has_upper = False
    for char in password:
        if char.isupper():
            has_upper = True
            break
    if not has_upper:
        errors.append("Password must contain at least one uppercase letter")

    # Rule 4: Must contain a lowercase letter
    has_lower = False
    for char in password:
        if char.islower():
            has_lower = True
            break
    if not has_lower:
        errors.append("Password must contain at least one lowercase letter")

    # If there are any errors, raise them all
    if errors:
        raise ValueError("\n  - ".join(["Password problems found:"] + errors))

    return True

# Test the validator
print("===== Password Validator =====\n")

test_passwords = ["abc", "abcdefgh", "ABCDEFGH", "abcdEFGH", "Abcdefg1", "MyP@ss123"]

for pwd in test_passwords:
    try:
        validate_password(pwd)
        print(f"  '{pwd}' — VALID!")
    except ValueError as e:
        print(f"  '{pwd}' — INVALID")
        print(f"  {e}\n")

# Interactive mode
print("\n===== Try Your Own Password =====")
while True:
    password = input("Enter a password to test (or 'quit'): ")
    if password.lower() == "quit":
        break

    try:
        validate_password(password)
        print("  Strong password! You're all set!\n")
    except ValueError as e:
        print(f"  {e}\n")
```
</details>

---

### Exercise 6: Safe Dictionary Merger

Write a function that safely merges two dictionaries, handling cases where values might conflict. If both dictionaries have the same key, keep the value from the second dictionary but log a warning.

<details>
<summary>Click to see the solution</summary>

```python
# ===== SAFE DICTIONARY MERGER =====

def safe_merge(dict1, dict2):
    """
    Safely merge two dictionaries.
    If there are conflicting keys, use dict2's value and print a warning.
    Returns the merged dictionary and a list of conflicts.
    """
    # Check that both inputs are dictionaries
    if not isinstance(dict1, dict):
        raise TypeError(f"First argument must be a dict, got {type(dict1).__name__}")
    if not isinstance(dict2, dict):
        raise TypeError(f"Second argument must be a dict, got {type(dict2).__name__}")

    merged = {}
    conflicts = []

    # Add all items from dict1
    for key, value in dict1.items():
        merged[key] = value

    # Add items from dict2, checking for conflicts
    for key, value in dict2.items():
        if key in merged:
            old_value = merged[key]
            conflicts.append((key, old_value, value))
            print(f"  Warning: Key '{key}' conflict — "
                  f"'{old_value}' replaced with '{value}'")
        merged[key] = value

    return merged, conflicts

# Test it
print("===== Dictionary Merger =====\n")

student1 = {"name": "Alice", "age": 15, "grade": "A"}
student2 = {"age": 16, "school": "Python High", "grade": "A+"}

print("Dictionary 1:", student1)
print("Dictionary 2:", student2)
print()

try:
    result, conflicts = safe_merge(student1, student2)
    print(f"\nMerged result: {result}")
    print(f"Number of conflicts: {len(conflicts)}")

    # Test with invalid input
    print("\nTesting with invalid input...")
    safe_merge("not a dict", student2)

except TypeError as e:
    print(f"  Error: {e}")
```
</details>

---

### Exercise 7: Error-Proof Number Guesser

Write a number guessing game that handles every possible error: invalid input, out of range numbers, and even keyboard interrupts (Ctrl+C).

<details>
<summary>Click to see the solution</summary>

```python
# ===== ERROR-PROOF NUMBER GUESSER =====

import random

def play_guessing_game():
    """A number guessing game that handles ALL errors."""
    secret = random.randint(1, 100)
    attempts = 0
    max_attempts = 7

    print("\n===== Number Guessing Game =====")
    print(f"I'm thinking of a number between 1 and 100.")
    print(f"You have {max_attempts} attempts. Good luck!\n")

    while attempts < max_attempts:
        remaining = max_attempts - attempts
        print(f"Attempts remaining: {remaining}")

        try:
            # Get the user's guess
            user_input = input("Your guess: ")

            # Convert to integer
            guess = int(user_input)

            # Check range
            if guess < 1 or guess > 100:
                raise ValueError("Number must be between 1 and 100!")

            attempts += 1

            # Check the guess
            if guess == secret:
                print(f"\n  CORRECT! You got it in {attempts} attempt(s)!")
                return True
            elif guess < secret:
                print("  Too low! Try higher.\n")
            else:
                print("  Too high! Try lower.\n")

        except ValueError as e:
            if "invalid literal" in str(e):
                print(f"  '{user_input}' is not a number! Try again.\n")
            else:
                print(f"  {e} Try again.\n")
            # Don't count invalid inputs as attempts

        except KeyboardInterrupt:
            # Handle Ctrl+C gracefully
            print("\n\n  Game interrupted! No worries.")
            print(f"  The secret number was {secret}.")
            return False

    # Out of attempts
    print(f"\n  Out of attempts! The number was {secret}.")
    return False

# Main program
try:
    while True:
        play_guessing_game()

        try:
            play_again = input("\nPlay again? (yes/no): ")
            if play_again.lower() != "yes":
                print("Thanks for playing! Goodbye!")
                break
        except KeyboardInterrupt:
            print("\nGoodbye!")
            break

except Exception as e:
    print(f"\nUnexpected error: {e}")
    print("The game has ended.")
```
</details>

---

### Exercise 8: Multi-File Error Handler

Write a program that tries to read multiple files and reports which ones succeeded and which ones failed, without crashing.

<details>
<summary>Click to see the solution</summary>

```python
# ===== MULTI-FILE ERROR HANDLER =====

def try_read_file(filename):
    """
    Try to read a file. Returns (success, data_or_error).
    """
    try:
        with open(filename, "r") as file:
            content = file.read()
            lines = content.strip().split("\n")
            word_count = len(content.split())
            return True, {
                "content": content,
                "lines": len(lines),
                "words": word_count,
                "chars": len(content)
            }
    except FileNotFoundError:
        return False, "File not found"
    except PermissionError:
        return False, "Permission denied"
    except IsADirectoryError:
        return False, "Is a directory, not a file"
    except UnicodeDecodeError:
        return False, "File contains non-text data"
    except Exception as e:
        return False, f"Unknown error: {e}"

def batch_read_files(filenames):
    """Try to read multiple files and report results."""
    results = {
        "success": [],
        "failed": []
    }

    print("===== Batch File Reader =====\n")
    print(f"Attempting to read {len(filenames)} file(s)...\n")

    for filename in filenames:
        success, data = try_read_file(filename)

        if success:
            results["success"].append((filename, data))
            print(f"  [OK]   {filename} — {data['lines']} lines, {data['words']} words")
        else:
            results["failed"].append((filename, data))
            print(f"  [FAIL] {filename} — {data}")

    # Print summary
    print(f"\n===== Summary =====")
    print(f"  Successful: {len(results['success'])}")
    print(f"  Failed:     {len(results['failed'])}")
    print(f"  Total:      {len(filenames)}")
    print(f"====================\n")

    return results

# Create some test files
with open("test_file1.txt", "w") as f:
    f.write("Hello from file 1!\nThis file works.\n")

with open("test_file2.txt", "w") as f:
    f.write("Greetings from file 2!\nPython is awesome.\nLet's go!\n")

# Try to read a mix of existing and non-existing files
files_to_read = [
    "test_file1.txt",
    "test_file2.txt",
    "nonexistent_file.txt",
    "missing_data.csv",
    "test_file1.txt"  # This one exists
]

results = batch_read_files(files_to_read)

# Show details of successful files
if results["success"]:
    show = input("Show content of successful files? (yes/no): ")
    if show.lower() == "yes":
        for filename, data in results["success"]:
            print(f"\n--- {filename} ---")
            print(data["content"])
```
</details>

---

### Exercise 9: Input Validation Library

Create a mini library of input validation functions that use error handling.

<details>
<summary>Click to see the solution</summary>

```python
# ===== INPUT VALIDATION LIBRARY =====
# A collection of reusable safe input functions!

def get_int(prompt, min_val=None, max_val=None):
    """Get a valid integer from the user."""
    while True:
        try:
            value = int(input(prompt))
            if min_val is not None and value < min_val:
                print(f"  Must be at least {min_val}. Try again.")
                continue
            if max_val is not None and value > max_val:
                print(f"  Must be at most {max_val}. Try again.")
                continue
            return value
        except ValueError:
            print("  Please enter a whole number. Try again.")

def get_float(prompt, min_val=None, max_val=None):
    """Get a valid float from the user."""
    while True:
        try:
            value = float(input(prompt))
            if min_val is not None and value < min_val:
                print(f"  Must be at least {min_val}. Try again.")
                continue
            if max_val is not None and value > max_val:
                print(f"  Must be at most {max_val}. Try again.")
                continue
            return value
        except ValueError:
            print("  Please enter a valid number. Try again.")

def get_choice(prompt, valid_choices):
    """Get a valid choice from a list of options."""
    choices_str = ", ".join(str(c) for c in valid_choices)
    while True:
        value = input(prompt)
        if value in [str(c) for c in valid_choices]:
            return value
        print(f"  Invalid choice. Choose from: {choices_str}")

def get_yes_no(prompt):
    """Get a yes or no answer."""
    while True:
        value = input(prompt).lower().strip()
        if value in ["yes", "y"]:
            return True
        elif value in ["no", "n"]:
            return False
        print("  Please enter 'yes' or 'no'.")

def get_non_empty_string(prompt, max_length=None):
    """Get a non-empty string from the user."""
    while True:
        value = input(prompt).strip()
        if not value:
            print("  Input cannot be empty. Try again.")
            continue
        if max_length and len(value) > max_length:
            print(f"  Too long! Maximum {max_length} characters.")
            continue
        return value

# ===== Demo: Using the Library =====
print("===== Student Registration Form =====\n")

try:
    name = get_non_empty_string("Full name: ", max_length=50)
    age = get_int("Age: ", min_val=5, max_val=100)
    grade = get_int("Grade (1-12): ", min_val=1, max_val=12)
    gpa = get_float("GPA (0.0 - 4.0): ", min_val=0.0, max_val=4.0)
    sport = get_choice("Favorite sport (soccer/basketball/tennis): ",
                       ["soccer", "basketball", "tennis"])
    wants_newsletter = get_yes_no("Subscribe to newsletter? (yes/no): ")

    print(f"\n===== Registration Complete =====")
    print(f"  Name:       {name}")
    print(f"  Age:        {age}")
    print(f"  Grade:      {grade}")
    print(f"  GPA:        {gpa}")
    print(f"  Sport:      {sport}")
    print(f"  Newsletter: {'Yes' if wants_newsletter else 'No'}")
    print(f"=================================")

except KeyboardInterrupt:
    print("\n\nRegistration cancelled.")
```
</details>

---

### Exercise 10: Error Log System

Create a system that catches errors from a function, logs them to a file, and lets you view the error log later.

<details>
<summary>Click to see the solution</summary>

```python
# ===== ERROR LOG SYSTEM =====

import datetime

def log_error(error_type, error_message, function_name="unknown"):
    """Log an error to the error log file."""
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")

    with open("error_log.txt", "a") as file:
        file.write(f"[{timestamp}] {error_type} in {function_name}: {error_message}\n")

def view_error_log():
    """Display the error log."""
    try:
        with open("error_log.txt", "r") as file:
            content = file.read()
            if content.strip():
                print("\n===== ERROR LOG =====")
                print(content)
                print("=====================\n")
            else:
                print("Error log is empty. No errors recorded!\n")
    except FileNotFoundError:
        print("No error log file found. No errors yet!\n")

def clear_error_log():
    """Clear the error log."""
    with open("error_log.txt", "w") as file:
        pass  # Empty the file
    print("Error log cleared!\n")

def risky_division():
    """A function that might fail — with error logging."""
    try:
        a = int(input("Enter a number: "))
        b = int(input("Divide by: "))
        result = a / b
        print(f"Result: {result}\n")
    except ValueError as e:
        log_error("ValueError", str(e), "risky_division")
        print("Invalid number! Error has been logged.\n")
    except ZeroDivisionError as e:
        log_error("ZeroDivisionError", str(e), "risky_division")
        print("Can't divide by zero! Error has been logged.\n")

def risky_list_access():
    """Another function that might fail — with error logging."""
    items = ["apple", "banana", "cherry"]

    try:
        index = int(input(f"Enter an index (0-{len(items)-1}): "))
        print(f"Item: {items[index]}\n")
    except ValueError as e:
        log_error("ValueError", str(e), "risky_list_access")
        print("Invalid index! Error has been logged.\n")
    except IndexError as e:
        log_error("IndexError", str(e), "risky_list_access")
        print("Index out of range! Error has been logged.\n")

# Main program
print("===== Error Log Demo =====\n")

while True:
    print("1. Try division (might cause an error)")
    print("2. Try list access (might cause an error)")
    print("3. View error log")
    print("4. Clear error log")
    print("5. Quit")

    choice = input("Choose: ")

    if choice == "1":
        risky_division()
    elif choice == "2":
        risky_list_access()
    elif choice == "3":
        view_error_log()
    elif choice == "4":
        clear_error_log()
    elif choice == "5":
        print("Goodbye!")
        break
    else:
        print("Invalid choice.\n")
```
</details>

---

## Summary

| Concept | What It Does |
|---------|-------------|
| `SyntaxError` | Code has grammar mistakes |
| `NameError` | Using a variable/function that doesn't exist |
| `TypeError` | Wrong data type for an operation |
| `ValueError` | Right type but wrong value |
| `IndexError` | List index out of range |
| `KeyError` | Dictionary key not found |
| `ZeroDivisionError` | Dividing by zero |
| `FileNotFoundError` | File doesn't exist |
| `try-except` | Catch and handle errors |
| `try-except-else` | Do something extra if no error |
| `try-except-finally` | Always run cleanup code |
| `raise` | Create your own errors on purpose |
| `except Error as e` | Get the error message in variable `e` |

**Key Rules:**
1. **Always catch specific errors** — don't use bare `except:`
2. **Read error messages carefully** — they tell you what and where
3. **Use `print()` to debug** — see what your variables contain
4. **Test edge cases** — what if the list is empty? What if the user types nothing?
5. **Errors are your friends** — they help you write better code!

**You're now a Bug-Catching Champion! No error can stop your programs!**
