# Lesson 03: Numbers and Math - Python as Your Super Calculator

---

## Numbers in Python: int and float

You already met these two number types in Lesson 02. Let's dive deeper!

### Integers (`int`) -- Whole Numbers

Integers are numbers **without** a decimal point. They can be positive, negative, or zero.

```python
apples = 10
temperature = -3
score = 0
population = 1400000000

print(apples)
print(temperature)
print(score)
print(population)
```

**Output:**
```
10
-3
0
1400000000
```

Python can handle incredibly large integers -- there is no limit!

```python
huge_number = 999999999999999999999999999999
print(huge_number)
```

**Output:**
```
999999999999999999999999999999
```

### Floats (`float`) -- Decimal Numbers

Floats are numbers **with** a decimal point.

```python
height = 4.5
price = 99.99
pi = 3.14159
tiny = 0.001

print(height)
print(price)
print(pi)
print(tiny)
```

**Output:**
```
4.5
99.99
3.14159
0.001
```

### int vs float -- What Is the Difference?

```python
a = 10      # This is an int
b = 10.0    # This is a float

print(type(a))
print(type(b))
```

**Output:**
```
<class 'int'>
<class 'float'>
```

Even though `10` and `10.0` look almost the same, Python treats them as different types. The moment you add a decimal point, it becomes a float!

---

## Arithmetic Operators

Python can do all the math you learn in school (and more!). Here are the **arithmetic operators**:

| Operator | Name                 | Example     | Result   |
|----------|----------------------|-------------|----------|
| `+`      | Addition             | `5 + 3`     | `8`      |
| `-`      | Subtraction          | `10 - 4`    | `6`      |
| `*`      | Multiplication       | `6 * 7`     | `42`     |
| `/`      | Division             | `15 / 4`    | `3.75`   |
| `//`     | Floor Division       | `15 // 4`   | `3`      |
| `%`      | Modulus (Remainder)  | `15 % 4`    | `3`      |
| `**`     | Exponent (Power)     | `2 ** 3`    | `8`      |

Let's explore each one in detail!

---

### Addition (`+`)

Addition works exactly like you would expect. Think of it as combining things together.

```python
print(5 + 3)
print(10 + 20)
print(100 + 200 + 300)
```

**Output:**
```
8
30
600
```

**Real-world example:** You have 12 red marbles and 8 blue marbles. How many total?

```python
red_marbles = 12
blue_marbles = 8
total = red_marbles + blue_marbles

print(f"Total marbles: {total}")
```

**Output:**
```
Total marbles: 20
```

---

### Subtraction (`-`)

Subtraction finds the difference between numbers.

```python
print(10 - 3)
print(100 - 45)
print(5 - 8)     # Negative results work too!
```

**Output:**
```
7
55
-3
```

**Real-world example:** You had 50 rupees. You bought a pen for 15 rupees. How much is left?

```python
money = 50
pen_cost = 15
remaining = money - pen_cost

print(f"Money remaining: {remaining} rupees")
```

**Output:**
```
Money remaining: 35 rupees
```

---

### Multiplication (`*`)

Multiplication is repeated addition. In Python, we use the `*` symbol (not `x`).

```python
print(6 * 7)
print(3 * 10)
print(12 * 12)
```

**Output:**
```
42
30
144
```

**Real-world example:** There are 5 rows of chairs with 8 chairs in each row. How many chairs total?

```python
rows = 5
chairs_per_row = 8
total_chairs = rows * chairs_per_row

print(f"Total chairs: {total_chairs}")
```

**Output:**
```
Total chairs: 40
```

---

### Division (`/`)

Division splits a number into equal parts. The result is **always a float** (decimal number), even if it divides evenly!

```python
print(15 / 3)
print(10 / 4)
print(7 / 2)
```

**Output:**
```
5.0
2.5
3.5
```

Notice that `15 / 3` gives `5.0` (a float), not `5` (an integer).

**Real-world example:** You have 20 chocolates to share equally among 4 friends. How many does each get?

```python
chocolates = 20
friends = 4
each_gets = chocolates / friends

print(f"Each friend gets: {each_gets} chocolates")
```

**Output:**
```
Each friend gets: 5.0 chocolates
```

---

### Floor Division (`//`) -- Division Without the Decimal

Floor division divides and then **rounds down** to the nearest whole number. It throws away the decimal part.

