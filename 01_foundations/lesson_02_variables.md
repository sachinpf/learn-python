# Lesson 02: Variables - Giving Names to Things

---

## What Are Variables?

Imagine you have a bunch of **labeled boxes** in your room.

- One box is labeled **"Name"** and inside it you put a piece of paper that says "Sachin."
- Another box is labeled **"Age"** and inside it you put the number 10.
- A third box is labeled **"Favorite Color"** and inside it you put "Blue."

In Python, **variables** (चल — एखादे मूल्य ठेवण्यासाठीचे नाव) work exactly like these labeled boxes. A variable is a **name** that stores a **value** (मूल्य — चलामध्ये ठेवलेली माहिती). You can look inside the box anytime to see what is in it, and you can even swap out what is inside for something new!

```python
name = "Sachin"
age = 10
favorite_color = "Blue"
```

Here, `name`, `age`, and `favorite_color` are the **labels** on the boxes. `"Sachin"`, `10`, and `"Blue"` are the things **inside** the boxes.

---

## Creating Variables

Creating a variable in Python is super easy. You just write:

```
variable_name = value
```

The `=` sign does **not** mean "equals" like in math class. In Python, `=` means **"store this value in this variable."** Think of it as an arrow pointing left: take the value on the right and put it into the box on the left.

```
   age   =   10
    ▲         │
    └─────────┘
   (the value 10 flows into the box called 'age')
```

> **Watch out!** Because `=` is one-way (right → left), `10 = age` is a mistake — you cannot put a box into a number! Always write the variable name on the **left**.

```python
message = "Hello, World!"
lucky_number = 7
temperature = 36.5
is_sunny = True
```

Now let's print these variables to see what is inside:

```python
message = "Hello, World!"
lucky_number = 7
temperature = 36.5
is_sunny = True

print(message)
print(lucky_number)
print(temperature)
print(is_sunny)
```

**Output:**
```
Hello, World!
7
36.5
True
```

> **Notice:** When you print a variable, you do NOT put quotes around its name. Writing `print(message)` prints what is inside the variable. Writing `print("message")` would print the word "message" literally.

```python
name = "Sachin"

print(name)       # Prints what is inside the variable
print("name")     # Prints the word "name" literally
```

**Output:**
```
Sachin
name
```

See the difference? This is very important!

---

## Variable Naming Rules

You cannot name your variables just anything. Python has some rules:

### The Rules (You MUST follow these):

| Rule | OK | NOT OK |
|------|----|--------|
| Must start with a letter or underscore `_` | `name`, `_score` | `1name`, `@score` |
| Can contain letters, numbers, and underscores | `player1`, `high_score` | `player-1`, `high score` |
| Cannot contain spaces | `my_name` | `my name` |
| Cannot be a Python keyword | `color` | `print`, `if`, `for` |
| Case sensitive (uppercase and lowercase matter) | `Name` and `name` are DIFFERENT variables | -- |

### Tips for Good Variable Names:

- Use **descriptive names** that explain what the variable stores:
  ```python
  # Good - you can tell what these store
  student_name = "Priya"
  student_age = 12

  # Bad - these names are confusing
  x = "Priya"
  y = 12
  ```

- Use **snake_case** for variable names (lowercase words separated by underscores):
  ```python
  favorite_food = "Pizza"       # Good: snake_case
  favoriteFood = "Pizza"        # Works, but not the Python style
  FAVORITE_FOOD = "Pizza"       # Usually reserved for constants
  ```

---

## Types of Data: str, int, float, bool

Not everything you store in a variable is the same kind of thing. Your name is text, your age is a whole number, your height might be a decimal number, and "Are you a student?" is either yes or no.

Python has different **data types** (डेटा प्रकार — डेटाचा वर्ग: संख्या, स्ट्रिंग, बूलियन इत्यादी) for these:

### 1. `str` (String) -- Text

A **string** (स्ट्रिंग — अवतरण चिन्हांतील अक्षरांची मालिका) is any text wrapped in quotes. It can contain letters, numbers, spaces, symbols -- anything!

```python
first_name = "Sachin"
greeting = "Hello, how are you?"
address = "123 Main Street"
emoji_text = "I love Python! :)"
```

