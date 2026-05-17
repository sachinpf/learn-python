# Lesson 09: Functions in Python

Welcome to one of the most important lessons in your Python journey -- **Functions**! Functions are the building blocks of bigger, better programs. Once you learn functions, you will be able to write code like a real software developer. Let's go!

---

## What Are Functions?

A **function** *(फंक्शन)* is a reusable block of code that performs a specific task. You write it once, and then you can use it as many times as you want!

### Analogy 1: A Recipe

Think of a function like a **recipe**. A recipe for making a sandwich:

1. Take two slices of bread
2. Spread peanut butter on one
3. Spread jelly on the other
4. Put them together

You write the recipe once. Every time you want a sandwich, you just follow the same recipe. You do not rewrite the instructions every single time!

### Analogy 2: A Machine

Think of a function like a **machine** in a factory:

```
    INPUT            MACHINE              OUTPUT
    ------          ---------            --------
    Oranges   -->   [Juicer]    -->      Orange Juice
    2, 3      -->   [Adder]     -->      5
    "hello"   -->   [Uppercaser] -->     "HELLO"
```

You put something **in** (input), the machine does its job, and something comes **out** (output).

### Why Use Functions?

1. **Avoid repeating code** -- Write once, use many times
2. **Organize your code** -- Break big problems into small, manageable pieces
3. **Make code easier to read** -- A function name tells you what it does
4. **Make code easier to fix** -- Fix a bug in one place instead of ten
5. **Share code** -- Other people can use your functions

---

## Defining Functions with `def`

To create a function, use the `def` keyword (short for "define").

```python
def say_hello():
    print("Hello there!")
    print("Welcome to Python!")
```

**Breaking it down:**
- `def` -- tells Python "I am creating a function"
- `say_hello` -- the name of the function (you choose this!)
- `()` -- parentheses (we will put parameters here later)
- `:` -- colon at the end
- The **indented code** below is the function's body (what it does)

**Important:** Defining a function does NOT run it! It is like writing a recipe but not cooking yet.

---

## Calling Functions

To actually **run** a function, you "call" it by writing its name followed by parentheses.

```python
def say_hello():
    print("Hello there!")
    print("Welcome to Python!")

# Call the function
say_hello()
```
**Output:**
```
Hello there!
Welcome to Python!
```

```python
# You can call a function as many times as you want!
def cheer():
    print("Go team! You can do it!")

cheer()
cheer()
cheer()
```
**Output:**
```
Go team! You can do it!
Go team! You can do it!
Go team! You can do it!
```

```python
# Using a function to draw a line separator
def draw_line():
    print("=" * 40)

draw_line()
print("   Welcome to My Program")
draw_line()
print("   Today we learn functions!")
draw_line()
```
**Output:**
```
========================================
   Welcome to My Program
========================================
   Today we learn functions!
========================================
```

---

## Parameters and Arguments

**Parameters** *(पॅरामीटर)* make functions flexible. Instead of always doing the same thing, a function can accept **input** and behave differently based on what you give it.

- **Parameter** = the variable name in the function definition (the placeholder)
- **Argument** *(आर्ग्युमेंट)* = the actual value you pass when calling the function

> **Easy way to remember:** **P**arameter = **P**laceholder (when you write the function). **A**rgument = **A**ctual value (when you call the function). People often use these two words interchangeably in casual speech, and that's fine — but if a tutorial or error message uses one, now you know which is which.

```python
def greet(name):       # "name" is a PARAMETER
    print(f"Hello, {name}! Nice to meet you!")

greet("Alice")         # "Alice" is an ARGUMENT
greet("Bob")           # "Bob" is an ARGUMENT
greet("Charlie")
```
**Output:**
```
Hello, Alice! Nice to meet you!
Hello, Bob! Nice to meet you!
Hello, Charlie! Nice to meet you!
```

### Multiple Parameters

```python
def introduce(name, age):
    print(f"Hi! My name is {name} and I am {age} years old.")

introduce("Alice", 14)
introduce("Bob", 13)
```
**Output:**
```
Hi! My name is Alice and I am 14 years old.
Hi! My name is Bob and I am 13 years old.
```

```python
def add(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")

add(5, 3)
add(100, 200)
add(7.5, 2.5)
```
**Output:**
```
5 + 3 = 8
100 + 200 = 300
7.5 + 2.5 = 10.0
```

```python
# A function to calculate the area of a rectangle
def rectangle_info(length, width):
    area = length * width
    perimeter = 2 * (length + width)
    print(f"Rectangle: {length} x {width}")
    print(f"  Area: {area}")
    print(f"  Perimeter: {perimeter}")
    print()

rectangle_info(10, 5)
rectangle_info(7, 3)
rectangle_info(4, 4)
```
**Output:**
```
Rectangle: 10 x 5
  Area: 50
  Perimeter: 30

Rectangle: 7 x 3
  Area: 21
  Perimeter: 20

Rectangle: 4 x 4
  Area: 16
  Perimeter: 16
```