```python
print(15 // 4)    # 15 / 4 = 3.75, rounded down = 3
print(10 // 3)    # 10 / 3 = 3.33, rounded down = 3
print(7 // 2)     # 7 / 2 = 3.5, rounded down = 3
print(20 // 5)    # 20 / 5 = 4.0, rounded down = 4
```

**Output:**
```
3
3
3
4
```

**Real-world example:** You have 25 students and each bus can hold 7 students. How many **full** buses can you fill?

```python
students = 25
bus_capacity = 7
full_buses = students // bus_capacity

print(f"Full buses: {full_buses}")
```

**Output:**
```
Full buses: 3
```

(3 full buses hold 21 students, and 4 students are left over.)

---

### Modulus (`%`) -- The Remainder

The modulus operator gives you the **remainder** after division. It answers: "What is left over?"

```python
print(15 % 4)     # 15 / 4 = 3 remainder 3
print(10 % 3)     # 10 / 3 = 3 remainder 1
print(20 % 5)     # 20 / 5 = 4 remainder 0 (divides evenly!)
print(7 % 2)      # 7 / 2 = 3 remainder 1
```

**Output:**
```
3
1
0
1
```

**Real-world example:** Continuing the bus example -- how many students are left over?

```python
students = 25
bus_capacity = 7
leftover = students % bus_capacity

print(f"Students waiting for the next bus: {leftover}")
```

**Output:**
```
Students waiting for the next bus: 4
```

**Cool trick:** You can use `%` to check if a number is even or odd!

```python
number = 7

if number % 2 == 0:
    print(f"{number} is even")
else:
    print(f"{number} is odd")
```

**Output:**
```
7 is odd
```

(We will learn about `if` and `else` in a future lesson, but this shows why `%` is so useful!)

---

### Exponent (`**`) -- Powers

The `**` operator raises a number to a power. `2 ** 3` means "2 to the power of 3" or 2 x 2 x 2.

```python
print(2 ** 3)      # 2 x 2 x 2 = 8
print(5 ** 2)      # 5 x 5 = 25
print(10 ** 4)     # 10 x 10 x 10 x 10 = 10000
print(3 ** 3)      # 3 x 3 x 3 = 27
```

**Output:**
```
8
25
10000
27
```

**Real-world example:** What is the area of a square with side length 6?

```python
side = 6
area = side ** 2    # side x side

print(f"Area of the square: {area} square units")
```

**Output:**
```
Area of the square: 36 square units
```

You can also use `**` for square roots! The square root of a number is the same as raising it to the power of 0.5:

```python
print(25 ** 0.5)    # Square root of 25
print(144 ** 0.5)   # Square root of 144
```

**Output:**
```
5.0
12.0
```

---

## Order of Operations (PEMDAS / BODMAS)

When you have a math expression with multiple operators, Python follows the same rules you learn in school!

**PEMDAS** (or **BODMAS** if you use that term):

| Letter | Stands For        | Python Symbol |
|--------|-------------------|---------------|
| P / B  | Parentheses / Brackets | `()`     |
| E / O  | Exponents / Orders     | `**`     |
| M      | Multiplication         | `*`      |
| D      | Division               | `/`, `//`, `%` |
| A      | Addition               | `+`      |
| S      | Subtraction            | `-`      |

**Multiplication and division happen before addition and subtraction!**

```python
# What does Python calculate here?
print(2 + 3 * 4)
```

**Output:**
```
14
```

**Why?** Python does multiplication first: `3 * 4 = 12`, then addition: `2 + 12 = 14`.

It does NOT do `2 + 3 = 5` first. Multiplication comes before addition!

More examples:

```python
print(10 - 2 * 3)       # 2*3=6, then 10-6=4
print(10 + 6 / 2)       # 6/2=3, then 10+3=13
print(2 ** 3 + 1)        # 2**3=8, then 8+1=9
print(2 ** 3 * 2)        # 2**3=8, then 8*2=16
```

**Output:**
```
4
13.0
9
16
```

---

## Using Parentheses

Parentheses `()` let you **control** the order of operations. Whatever is inside parentheses gets calculated **first**.

```python
# Without parentheses
print(2 + 3 * 4)        # 3*4 first, then +2 = 14

# With parentheses
print((2 + 3) * 4)      # 2+3 first = 5, then *4 = 20
```

**Output:**
```
14
20
```

Big difference! Parentheses change the answer completely.

More examples:

```python
print((10 + 5) * 2)     # 15 * 2 = 30
print(10 + 5 * 2)       # 10 + 10 = 20

print((6 + 4) / (2 + 3))  # 10 / 5 = 2.0
print(100 / (5 * 4))      # 100 / 20 = 5.0
```