Strings must always be in quotes (single `'...'` or double `"..."`).

### 2. `int` (Integer) -- Whole Numbers

An **integer** (पूर्णांक — दशांशविनाचा पूर्ण संख्या प्रकार) is a whole number -- no decimal point. It can be positive, negative, or zero.

```python
age = 10
score = 95
temperature = -5
zero = 0
big_number = 1000000
```

> **Note:** Numbers do NOT go in quotes. `age = 10` stores a number. `age = "10"` stores a string (text that looks like a number but is not actually a number).

### 3. `float` (Floating Point) -- Decimal Numbers

A **float** (दशांश — दशांश चिन्ह असलेली संख्या) is a number that has a **decimal point**.

```python
height = 4.5
price = 99.99
pi = 3.14159
negative_float = -2.7
```

> **Fun Fact:** They are called "floating point" numbers because the decimal point can "float" to different positions (like 3.14 vs 314.0).

### 4. `bool` (Boolean) -- True or False

A **boolean** (बूलियन — True किंवा False, फक्त दोन मूल्यांचा प्रकार) can only be one of two values: `True` or `False`. Think of it like a light switch -- it is either ON or OFF.

```python
is_student = True
is_raining = False
likes_python = True
has_pet = False
```

> **Important:** `True` and `False` must start with a **capital letter**. Writing `true` or `false` (lowercase) will cause an error!

### Quick Summary Table

| Type    | What It Stores       | Examples                        |
|---------|----------------------|---------------------------------|
| `str`   | Text                 | `"Hello"`, `'Python'`, `"123"` |
| `int`   | Whole numbers        | `10`, `-5`, `0`, `1000`        |
| `float` | Decimal numbers      | `3.14`, `-2.5`, `99.99`        |
| `bool`  | True or False        | `True`, `False`                |

---

## The `type()` Function

Not sure what type a variable is? Ask Python using the `type()` **function** (फंक्शन — नाव दिलेला, एक काम करणारा कोडाचा गट)!

```python
name = "Sachin"
age = 10
height = 4.5
is_student = True

print(type(name))
print(type(age))
print(type(height))
print(type(is_student))
```

**Output:**
```
<class 'str'>
<class 'int'>
<class 'float'>
<class 'bool'>
```

This tells you:
- `name` is a `str` (string)
- `age` is an `int` (integer)
- `height` is a `float`
- `is_student` is a `bool` (boolean)

You can also use `type()` directly on values:

```python
print(type("Hello"))
print(type(42))
print(type(3.14))
print(type(True))
```

**Output:**
```
<class 'str'>
<class 'int'>
<class 'float'>
<class 'bool'>
```

---

## Changing Variable Values

Remember the labeled box analogy? You can always **take out** what is in the box and **put something new** in. The label stays the same, but the contents change.

```python
favorite_food = "Pizza"
print(favorite_food)

favorite_food = "Ice Cream"
print(favorite_food)

favorite_food = "Biryani"
print(favorite_food)
```

**Output:**
```
Pizza
Ice Cream
Biryani
```

The variable `favorite_food` changed its value three times. Python always uses the **most recent** value.

> **Common worry:** "Doesn't `favorite_food = "Pizza"` followed by `favorite_food = "Ice Cream"` cause a conflict?" Nope! The old value is simply thrown away. There's only ever **one thing** in the box at a time.

### A surprising trick: updating a variable using itself

This looks impossible in math class, but it works in Python:

```python
score = 10
score = score + 5
print(score)
```

**Output:**
```
15
```

How? Python reads the **right side first**: "what is `score + 5`?" It looks up `score` (currently 10), adds 5, and gets 15. **Then** it stores 15 back into `score`. Old value gone, new value in the box.

This pattern — `score = score + 5` — is one of the most useful tricks in programming. You'll see it everywhere when we get to loops!

You can even change the type of data in a variable (though this is not always a good idea):

```python
my_variable = "Hello"     # It is a string
print(my_variable)
print(type(my_variable))

my_variable = 42           # Now it is an integer
print(my_variable)
print(type(my_variable))
```

**Output:**
```
Hello
<class 'str'>
42
<class 'int'>
```

---

## Multiple Assignment