---

## Return Values

So far, our functions have been **printing** results. But often, you want a function to **give back** *(परत देणे)* a value so you can use it later. That is what `return` does.

Think of it this way:
- **print()** -- shows something on screen (like shouting the answer)
- **return** -- hands the answer back to you (like writing it on a note and passing it)

```python
def add(a, b):
    return a + b

# The function gives back the result, and we store it
result = add(5, 3)
print(f"5 + 3 = {result}")

# You can use the returned value directly
print(f"10 + 20 = {add(10, 20)}")

# You can use it in calculations
total = add(100, 200) + add(50, 50)
print(f"Total: {total}")
```
**Output:**
```
5 + 3 = 8
10 + 20 = 30
Total: 400
```

```python
def square(number):
    return number ** 2

print(square(4))
print(square(7))
print(square(12))

# Use the return value in a list
squares = [square(n) for n in range(1, 6)]
print(f"Squares of 1-5: {squares}")
```
**Output:**
```
16
49
144
Squares of 1-5: [1, 4, 9, 16, 25]
```

```python
def is_even(number):
    """Check if a number is even."""
    return number % 2 == 0

print(is_even(4))    # True
print(is_even(7))    # False

# Using it in an if statement
num = 10
if is_even(num):
    print(f"{num} is even!")
else:
    print(f"{num} is odd!")
```
**Output:**
```
True
False
10 is even!
```

### The Difference Between print() and return

This is the **most important distinction** in this whole lesson. Read it twice if you have to!

- **`print()` SHOWS YOU something.** It puts text on the screen so a human can read it. That's it. Nothing is left over for the rest of your code to use.
- **`return` GIVES YOU something.** It hands a value back to wherever the function was called from, so the rest of your code can use it (do math with it, store it in a variable, pass it to another function).

Think of it like this: you ask a friend "what's 5 + 3?"
- If they shout "**8!**" loudly so everyone hears, that's `print`. You heard it, but you can't grab the number and use it in your homework.
- If they hand you a piece of paper with "8" written on it, that's `return`. Now you can use it.

```python
# This function PRINTS -- you see it but cannot use the value later
def add_print(a, b):
    print(a + b)

# This function RETURNS -- you get the value to use later
def add_return(a, b):
    return a + b

# Watch the difference:
result1 = add_print(5, 3)    # Prints 8, but result1 is None!
result2 = add_return(5, 3)   # Does not print, but result2 is 8

print(f"result1: {result1}")
print(f"result2: {result2}")

# Can we do math with the results?
# print(result1 * 2)  # Error! None * 2 does not work
print(result2 * 2)     # Works! 8 * 2 = 16
```
**Output:**
```
8
result1: None
result2: 8
16
```

---

## Default Parameters

You can give parameters a **default value**. If someone calls the function without providing that argument, the default is used.

```python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")

greet("Alice")                # Uses default greeting
greet("Bob", "Hi")            # Uses custom greeting
greet("Charlie", "Hey there")
```
**Output:**
```
Hello, Alice!
Hi, Bob!
Hey there, Charlie!
```

```python
def power(base, exponent=2):
    """Calculate base raised to exponent. Default is squaring."""
    return base ** exponent

print(power(5))       # 5^2 = 25 (default exponent)
print(power(5, 3))    # 5^3 = 125
print(power(2, 10))   # 2^10 = 1024
```
**Output:**
```
25
125
1024
```

```python
def make_sandwich(bread="white", filling="peanut butter", extra=None):
    print(f"Making a {bread} bread sandwich with {filling}", end="")
    if extra:
        print(f" and {extra}!")
    else:
        print("!")

make_sandwich()
make_sandwich("wheat")
make_sandwich("rye", "turkey")
make_sandwich("sourdough", "ham", "cheese")
```
**Output:**
```
Making a white bread sandwich with peanut butter!
Making a wheat bread sandwich with peanut butter!
Making a rye bread sandwich with turkey!
Making a sourdough bread sandwich with ham and cheese!
```

---

## Multiple Return Values

A function can return **more than one value** at a time using a tuple!

```python
def get_min_max(numbers):
    """Return both the minimum and maximum of a list."""
    return min(numbers), max(numbers)

scores = [78, 92, 85, 100, 67, 88]
lowest, highest = get_min_max(scores)

print(f"Scores: {scores}")
print(f"Lowest: {lowest}")
print(f"Highest: {highest}")
```
**Output:**
```
Scores: [78, 92, 85, 100, 67, 88]
Lowest: 67
Highest: 100
```