**Output:**
```
30
20
2.0
5.0
```

> **Tip:** When in doubt, use parentheses! They make your code easier to read and ensure the math works the way you want.

---

## Math with Variables

You can use variables in math expressions just like regular numbers:

```python
price = 120
quantity = 3
total = price * quantity

print(f"Total cost: {total} rupees")
```

**Output:**
```
Total cost: 360 rupees
```

### Updating a Variable with Math

You can use a variable's current value to calculate its new value:

```python
score = 100
print(f"Starting score: {score}")

score = score + 10    # Add 10 points
print(f"After bonus: {score}")

score = score - 5     # Lose 5 points
print(f"After penalty: {score}")
```

**Output:**
```
Starting score: 100
After bonus: 110
After penalty: 105
```

### Shortcut Operators

Python has shorter ways to update variables:

| Long Way              | Shortcut      | Meaning              |
|-----------------------|---------------|----------------------|
| `score = score + 10`  | `score += 10` | Add 10 to score      |
| `score = score - 5`   | `score -= 5`  | Subtract 5 from score|
| `price = price * 2`   | `price *= 2`  | Multiply price by 2  |
| `total = total / 4`   | `total /= 4`  | Divide total by 4    |

```python
score = 100
score += 10     # Same as: score = score + 10
print(score)

score -= 5      # Same as: score = score - 5
print(score)

score *= 2      # Same as: score = score * 2
print(score)
```

**Output:**
```
110
105
210
```

---

## Built-in Math Functions

Python comes with some handy math functions you can use right away!

### `abs()` -- Absolute Value

The absolute value is the "distance from zero" -- it makes negative numbers positive.

```python
print(abs(5))       # Already positive, stays 5
print(abs(-5))      # Negative becomes positive: 5
print(abs(-3.7))    # Works with floats too: 3.7
print(abs(0))       # Zero stays zero
```

**Output:**
```
5
5
3.7
0
```

**Real-world example:** Finding the difference between two temperatures, no matter which is higher:

```python
temp_monday = 32
temp_tuesday = 27
difference = abs(temp_monday - temp_tuesday)

print(f"Temperature difference: {difference} degrees")
```

**Output:**
```
Temperature difference: 5 degrees
```

---

### `round()` -- Round a Number

The `round()` function rounds a number to a specified number of decimal places.

```python
print(round(3.7))        # Rounds to nearest whole number: 4
print(round(3.2))        # Rounds down: 3
print(round(3.5))        # Rounds to nearest even: 4
print(round(2.5))        # Rounds to nearest even: 2
```

**Output:**
```
4
3
4
2
```

You can also specify how many decimal places:

```python
print(round(3.14159, 2))   # Round to 2 decimal places: 3.14
print(round(3.14159, 3))   # Round to 3 decimal places: 3.142
print(round(3.14159, 1))   # Round to 1 decimal place: 3.1
```

**Output:**
```
3.14
3.142
3.1
```

**Real-world example:** Calculating a price and rounding to 2 decimal places:

```python
total = 100 / 3
print(f"Exact: {total}")
print(f"Rounded: {round(total, 2)}")
```

**Output:**
```
Exact: 33.333333333333336
Rounded: 33.33
```

---

### `min()` and `max()` -- Find the Smallest and Largest

```python
print(min(5, 3, 8, 1, 9))     # Finds the smallest: 1
print(max(5, 3, 8, 1, 9))     # Finds the largest: 9
```

**Output:**
```
1
9
```

You can compare as many numbers as you want:

```python
print(min(100, 200, 50, 75))
print(max(100, 200, 50, 75))
```

**Output:**
```
50
200
```

**Real-world example:** Finding the highest and lowest scores:

```python
score1 = 85
score2 = 92
score3 = 78
score4 = 95

highest = max(score1, score2, score3, score4)
lowest = min(score1, score2, score3, score4)

print(f"Highest score: {highest}")
print(f"Lowest score: {lowest}")
```

**Output:**
```
Highest score: 95
Lowest score: 78
```

---

## Importing the `math` Module

Python has a special toolbox called the `math` module that contains extra math functions. To use it, you need to **import** it first:

```python
import math
```

Think of it like opening a toolbox -- once you open it, you can use all the tools inside.

### `math.sqrt()` -- Square Root