Python lets you create several variables at once in a single line. This is called **multiple assignment**.

### Assign Different Values to Different Variables

```python
name, age, city = "Sachin", 10, "Mumbai"

print(name)
print(age)
print(city)
```

**Output:**
```
Sachin
10
Mumbai
```

### Assign the Same Value to Multiple Variables

```python
x = y = z = 0

print(x)
print(y)
print(z)
```

**Output:**
```
0
0
0
```

This is handy when you want to set several variables to the same starting value.

---

## The `input()` Function -- Getting User Input

So far, all the values in our programs have been decided by us (the programmer). But what if you want the **user** (the person running the program) to type something?

That is where `input()` (इनपुट — कार्यक्रमात आत येणारी माहिती) comes in! The `input()` function **pauses** the program and **waits** for the user to type something.

```python
name = input("What is your name? ")
print("Hello,", name, "!")
```

**How to run this in PyCharm:**
1. Write the code in your Python file.
2. Click the green Run button.
3. Look at the **Run window** at the bottom of PyCharm.
4. You will see the text `What is your name? ` and a blinking cursor.
5. **Click inside the Run window**, type your name, and press **Enter**.
6. The program will continue and print the greeting.

**Example interaction:**
```
What is your name? Sachin
Hello, Sachin !
```

### How `input()` Works

1. The text inside `input("...")` is the **prompt** -- the message shown to the user.
2. The program **waits** for the user to type something and press Enter.
3. Whatever the user types is **returned as a string** and stored in the variable.

```python
color = input("What is your favorite color? ")
print("Wow,", color, "is a great color!")
```

**Example interaction:**
```
What is your favorite color? Blue
Wow, Blue is a great color!
```

> **Very Important:** `input()` ALWAYS returns a **string**, even if the user types a number!

```python
age = input("How old are you? ")
print(age)
print(type(age))
```

**Example interaction:**
```
How old are you? 10
10
<class 'str'>
```

Even though the user typed `10`, Python treats it as the **string** `"10"`, not the number `10`. This matters when you want to do math, as we will see next!

> **Why does this happen?** Python cannot read your mind. When you type `10`, Python has no way to know whether you meant the **number** ten (for math) or the **text** "10" (like a house number or a phone number — where math would be silly). So `input()` plays it safe and always gives you text. **You** decide if it should be a number by converting it with `int()` or `float()`, which you'll learn next.

---

## Converting Types: int(), float(), str()

Since `input()` always gives us a string, we need a way to **convert** (change) data from one type to another. Python has built-in functions for this:

### `int()` -- Convert to Integer

```python
age_text = "10"          # This is a string
age_number = int("10")   # This converts it to an integer

print(type(age_text))
print(type(age_number))
```

**Output:**
```
<class 'str'>
<class 'int'>
```

**Using it with `input()`:**

```python
age = input("How old are you? ")    # age is a string
age = int(age)                       # now age is an integer

next_year = age + 1
print("Next year you will be", next_year)
```

**Example interaction:**
```
How old are you? 10
Next year you will be 11
```

**Shortcut:** You can combine `input()` and `int()` in one line:

```python
age = int(input("How old are you? "))
```

### `float()` -- Convert to Float

```python
height = float(input("How tall are you in feet? "))
print("You are", height, "feet tall!")
print(type(height))
```

**Example interaction:**
```
How tall are you in feet? 4.5
You are 4.5 feet tall!
<class 'float'>
```

### `str()` -- Convert to String

```python
age = 10
age_text = str(age)

print(type(age))
print(type(age_text))
```

**Output:**
```
<class 'int'>
<class 'str'>
```

This is useful when you need to combine a number with text (as we will see in the next section).

### Quick Reference

| Function   | What It Does                          | Example                  |
|------------|---------------------------------------|--------------------------|
| `int()`    | Converts to a whole number            | `int("10")` gives `10`  |
| `float()`  | Converts to a decimal number          | `float("3.5")` gives `3.5` |
| `str()`    | Converts to text                      | `str(10)` gives `"10"`  |

---

## String Concatenation with `+`

**Concatenation** is a big word that means **joining strings together**. You can use the `+` sign to glue strings together:

```python
first_name = "Sachin"
last_name = "Fegade"
full_name = first_name + " " + last_name

print(full_name)
```

**Output:**
```
Sachin Fegade
```

Notice we added `" "` (a space) in between, otherwise the names would be smashed together:

```python
# Without a space
print("Sachin" + "Fegade")

# With a space
print("Sachin" + " " + "Fegade")
```

**Output:**
```
SachinFegade
Sachin Fegade
```

### Concatenation Only Works with Strings!

You **cannot** concatenate a string and a number directly. Python will give you an error:

```python
age = 10
# This will cause an ERROR:
# print("I am " + age + " years old.")

# Solution: Convert the number to a string first
print("I am " + str(age) + " years old.")
```

**Output:**
```
I am 10 years old.
```

---

## f-strings (Formatted Strings) -- The Easy Way!

Concatenation with `+` can get messy with lots of variables. Python has a much easier way called **f-strings** (the "f" stands for "formatted").

Just put an `f` before the opening quote and put your variables inside **curly braces** `{}`:

```python
name = "Sachin"
age = 10

print(f"My name is {name} and I am {age} years old.")
```

**Output:**
```
My name is Sachin and I am 10 years old.
```

No need to convert numbers to strings. No need for `+` signs. Clean and simple!

### More f-string Examples

```python
item = "notebook"
price = 45.50

print(f"The {item} costs {price} rupees.")
```

**Output:**
```
The notebook costs 45.5 rupees.
```

You can even do **math** inside the curly braces:

```python
length = 5
width = 3

print(f"The area of the rectangle is {length * width} square units.")
```

**Output:**
```
The area of the rectangle is 15 square units.
```

### f-strings vs Concatenation -- Comparison

```python
name = "Priya"
age = 12
city = "Delhi"

# Using concatenation (the hard way)
print("My name is " + name + ", I am " + str(age) + " years old, and I live in " + city + ".")

# Using f-strings (the easy way)
print(f"My name is {name}, I am {age} years old, and I live in {city}.")
```

**Output (both produce the same result):**
```
My name is Priya, I am 12 years old, and I live in Delhi.
My name is Priya, I am 12 years old, and I live in Delhi.
```

The f-string version is so much easier to read and write!

> **Tip:** f-strings are the preferred way to format strings in modern Python. Get comfortable using them!

---

## Summary

| Concept              | Example                                   |
|----------------------|-------------------------------------------|
| Create a variable    | `name = "Sachin"`                         |
| Print a variable     | `print(name)`                             |
| Check the type       | `print(type(name))`                       |
| String               | `"Hello"` or `'Hello'`                    |
| Integer              | `42`                                      |
| Float                | `3.14`                                    |
| Boolean              | `True` or `False`                         |
| Get user input       | `name = input("Your name? ")`             |
| Convert to int       | `int("10")`                               |
| Convert to float     | `float("3.5")`                            |
| Convert to string    | `str(10)`                                 |
| Concatenation        | `"Hello" + " " + "World"`                 |
| f-string             | `f"I am {age} years old"`                 |
| Multiple assignment  | `a, b, c = 1, 2, 3`                      |

---

## Exercises

Create a new Python file in PyCharm for each exercise (or put them all in one file -- your choice!). Remember to run each program using the green Play button or by right-clicking and selecting Run.

---

### Exercise 1: All About Me

Create variables for your name, age, city, and favorite hobby. Print a short paragraph about yourself using these variables.

**Example Output:**
```
Hi! My name is Sachin. I am 10 years old.
I live in Mumbai and I love playing cricket.
```

---

### Exercise 2: Name and Type

Create one variable of each type (str, int, float, bool). Print the value AND the type of each variable.

**Example Output:**
```
Value: Sachin, Type: <class 'str'>
Value: 10, Type: <class 'int'>
Value: 4.5, Type: <class 'float'>
Value: True, Type: <class 'bool'>
```

---

### Exercise 3: Swap the Values

Create two variables `a = 5` and `b = 10`. Swap their values so that `a` becomes `10` and `b` becomes `5`. Print both before and after swapping.

**Expected Output:**
```
Before swap: a = 5, b = 10
After swap: a = 10, b = 5
```

---