```python
def calculate_circle(radius):
    """Calculate the area and circumference of a circle."""
    import math
    area = math.pi * radius ** 2
    circumference = 2 * math.pi * radius
    return area, circumference

a, c = calculate_circle(5)
print(f"Circle with radius 5:")
print(f"  Area: {a:.2f}")
print(f"  Circumference: {c:.2f}")
```
**Output:**
```
Circle with radius 5:
  Area: 78.54
  Circumference: 31.42
```

```python
def divide(a, b):
    """Return both the quotient and remainder."""
    quotient = a // b
    remainder = a % b
    return quotient, remainder

q, r = divide(17, 5)
print(f"17 / 5 = {q} remainder {r}")

q, r = divide(100, 7)
print(f"100 / 7 = {q} remainder {r}")
```
**Output:**
```
17 / 5 = 3 remainder 2
100 / 7 = 14 remainder 2
```

---

## Scope: Local vs Global Variables

**Scope** means "where a variable can be seen and used." This is a really important concept!

### Local Variables

Variables created **inside** a function are **local** -- they only exist inside that function. Once the function is done, they disappear. Think of them as notes written on a whiteboard that gets erased after class.

```python
def my_function():
    secret = "I only exist inside this function!"
    print(secret)

my_function()

# Trying to use "secret" outside the function causes an error:
# print(secret)  # NameError: name 'secret' is not defined
```
**Output:**
```
I only exist inside this function!
```

### Global Variables

Variables created **outside** functions are **global** -- they can be seen everywhere.

```python
school_name = "Python Academy"   # Global variable

def print_school():
    print(f"Welcome to {school_name}!")   # Can READ the global variable

print_school()
print(school_name)
```
**Output:**
```
Welcome to Python Academy!
Python Academy
```

### Local vs Global -- Same Name!

If a local variable has the same name as a global variable, the function uses the **local** one. The global one is not affected.

```python
message = "I am global!"        # Global variable

def show_message():
    message = "I am local!"     # Local variable (different from global)
    print(f"Inside function: {message}")

show_message()
print(f"Outside function: {message}")
```
**Output:**
```
Inside function: I am local!
Outside function: I am global!
```

### Simple Rule of Thumb

- **Create variables inside functions** whenever possible (local is safer!)
- **Avoid changing global variables** inside functions
- **Pass data to functions** using parameters and get data back using `return`

```python
# Good practice: use parameters and return
def add_tax(price, tax_rate):
    total = price + (price * tax_rate)
    return total

item_price = 100
final = add_tax(item_price, 0.08)
print(f"Price: ${item_price}")
print(f"With tax: ${final}")
```
**Output:**
```
Price: $100
With tax: $108.0
```

---

## Built-in Functions Review

Python comes with many **built-in functions** that you have already been using. Let's review the most important ones!

### print() -- Display Output

```python
print("Hello, World!")
print("Name:", "Alice", "Age:", 14)
print(f"2 + 3 = {2 + 3}")
```
**Output:**
```
Hello, World!
Name: Alice Age: 14
2 + 3 = 5
```

### input() -- Get User Input

```python
name = input("What is your name? ")
print(f"Hello, {name}!")
# (User would type their name and press Enter)
```

### len() -- Get Length

```python
print(len("Hello"))           # Length of a string: 5
print(len([1, 2, 3, 4, 5]))  # Length of a list: 5
print(len({"a": 1, "b": 2})) # Length of a dictionary: 2
```
**Output:**
```
5
5
2
```

### type() -- Check the Data Type

```python
print(type(42))
print(type(3.14))
print(type("hello"))
print(type(True))
print(type([1, 2, 3]))
print(type({"a": 1}))
```
**Output:**
```
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
<class 'list'>
<class 'dict'>
```

### range() -- Generate a Sequence of Numbers

```python
# range(stop)
print(list(range(5)))

# range(start, stop)
print(list(range(2, 8)))

# range(start, stop, step)
print(list(range(0, 20, 3)))
```
**Output:**
```
[0, 1, 2, 3, 4]
[2, 3, 4, 5, 6, 7]
[0, 3, 6, 9, 12, 15, 18]
```

### int(), str(), float() -- Type Conversion

```python
# String to integer
age = int("14")
print(age + 1)

# Integer to string
num_str = str(42)
print("The answer is " + num_str)

# String to float
price = float("9.99")
print(price * 2)
```
**Output:**
```
15
The answer is 42
19.98
```

---

## Docstrings

A **docstring** is a special string you put at the beginning of a function to explain what it does. It is like a mini instruction manual for your function.

Use triple quotes `"""..."""` for docstrings.