```python
import math

print(math.sqrt(25))     # Square root of 25 = 5.0
print(math.sqrt(144))    # Square root of 144 = 12.0
print(math.sqrt(2))      # Square root of 2 = 1.414...
```

**Output:**
```
5.0
12.0
1.4142135623730951
```

**Real-world example:** Finding the side length of a square given its area:

```python
import math

area = 64
side = math.sqrt(area)

print(f"A square with area {area} has a side length of {side}")
```

**Output:**
```
A square with area 64 has a side length of 8.0
```

### `math.pi` -- The Value of Pi

`math.pi` gives you the value of pi (approximately 3.14159265...). Note: `pi` is a value, not a function, so you do NOT use parentheses.

```python
import math

print(math.pi)
```

**Output:**
```
3.141592653589793
```

**Real-world example:** Finding the area and circumference of a circle:

```python
import math

radius = 5
area = math.pi * radius ** 2
circumference = 2 * math.pi * radius

print(f"Radius: {radius}")
print(f"Area: {round(area, 2)}")
print(f"Circumference: {round(circumference, 2)}")
```

**Output:**
```
Radius: 5
Area: 78.54
Circumference: 31.42
```

### Other Useful `math` Functions

```python
import math

print(math.ceil(3.2))     # Rounds UP to 4
print(math.floor(3.9))    # Rounds DOWN to 3
print(math.pow(2, 3))     # 2 to the power of 3 = 8.0 (same as 2**3)
print(math.factorial(5))  # 5! = 5*4*3*2*1 = 120
```

**Output:**
```
4
3
8.0
120
```

---

## Building a Simple Calculator Using `input()`

Let's put everything together and build a calculator that takes two numbers from the user and shows the results of all operations!

```python
# Simple Calculator
print("=== Simple Calculator ===")
print()

num1 = float(input("Enter the first number: "))
num2 = float(input("Enter the second number: "))

print()
print(f"--- Results ---")
print(f"{num1} + {num2} = {num1 + num2}")
print(f"{num1} - {num2} = {num1 - num2}")
print(f"{num1} * {num2} = {num1 * num2}")
print(f"{num1} / {num2} = {num1 / num2}")
print(f"{num1} // {num2} = {num1 // num2}")
print(f"{num1} % {num2} = {num1 % num2}")
print(f"{num1} ** {num2} = {num1 ** num2}")
```

**Example Interaction:**
```
=== Simple Calculator ===

Enter the first number: 15
Enter the second number: 4

--- Results ---
15.0 + 4.0 = 19.0
15.0 - 4.0 = 11.0
15.0 * 4.0 = 60.0
15.0 / 4.0 = 3.75
15.0 // 4.0 = 3.0
15.0 % 4.0 = 3.0
15.0 ** 4.0 = 50625.0
```

**How to run this in PyCharm:**
1. Create a new Python file (right-click project folder -> New -> Python File).
2. Name it `calculator`.
3. Type the code above.
4. Click the green Run button.
5. Click inside the Run window at the bottom of PyCharm.
6. Type the first number and press Enter.
7. Type the second number and press Enter.
8. See all the results appear!

---

## Summary

| Concept              | Example                      | Result        |
|----------------------|------------------------------|---------------|
| Addition             | `5 + 3`                      | `8`           |
| Subtraction          | `10 - 4`                     | `6`           |
| Multiplication       | `6 * 7`                      | `42`          |
| Division             | `15 / 4`                     | `3.75`        |
| Floor Division       | `15 // 4`                    | `3`           |
| Modulus (Remainder)  | `15 % 4`                     | `3`           |
| Exponent             | `2 ** 3`                     | `8`           |
| Absolute Value       | `abs(-5)`                    | `5`           |
| Round                | `round(3.14159, 2)`          | `3.14`        |
| Minimum              | `min(3, 7, 1)`               | `1`           |
| Maximum              | `max(3, 7, 1)`               | `7`           |
| Square Root          | `math.sqrt(25)`              | `5.0`         |
| Pi                   | `math.pi`                    | `3.14159...`  |

---

## Exercises

Create new Python files in PyCharm for these exercises. Run each one using the green Play button!

---

### Exercise 1: Area of a Rectangle

Ask the user for the length and width of a rectangle. Calculate and print the area.

**Formula:** `Area = length * width`

**Example Interaction:**
```
Enter the length: 8
Enter the width: 5
The area of the rectangle is 40.0 square units.
```

---

### Exercise 2: Area and Circumference of a Circle

Ask the user for the radius of a circle. Calculate and print the area and circumference.