### Exercise 4: Greeting Program

Write a program that asks the user for their name and then greets them.

**Example Interaction:**
```
What is your name? Priya
Hello, Priya! Welcome to Python!
```

---

### Exercise 5: Age Calculator

Ask the user for their birth year. Calculate and print their age.

**Example Interaction:**
```
What year were you born? 2014
You are 12 years old!
```

(Hint: The current year is 2026. Use `int()` to convert the input.)

---

### Exercise 6: Mad Libs Game

Ask the user for a noun, a verb, an adjective, and a name. Then print a funny sentence using their answers.

**Example Interaction:**
```
Enter a noun: elephant
Enter a verb: danced
Enter an adjective: sparkly
Enter a name: Rahul

Rahul saw a sparkly elephant that danced in the park!
```

---

### Exercise 7: Rectangle Info

Ask the user for the length and width of a rectangle. Print the area and perimeter.

**Example Interaction:**
```
Enter the length: 5
Enter the width: 3
The area is 15 square units.
The perimeter is 16 units.
```

---

### Exercise 8: Temperature Converter (Concept Preview)

Ask the user for a temperature in Celsius. Convert it to Fahrenheit and print the result.

**Formula:** `Fahrenheit = (Celsius * 9/5) + 32`

**Example Interaction:**
```
Enter temperature in Celsius: 37
37.0 degrees Celsius is 98.6 degrees Fahrenheit.
```

---

### Exercise 9: String Repetition

Ask the user for a word and a number. Print the word repeated that many times.

**Example Interaction:**
```
Enter a word: Ha
Enter a number: 5
HaHaHaHaHa
```

(Hint: You can multiply a string by a number! Try `"Ha" * 3`)

---

### Exercise 10: Personal ID Card

Ask the user for their name, age, school, and favorite subject. Then print a formatted ID card.

**Example Interaction:**
```
Enter your name: Sachin
Enter your age: 10
Enter your school: Delhi Public School
Enter your favorite subject: Science

============================
       STUDENT ID CARD
============================
Name    : Sachin
Age     : 10
School  : Delhi Public School
Subject : Science
============================
```

---

### Exercise 11: f-string Practice

Create variables for an item name, quantity, and price per item. Use an f-string to print a receipt line that shows the total cost.

**Example Output:**
```
Item: Pencil
Quantity: 12
Price per item: 5 rupees
Total: 60 rupees
```

---

### Exercise 12: Story Builder

Ask the user for their name, a friend's name, a place, and a food item. Print a short story using all four inputs.

**Example Interaction:**
```
Enter your name: Sachin
Enter your friend's name: Rahul
Enter a place: the moon
Enter a food: pizza

One day, Sachin and Rahul went on an adventure to the moon.
They were very hungry, so they ordered pizza.
It was the best day ever!
```

---

## Solutions

---

### Solution 1: All About Me

```python
name = "Sachin"
age = 10
city = "Mumbai"
hobby = "playing cricket"

print(f"Hi! My name is {name}. I am {age} years old.")
print(f"I live in {city} and I love {hobby}.")
```

**Output:**
```
Hi! My name is Sachin. I am 10 years old.
I live in Mumbai and I love playing cricket.
```

---

### Solution 2: Name and Type

```python
my_string = "Sachin"
my_int = 10
my_float = 4.5
my_bool = True

print(f"Value: {my_string}, Type: {type(my_string)}")
print(f"Value: {my_int}, Type: {type(my_int)}")
print(f"Value: {my_float}, Type: {type(my_float)}")
print(f"Value: {my_bool}, Type: {type(my_bool)}")
```

**Output:**
```
Value: Sachin, Type: <class 'str'>
Value: 10, Type: <class 'int'>
Value: 4.5, Type: <class 'float'>
Value: True, Type: <class 'bool'>
```

---

### Solution 3: Swap the Values

```python
a = 5
b = 10

print(f"Before swap: a = {a}, b = {b}")

# Swap using a temporary variable
temp = a
a = b
b = temp

print(f"After swap: a = {a}, b = {b}")
```

**Output:**
```
Before swap: a = 5, b = 10
After swap: a = 10, b = 5
```

**Bonus -- Python shortcut for swapping:**