```python
def calculate_average(numbers):
    """
    Calculate the average of a list of numbers.

    Parameters:
        numbers: A list of numbers

    Returns:
        The average as a float
    """
    return sum(numbers) / len(numbers)

# You can view the docstring using help()
help(calculate_average)
```
**Output:**
```
Help on function calculate_average in module __main__:

calculate_average(numbers)
    Calculate the average of a list of numbers.

    Parameters:
        numbers: A list of numbers

    Returns:
        The average as a float
```

```python
def is_palindrome(text):
    """Check if a string reads the same forwards and backwards."""
    cleaned = text.lower().replace(" ", "")
    return cleaned == cleaned[::-1]

print(is_palindrome("racecar"))
print(is_palindrome("hello"))
print(is_palindrome("A man a plan a canal Panama"))
```
**Output:**
```
True
False
True
```

---

## Functions Calling Other Functions

Functions can **call other functions**! This is how you build complex programs from simple pieces, like building with LEGO blocks.

```python
def square(n):
    """Return the square of n."""
    return n * n

def sum_of_squares(a, b):
    """Return the sum of squares of a and b."""
    return square(a) + square(b)

result = sum_of_squares(3, 4)
print(f"3^2 + 4^2 = {result}")
```
**Output:**
```
3^2 + 4^2 = 25
```

```python
def is_even(n):
    """Check if a number is even."""
    return n % 2 == 0

def is_positive(n):
    """Check if a number is positive."""
    return n > 0

def describe_number(n):
    """Give a description of a number."""
    # Call other functions!
    even_odd = "even" if is_even(n) else "odd"
    pos_neg = "positive" if is_positive(n) else "negative" if n < 0 else "zero"
    print(f"{n} is {pos_neg} and {even_odd}")

describe_number(4)
describe_number(-7)
describe_number(0)
describe_number(13)
```
**Output:**
```
4 is positive and even
-7 is negative and odd
0 is zero and even
13 is positive and odd
```

```python
# Building a formatted report using helper functions
def get_letter_grade(score):
    """Convert a numeric score to a letter grade."""
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

def get_average(scores):
    """Calculate the average of a list of scores."""
    return sum(scores) / len(scores)

def print_report(name, scores):
    """Print a student report using helper functions."""
    avg = get_average(scores)
    grade = get_letter_grade(avg)
    print(f"Student: {name}")
    print(f"  Scores: {scores}")
    print(f"  Average: {avg:.1f}")
    print(f"  Grade: {grade}")
    print()

# Use the main function
print_report("Alice", [95, 88, 92, 90])
print_report("Bob", [72, 68, 75, 80])
print_report("Charlie", [55, 62, 58, 60])
```
**Output:**
```
Student: Alice
  Scores: [95, 88, 92, 90]
  Average: 91.2
  Grade: A

Student: Bob
  Scores: [72, 68, 75, 80]
  Average: 73.8
  Grade: C

Student: Charlie
  Scores: [55, 62, 58, 60]
  Average: 58.8
  Grade: F
```

---

## Exercises

Test your skills with these exercises! Try to solve each one before looking at the solutions.

### Exercise 1: Greeting Function
Write a function `greet(name, time_of_day)` that prints a greeting based on the time of day ("morning", "afternoon", "evening").

### Exercise 2: Area Calculator
Write functions to calculate the area of:
- A rectangle (length, width)
- A triangle (base, height)
- A circle (radius)

### Exercise 3: Temperature Converter
Write two functions:
- `celsius_to_fahrenheit(celsius)` -- converts C to F
- `fahrenheit_to_celsius(fahrenheit)` -- converts F to C

Formula: F = C * 9/5 + 32

### Exercise 4: is_prime
Write a function `is_prime(n)` that returns `True` if a number is prime and `False` otherwise.

### Exercise 5: Password Checker
Write a function `check_password(password)` that checks if a password is strong. A strong password has:
- At least 8 characters
- At least one uppercase letter
- At least one lowercase letter
- At least one digit

### Exercise 6: Mini Calculator with Menu
Create a calculator program with functions for add, subtract, multiply, and divide. Show a menu and let the user choose.

### Exercise 7: Factorial
Write a function `factorial(n)` that returns the factorial of n (n! = n * (n-1) * ... * 1).

### Exercise 8: Count Vowels
Write a function `count_vowels(text)` that returns the number of vowels in a string.

### Exercise 9: List Statistics
Write a function `list_stats(numbers)` that returns the min, max, average, and sum of a list.

### Exercise 10: Reverse a String
Write a function `reverse_string(text)` that returns the reversed string without using slicing or the reversed() function.

### Exercise 11: FizzBuzz Function
Write a function `fizzbuzz(n)` that prints numbers from 1 to n. But for multiples of 3, print "Fizz". For multiples of 5, print "Buzz". For multiples of both, print "FizzBuzz".

### Exercise 12: Number Guessing Game
Write a number guessing game using functions. The program picks a random number, and the user tries to guess it. Use separate functions for generating the number, getting a guess, and checking the guess.