**Formulas:**
- `Area = pi * radius * radius`
- `Circumference = 2 * pi * radius`

**Example Interaction:**
```
Enter the radius: 7
Area: 153.94
Circumference: 43.98
```

---

### Exercise 3: Temperature Converter (Celsius to Fahrenheit)

Ask the user for a temperature in Celsius and convert it to Fahrenheit.

**Formula:** `F = (C * 9/5) + 32`

**Example Interaction:**
```
Enter temperature in Celsius: 100
100.0 degrees Celsius = 212.0 degrees Fahrenheit
```

---

### Exercise 4: Temperature Converter (Fahrenheit to Celsius)

Now do it the other way! Ask for Fahrenheit and convert to Celsius.

**Formula:** `C = (F - 32) * 5/9`

**Example Interaction:**
```
Enter temperature in Fahrenheit: 98.6
98.6 degrees Fahrenheit = 37.0 degrees Celsius
```

---

### Exercise 5: Tip Calculator

Ask the user for the bill amount and the tip percentage. Calculate and print the tip amount and total amount.

**Example Interaction:**
```
Enter the bill amount: 500
Enter the tip percentage: 15
Tip amount: 75.0 rupees
Total amount: 575.0 rupees
```

---

### Exercise 6: Kilometers to Miles

Ask the user for a distance in kilometers and convert it to miles.

**Formula:** `miles = kilometers * 0.621371`

**Example Interaction:**
```
Enter distance in kilometers: 10
10.0 km = 6.21 miles
```

---

### Exercise 7: Average of Three Numbers

Ask the user for three test scores. Calculate and print the average.

**Example Interaction:**
```
Enter score 1: 85
Enter score 2: 92
Enter score 3: 78
The average score is 85.0
```

---

### Exercise 8: Time Converter

Ask the user for a number of minutes. Convert it to hours and minutes.

**Example Interaction:**
```
Enter the number of minutes: 150
150 minutes = 2 hours and 30 minutes
```

(Hint: Use `//` for hours and `%` for remaining minutes!)

---

### Exercise 9: Candy Sharing

Ask the user for the number of candies and the number of kids. Calculate how many candies each kid gets and how many are left over.

**Example Interaction:**
```
Enter the number of candies: 23
Enter the number of kids: 5
Each kid gets 4 candies.
Candies left over: 3
```

---

### Exercise 10: Simple Interest Calculator

Ask the user for the principal amount, interest rate (per year), and time (in years). Calculate the simple interest.

**Formula:** `Simple Interest = (Principal * Rate * Time) / 100`

**Example Interaction:**
```
Enter the principal amount: 1000
Enter the interest rate (per year): 5
Enter the time in years: 3
Simple Interest: 150.0
Total Amount: 1150.0
```

---

### Exercise 11: Hypotenuse Calculator

Ask the user for the two shorter sides of a right triangle. Calculate the hypotenuse.

**Formula:** `hypotenuse = sqrt(a^2 + b^2)`

**Example Interaction:**
```
Enter side a: 3
Enter side b: 4
The hypotenuse is 5.0
```

---

### Exercise 12: Body Mass Index (BMI) Calculator

Ask the user for their weight (in kg) and height (in meters). Calculate their BMI.

**Formula:** `BMI = weight / (height ** 2)`

**Example Interaction:**
```
Enter your weight in kg: 45
Enter your height in meters: 1.5
Your BMI is 20.0
```

---

## Solutions

---

### Solution 1: Area of a Rectangle

```python
length = float(input("Enter the length: "))
width = float(input("Enter the width: "))

area = length * width

print(f"The area of the rectangle is {area} square units.")
```

**Example Interaction:**
```
Enter the length: 8
Enter the width: 5
The area of the rectangle is 40.0 square units.
```

---

### Solution 2: Area and Circumference of a Circle

```python
import math

radius = float(input("Enter the radius: "))

area = math.pi * radius ** 2
circumference = 2 * math.pi * radius

print(f"Area: {round(area, 2)}")
print(f"Circumference: {round(circumference, 2)}")
```

**Example Interaction:**
```
Enter the radius: 7
Area: 153.94
Circumference: 43.98
```

---

### Solution 3: Temperature Converter (Celsius to Fahrenheit)

```python
celsius = float(input("Enter temperature in Celsius: "))
fahrenheit = (celsius * 9/5) + 32

print(f"{celsius} degrees Celsius = {fahrenheit} degrees Fahrenheit")
```