```python
a = 5
b = 10

print(f"Before swap: a = {a}, b = {b}")

a, b = b, a   # Python makes swapping super easy!

print(f"After swap: a = {a}, b = {b}")
```

---

### Solution 4: Greeting Program

```python
name = input("What is your name? ")
print(f"Hello, {name}! Welcome to Python!")
```

**Example Interaction:**
```
What is your name? Priya
Hello, Priya! Welcome to Python!
```

---

### Solution 5: Age Calculator

```python
birth_year = int(input("What year were you born? "))
age = 2026 - birth_year
print(f"You are {age} years old!")
```

**Example Interaction:**
```
What year were you born? 2014
You are 12 years old!
```

---

### Solution 6: Mad Libs Game

```python
noun = input("Enter a noun: ")
verb = input("Enter a verb: ")
adjective = input("Enter an adjective: ")
name = input("Enter a name: ")

print()
print(f"{name} saw a {adjective} {noun} that {verb} in the park!")
```

**Example Interaction:**
```
Enter a noun: elephant
Enter a verb: danced
Enter an adjective: sparkly
Enter a name: Rahul

Rahul saw a sparkly elephant that danced in the park!
```

---

### Solution 7: Rectangle Info

```python
length = float(input("Enter the length: "))
width = float(input("Enter the width: "))

area = length * width
perimeter = 2 * (length + width)

print(f"The area is {area} square units.")
print(f"The perimeter is {perimeter} units.")
```

**Example Interaction:**
```
Enter the length: 5
Enter the width: 3
The area is 15.0 square units.
The perimeter is 16.0 units.
```

---

### Solution 8: Temperature Converter

```python
celsius = float(input("Enter temperature in Celsius: "))
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius} degrees Celsius is {fahrenheit} degrees Fahrenheit.")
```

**Example Interaction:**
```
Enter temperature in Celsius: 37
37.0 degrees Celsius is 98.6 degrees Fahrenheit.
```

---

### Solution 9: String Repetition

```python
word = input("Enter a word: ")
number = int(input("Enter a number: "))

print(word * number)
```

**Example Interaction:**
```
Enter a word: Ha
Enter a number: 5
HaHaHaHaHa
```

---

### Solution 10: Personal ID Card

```python
name = input("Enter your name: ")
age = input("Enter your age: ")
school = input("Enter your school: ")
subject = input("Enter your favorite subject: ")

print()
print("============================")
print("       STUDENT ID CARD")
print("============================")
print(f"Name    : {name}")
print(f"Age     : {age}")
print(f"School  : {school}")
print(f"Subject : {subject}")
print("============================")
```

**Example Interaction:**
```
Enter your name: Sachin
Enter your age: 10
Enter your school: Delhi Public School
Enter your favorite subject: Science

============================
       STUDENT ID CARD
============================
Name    : Sachin
Age     : 10
School  : Delhi Public School
Subject : Science
============================
```

---

### Solution 11: f-string Practice

```python
item = "Pencil"
quantity = 12
price = 5

total = quantity * price

print(f"Item: {item}")
print(f"Quantity: {quantity}")
print(f"Price per item: {price} rupees")
print(f"Total: {total} rupees")
```

**Output:**
```
Item: Pencil
Quantity: 12
Price per item: 5 rupees
Total: 60 rupees
```

---

### Solution 12: Story Builder

```python
name = input("Enter your name: ")
friend = input("Enter your friend's name: ")
place = input("Enter a place: ")
food = input("Enter a food: ")

print()
print(f"One day, {name} and {friend} went on an adventure to {place}.")
print(f"They were very hungry, so they ordered {food}.")
print("It was the best day ever!")
```

**Example Interaction:**
```
Enter your name: Sachin
Enter your friend's name: Rahul
Enter a place: the moon
Enter a food: pizza

One day, Sachin and Rahul went on an adventure to the moon.
They were very hungry, so they ordered pizza.
It was the best day ever!
```

---

## What's Next?

Fantastic work! You now know how to store information in variables, get input from the user, and format beautiful output using f-strings. In the next lesson, we will learn about **Numbers and Math** -- how to make Python do calculations like a super-powered calculator!

Keep coding and keep having fun!

---