### Exercise 13: Word Reverser
Write a function `reverse_words(sentence)` that reverses the order of words in a sentence (not the letters).

### Exercise 14: Create a Multiplication Table Function
Write a function `multiplication_table(n)` that prints the multiplication table for a given number.

### Exercise 15: ATM Simulator
Create a simple ATM simulator with functions for checking balance, depositing money, and withdrawing money. Use a menu system.

---

## Solutions

### Solution 1: Greeting Function

```python
def greet(name, time_of_day="morning"):
    """Greet someone based on the time of day."""
    if time_of_day == "morning":
        print(f"Good morning, {name}! Rise and shine!")
    elif time_of_day == "afternoon":
        print(f"Good afternoon, {name}! How is your day going?")
    elif time_of_day == "evening":
        print(f"Good evening, {name}! Time to relax!")
    else:
        print(f"Hello, {name}!")

greet("Alice", "morning")
greet("Bob", "afternoon")
greet("Charlie", "evening")
greet("Diana")  # Uses default "morning"
```
**Output:**
```
Good morning, Alice! Rise and shine!
Good afternoon, Bob! How is your day going?
Good evening, Charlie! Time to relax!
Good morning, Diana! Rise and shine!
```

### Solution 2: Area Calculator

```python
import math

def rectangle_area(length, width):
    """Calculate the area of a rectangle."""
    return length * width

def triangle_area(base, height):
    """Calculate the area of a triangle."""
    return 0.5 * base * height

def circle_area(radius):
    """Calculate the area of a circle."""
    return math.pi * radius ** 2

# Test the functions
print(f"Rectangle (5 x 3): {rectangle_area(5, 3)}")
print(f"Triangle (base=6, height=4): {triangle_area(6, 4)}")
print(f"Circle (radius=5): {circle_area(5):.2f}")

print(f"\nRectangle (10 x 7): {rectangle_area(10, 7)}")
print(f"Triangle (base=8, height=5): {triangle_area(8, 5)}")
print(f"Circle (radius=3): {circle_area(3):.2f}")
```
**Output:**
```
Rectangle (5 x 3): 15
Triangle (base=6, height=4): 12.0
Circle (radius=5): 78.54

Rectangle (10 x 7): 70
Triangle (base=8, height=5): 20.0
Circle (radius=3): 28.27
```

### Solution 3: Temperature Converter

```python
def celsius_to_fahrenheit(celsius):
    """Convert Celsius to Fahrenheit."""
    return celsius * 9/5 + 32

def fahrenheit_to_celsius(fahrenheit):
    """Convert Fahrenheit to Celsius."""
    return (fahrenheit - 32) * 5/9

# Test conversions
print("--- Celsius to Fahrenheit ---")
for c in [0, 20, 37, 100]:
    f = celsius_to_fahrenheit(c)
    print(f"  {c}°C = {f:.1f}°F")

print("\n--- Fahrenheit to Celsius ---")
for f in [32, 68, 98.6, 212]:
    c = fahrenheit_to_celsius(f)
    print(f"  {f}°F = {c:.1f}°C")
```
**Output:**
```
--- Celsius to Fahrenheit ---
  0°C = 32.0°F
  20°C = 68.0°F
  37°C = 98.6°F
  100°C = 212.0°F

--- Fahrenheit to Celsius ---
  32°F = 0.0°C
  68°F = 20.0°C
  98.6°F = 37.0°C
  212°F = 100.0°C
```

### Solution 4: is_prime

```python
def is_prime(n):
    """Check if a number is prime."""
    if n < 2:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

# Test the function
print("Prime numbers from 1 to 30:")
primes = []
for num in range(1, 31):
    if is_prime(num):
        primes.append(num)

print(primes)

# Test individual numbers
for n in [1, 2, 7, 10, 17, 25, 29]:
    result = "is prime" if is_prime(n) else "is NOT prime"
    print(f"  {n} {result}")
```
**Output:**
```
Prime numbers from 1 to 30:
[2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
  1 is NOT prime
  2 is prime
  7 is prime
  10 is NOT prime
  17 is prime
  25 is NOT prime
  29 is prime
```

### Solution 5: Password Checker