**Example Interaction:**
```
Enter temperature in Celsius: 100
100.0 degrees Celsius = 212.0 degrees Fahrenheit
```

---

### Solution 4: Temperature Converter (Fahrenheit to Celsius)

```python
fahrenheit = float(input("Enter temperature in Fahrenheit: "))
celsius = (fahrenheit - 32) * 5/9

print(f"{fahrenheit} degrees Fahrenheit = {round(celsius, 1)} degrees Celsius")
```

**Example Interaction:**
```
Enter temperature in Fahrenheit: 98.6
98.6 degrees Fahrenheit = 37.0 degrees Celsius
```

---

### Solution 5: Tip Calculator

```python
bill = float(input("Enter the bill amount: "))
tip_percent = float(input("Enter the tip percentage: "))

tip_amount = bill * tip_percent / 100
total = bill + tip_amount

print(f"Tip amount: {tip_amount} rupees")
print(f"Total amount: {total} rupees")
```

**Example Interaction:**
```
Enter the bill amount: 500
Enter the tip percentage: 15
Tip amount: 75.0 rupees
Total amount: 575.0 rupees
```

---

### Solution 6: Kilometers to Miles

```python
km = float(input("Enter distance in kilometers: "))
miles = km * 0.621371

print(f"{km} km = {round(miles, 2)} miles")
```

**Example Interaction:**
```
Enter distance in kilometers: 10
10.0 km = 6.21 miles
```

---

### Solution 7: Average of Three Numbers

```python
score1 = float(input("Enter score 1: "))
score2 = float(input("Enter score 2: "))
score3 = float(input("Enter score 3: "))

average = (score1 + score2 + score3) / 3

print(f"The average score is {round(average, 1)}")
```

**Example Interaction:**
```
Enter score 1: 85
Enter score 2: 92
Enter score 3: 78
The average score is 85.0
```

---

### Solution 8: Time Converter

```python
total_minutes = int(input("Enter the number of minutes: "))

hours = total_minutes // 60
minutes = total_minutes % 60

print(f"{total_minutes} minutes = {hours} hours and {minutes} minutes")
```

**Example Interaction:**
```
Enter the number of minutes: 150
150 minutes = 2 hours and 30 minutes
```

---

### Solution 9: Candy Sharing

```python
candies = int(input("Enter the number of candies: "))
kids = int(input("Enter the number of kids: "))

each_gets = candies // kids
leftover = candies % kids

print(f"Each kid gets {each_gets} candies.")
print(f"Candies left over: {leftover}")
```

**Example Interaction:**
```
Enter the number of candies: 23
Enter the number of kids: 5
Each kid gets 4 candies.
Candies left over: 3
```

---

### Solution 10: Simple Interest Calculator

```python
principal = float(input("Enter the principal amount: "))
rate = float(input("Enter the interest rate (per year): "))
time = float(input("Enter the time in years: "))

interest = (principal * rate * time) / 100
total = principal + interest

print(f"Simple Interest: {interest}")
print(f"Total Amount: {total}")
```

**Example Interaction:**
```
Enter the principal amount: 1000
Enter the interest rate (per year): 5
Enter the time in years: 3
Simple Interest: 150.0
Total Amount: 1150.0
```

---

### Solution 11: Hypotenuse Calculator

```python
import math

a = float(input("Enter side a: "))
b = float(input("Enter side b: "))

hypotenuse = math.sqrt(a ** 2 + b ** 2)

print(f"The hypotenuse is {hypotenuse}")
```

**Example Interaction:**
```
Enter side a: 3
Enter side b: 4
The hypotenuse is 5.0
```

---

### Solution 12: Body Mass Index (BMI) Calculator

```python
weight = float(input("Enter your weight in kg: "))
height = float(input("Enter your height in meters: "))

bmi = weight / (height ** 2)

print(f"Your BMI is {round(bmi, 1)}")
```

**Example Interaction:**
```
Enter your weight in kg: 45
Enter your height in meters: 1.5
Your BMI is 20.0
```

---

## What's Next?

You are doing an incredible job! You now know how to use Python as a powerful calculator. You can add, subtract, multiply, divide, find remainders, calculate powers, and even use advanced math functions.

In the next lesson, we will learn about **conditional statements** (`if`, `elif`, `else`) -- how to make your programs make decisions! Imagine a program that can decide whether you passed or failed a test, or whether it is hot or cold outside. Exciting stuff ahead!

Keep practicing, and remember: the more you code, the better you get!

---