```python
def check_password(password):
    """
    Check if a password is strong.
    Returns a tuple of (is_strong, list_of_issues).
    """
    issues = []

    if len(password) < 8:
        issues.append("Must be at least 8 characters")

    has_upper = False
    has_lower = False
    has_digit = False

    for char in password:
        if char.isupper():
            has_upper = True
        if char.islower():
            has_lower = True
        if char.isdigit():
            has_digit = True

    if not has_upper:
        issues.append("Must have at least one uppercase letter")
    if not has_lower:
        issues.append("Must have at least one lowercase letter")
    if not has_digit:
        issues.append("Must have at least one digit")

    is_strong = len(issues) == 0
    return is_strong, issues

# Test passwords
test_passwords = ["hello", "Hello123", "ALLCAPS1", "Ab1", "MyP@ssw0rd"]

for pwd in test_passwords:
    strong, issues = check_password(pwd)
    print(f"\nPassword: '{pwd}'")
    if strong:
        print("  Strong password!")
    else:
        print("  Weak password. Issues:")
        for issue in issues:
            print(f"    - {issue}")
```
**Output:**
```
Password: 'hello'
  Weak password. Issues:
    - Must be at least 8 characters
    - Must have at least one uppercase letter
    - Must have at least one digit

Password: 'Hello123'
  Strong password!

Password: 'ALLCAPS1'
  Weak password. Issues:
    - Must have at least one lowercase letter

Password: 'Ab1'
  Weak password. Issues:
    - Must be at least 8 characters

Password: 'MyP@ssw0rd'
  Strong password!
```

### Solution 6: Mini Calculator with Menu

```python
def add(a, b):
    """Add two numbers."""
    return a + b

def subtract(a, b):
    """Subtract b from a."""
    return a - b

def multiply(a, b):
    """Multiply two numbers."""
    return a * b

def divide(a, b):
    """Divide a by b."""
    if b == 0:
        return "Error: Cannot divide by zero!"
    return a / b

def get_numbers():
    """Get two numbers from the user."""
    num1 = float(input("Enter first number: "))
    num2 = float(input("Enter second number: "))
    return num1, num2

def calculator():
    """Run the calculator program."""
    print("\n===== Mini Calculator =====")

    while True:
        print("\nChoose an operation:")
        print("1. Add (+)")
        print("2. Subtract (-)")
        print("3. Multiply (*)")
        print("4. Divide (/)")
        print("5. Quit")

        choice = input("\nYour choice (1-5): ")

        if choice == "5":
            print("Thanks for using the calculator! Goodbye!")
            break

        if choice in ["1", "2", "3", "4"]:
            num1, num2 = get_numbers()

            if choice == "1":
                result = add(num1, num2)
                symbol = "+"
            elif choice == "2":
                result = subtract(num1, num2)
                symbol = "-"
            elif choice == "3":
                result = multiply(num1, num2)
                symbol = "*"
            elif choice == "4":
                result = divide(num1, num2)
                symbol = "/"

            print(f"\n{num1} {symbol} {num2} = {result}")
        else:
            print("Invalid choice! Please try again.")

# Run the calculator
# calculator()   # Uncomment this line to run interactively

# Demo with direct function calls:
print("Calculator Demo:")
print(f"10 + 5 = {add(10, 5)}")
print(f"10 - 5 = {subtract(10, 5)}")
print(f"10 * 5 = {multiply(10, 5)}")
print(f"10 / 5 = {divide(10, 5)}")
print(f"10 / 0 = {divide(10, 0)}")
```
**Output:**
```
Calculator Demo:
10 + 5 = 15
10 - 5 = 5
10 * 5 = 50
10 / 5 = 2.0
10 / 0 = Error: Cannot divide by zero!
```

### Solution 7: Factorial

```python
def factorial(n):
    """Calculate the factorial of n (n! = n * (n-1) * ... * 1)."""
    if n < 0:
        return "Error: Factorial is not defined for negative numbers"
    if n == 0 or n == 1:
        return 1

    result = 1
    for i in range(2, n + 1):
        result *= i
    return result

# Test the function
for num in [0, 1, 5, 7, 10]:
    print(f"{num}! = {factorial(num)}")
```
**Output:**
```
0! = 1
1! = 1
5! = 120
7! = 5040
10! = 3628800
```

### Solution 8: Count Vowels

```python
def count_vowels(text):
    """Count the number of vowels in a string."""
    vowels = "aeiouAEIOU"
    count = 0
    for char in text:
        if char in vowels:
            count += 1
    return count

# Test the function
test_strings = ["Hello World", "Python", "AEIOU", "rhythm", "Beautiful Day"]

for s in test_strings:
    v = count_vowels(s)
    print(f"'{s}' has {v} vowel(s)")
```
**Output:**
```
'Hello World' has 3 vowel(s)
'Python' has 1 vowel(s)
'AEIOU' has 5 vowel(s)
'rhythm' has 0 vowel(s)
'Beautiful Day' has 6 vowel(s)
```

### Solution 9: List Statistics

```python
def list_stats(numbers):
    """Return statistics about a list of numbers."""
    minimum = min(numbers)
    maximum = max(numbers)
    total = sum(numbers)
    average = total / len(numbers)
    return minimum, maximum, total, average

# Test the function
scores = [85, 92, 78, 100, 67, 88, 95]

mn, mx, total, avg = list_stats(scores)
print(f"Numbers: {scores}")
print(f"  Minimum: {mn}")
print(f"  Maximum: {mx}")
print(f"  Sum:     {total}")
print(f"  Average: {avg:.2f}")
print(f"  Count:   {len(scores)}")
```
**Output:**
```
Numbers: [85, 92, 78, 100, 67, 88, 95]
  Minimum: 67
  Maximum: 100
  Sum:     605
  Average: 86.43
  Count:   7
```

### Solution 10: Reverse a String

```python
def reverse_string(text):
    """Reverse a string without using slicing or reversed()."""
    result = ""
    for i in range(len(text) - 1, -1, -1):
        result += text[i]
    return result

# Test the function
test_words = ["hello", "Python", "racecar", "12345"]

for word in test_words:
    reversed_word = reverse_string(word)
    print(f"'{word}' reversed is '{reversed_word}'")
    if word == reversed_word:
        print(f"  ^ This is a palindrome!")
```
**Output:**
```
'hello' reversed is 'olleh'
'Python' reversed is 'nohtyP'
'racecar' reversed is 'racecar'
  ^ This is a palindrome!
'12345' reversed is '54321'
```

### Solution 11: FizzBuzz Function

```python
def fizzbuzz(n):
    """Print FizzBuzz from 1 to n."""
    for i in range(1, n + 1):
        if i % 3 == 0 and i % 5 == 0:
            print("FizzBuzz", end=" ")
        elif i % 3 == 0:
            print("Fizz", end=" ")
        elif i % 5 == 0:
            print("Buzz", end=" ")
        else:
            print(i, end=" ")
    print()  # New line at the end

print("FizzBuzz up to 20:")
fizzbuzz(20)

print("\nFizzBuzz up to 30:")
fizzbuzz(30)
```
**Output:**
```
FizzBuzz up to 20:
1 2 Fizz 4 Buzz Fizz 7 8 Fizz Buzz 11 Fizz 13 14 FizzBuzz 16 17 Fizz 19 Buzz

FizzBuzz up to 30:
1 2 Fizz 4 Buzz Fizz 7 8 Fizz Buzz 11 Fizz 13 14 FizzBuzz 16 17 Fizz 19 Buzz Fizz 22 23 Fizz Buzz 26 Fizz 28 29 FizzBuzz
```

### Solution 12: Number Guessing Game

```python
import random

def generate_number(low, high):
    """Generate a random number between low and high."""
    return random.randint(low, high)

def get_guess(attempt):
    """Get a guess from the user."""
    guess = int(input(f"Attempt {attempt} - Enter your guess: "))
    return guess

def check_guess(guess, secret):
    """Check the guess and return a hint."""
    if guess == secret:
        return "correct"
    elif guess < secret:
        return "higher"
    else:
        return "lower"

def play_game():
    """Play the number guessing game."""
    low, high = 1, 50
    secret = generate_number(low, high)
    max_attempts = 7

    print(f"\nI am thinking of a number between {low} and {high}.")
    print(f"You have {max_attempts} attempts. Good luck!\n")

    for attempt in range(1, max_attempts + 1):
        guess = get_guess(attempt)
        result = check_guess(guess, secret)

        if result == "correct":
            print(f"Congratulations! You got it in {attempt} attempt(s)!")
            return
        elif result == "higher":
            print("Too low! Go higher.")
        else:
            print("Too high! Go lower.")

    print(f"\nOut of attempts! The number was {secret}.")

# To play: uncomment the line below
# play_game()

# Demo showing the functions work:
print("=== Guessing Game Demo ===")
secret = 25
print(f"Secret number: {secret}")
print(f"Guess 10: {check_guess(10, secret)}")
print(f"Guess 30: {check_guess(30, secret)}")
print(f"Guess 25: {check_guess(25, secret)}")
```
**Output:**
```
=== Guessing Game Demo ===
Secret number: 25
Guess 10: higher
Guess 30: lower
Guess 25: correct
```

### Solution 13: Word Reverser

```python
def reverse_words(sentence):
    """Reverse the order of words in a sentence."""
    words = sentence.split()
    reversed_words = words[::-1]
    return " ".join(reversed_words)

# Test the function
test_sentences = [
    "Hello World",
    "I love Python programming",
    "The quick brown fox jumps over the lazy dog"
]

for sentence in test_sentences:
    reversed_sentence = reverse_words(sentence)
    print(f"Original: {sentence}")
    print(f"Reversed: {reversed_sentence}")
    print()
```
**Output:**
```
Original: Hello World
Reversed: World Hello

Original: I love Python programming
Reversed: programming Python love I

Original: The quick brown fox jumps over the lazy dog
Reversed: dog lazy the over jumps fox brown quick The
```

### Solution 14: Multiplication Table Function

```python
def multiplication_table(n, up_to=10):
    """Print the multiplication table for n."""
    print(f"\n--- Multiplication Table for {n} ---")
    for i in range(1, up_to + 1):
        result = n * i
        print(f"  {n} x {i:2} = {result:3}")

multiplication_table(5)
multiplication_table(7)
multiplication_table(12, 5)  # Only up to 5
```
**Output:**
```
--- Multiplication Table for 5 ---
  5 x  1 =   5
  5 x  2 =  10
  5 x  3 =  15
  5 x  4 =  20
  5 x  5 =  25
  5 x  6 =  30
  5 x  7 =  35
  5 x  8 =  40
  5 x  9 =  45
  5 x 10 =  50

--- Multiplication Table for 7 ---
  7 x  1 =   7
  7 x  2 =  14
  7 x  3 =  21
  7 x  4 =  28
  7 x  5 =  35
  7 x  6 =  42
  7 x  7 =  49
  7 x  8 =  56
  7 x  9 =  63
  7 x 10 =  70

--- Multiplication Table for 12 ---
  12 x  1 =  12
  12 x  2 =  24
  12 x  3 =  36
  12 x  4 =  48
  12 x  5 =  60
```

### Solution 15: ATM Simulator

```python
def check_balance(balance):
    """Display the current balance."""
    print(f"\n  Your current balance is: ${balance:.2f}")

def deposit(balance):
    """Deposit money and return the new balance."""
    amount = float(input("  Enter deposit amount: $"))
    if amount <= 0:
        print("  Invalid amount! Must be positive.")
        return balance
    balance += amount
    print(f"  Deposited ${amount:.2f}")
    print(f"  New balance: ${balance:.2f}")
    return balance

def withdraw(balance):
    """Withdraw money and return the new balance."""
    amount = float(input("  Enter withdrawal amount: $"))
    if amount <= 0:
        print("  Invalid amount! Must be positive.")
        return balance
    if amount > balance:
        print("  Insufficient funds!")
        print(f"  Your balance is only ${balance:.2f}")
        return balance
    balance -= amount
    print(f"  Withdrew ${amount:.2f}")
    print(f"  New balance: ${balance:.2f}")
    return balance

def atm():
    """Run the ATM simulator."""
    balance = 1000.00  # Starting balance
    pin = "1234"

    print("\n===== Welcome to Python Bank ATM =====")
    entered_pin = input("Enter your PIN: ")

    if entered_pin != pin:
        print("Incorrect PIN! Access denied.")
        return

    print("PIN accepted! Welcome!")

    while True:
        print("\n----- ATM Menu -----")
        print("1. Check Balance")
        print("2. Deposit")
        print("3. Withdraw")
        print("4. Exit")

        choice = input("Choose (1-4): ")

        if choice == "1":
            check_balance(balance)
        elif choice == "2":
            balance = deposit(balance)
        elif choice == "3":
            balance = withdraw(balance)
        elif choice == "4":
            print(f"\nFinal balance: ${balance:.2f}")
            print("Thank you for using Python Bank ATM!")
            print("Have a great day!")
            break
        else:
            print("Invalid choice!")

# To run: uncomment the line below
# atm()

# Demo showing the functions work:
print("=== ATM Demo (Function Tests) ===")
balance = 1000.00
print(f"Starting balance: ${balance:.2f}")

check_balance(balance)
```
**Output:**
```
=== ATM Demo (Function Tests) ===
Starting balance: $1000.00

  Your current balance is: $1000.00
```

---

## Summary

Congratulations! You now know how to create and use **functions** -- one of the most important skills in programming!

| Concept | What You Learned |
|---------|-----------------|
| Defining | `def function_name(parameters):` |
| Calling | `function_name(arguments)` |
| Parameters | Variables that receive input values |
| Return | `return value` sends a result back |
| Default params | `def func(x, y=10):` |
| Multiple returns | `return a, b, c` |
| Scope | Local (inside function) vs Global (outside) |
| Docstrings | `"""Description of the function."""` |
| Built-in functions | `print()`, `input()`, `len()`, `type()`, `range()`, `int()`, `str()`, `float()` |
| Calling functions | Functions can call other functions |

### Golden Rules for Functions

1. **Each function should do ONE thing** -- keep them focused
2. **Give functions clear names** -- `calculate_area` is better than `func1`
3. **Use parameters** instead of relying on global variables
4. **Use return** to send results back (instead of printing inside the function)
5. **Add docstrings** so others (and future you!) understand what the function does
6. **Keep functions short** -- if a function is getting really long, break it into smaller functions

You are making incredible progress! Functions are what separate beginners from intermediate programmers, and you just leveled up! Keep practicing, keep building, and keep having fun with Python!

Happy coding!
