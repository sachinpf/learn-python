# Lesson 05: Conditions - Teaching Your Code to Make Decisions!

Imagine you're at a fork in the road. You look at a sign: "If it's raining, go left to the shelter. Otherwise, go right to the park." That's exactly what **conditions** (अट — खरे/खोटे ठरवणारे विधान) do in programming -- they let your code **choose** which path to follow!

---

## Making Decisions in Code

Every day, you make hundreds of decisions:
- **If** I'm hungry, I'll eat a snack.
- **If** it's cold outside, I'll wear a jacket. **Otherwise**, I'll wear a t-shirt.
- **If** I got an A, celebrate! **Else if** I got a B, still good! **Else**, study harder.

Python can make these same kinds of decisions! The magic words are `if` (जर — अट खरी असेल तर कोड चालवणे), `elif` (किंवा जर — आधीच्या अटी खोट्या असतील तर पुढची अट तपासणे), and `else` (नाहीतर — अट खोटी असेल तर वेगळा कोड चालवणे).

---

## Comparison Operators

Before we can make decisions, we need to **compare** things. Python gives us these comparison tools:

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |
| `>` | Greater than | `7 > 3` | `True` |
| `<` | Less than | `3 < 7` | `True` |
| `>=` | Greater than or equal to | `5 >= 5` | `True` |
| `<=` | Less than or equal to | `4 <= 5` | `True` |

> **Watch out!** A single `=` means "assign a value" (like `x = 5`). A double `==` means "is this equal to?" (like `x == 5`). Don't mix them up!

```python
print(10 == 10)    # Is 10 equal to 10?
print(10 != 5)     # Is 10 NOT equal to 5?
print(7 > 3)       # Is 7 greater than 3?
print(2 < 1)       # Is 2 less than 1?
print(5 >= 5)      # Is 5 greater than or equal to 5?
print(3 <= 2)      # Is 3 less than or equal to 2?
```
**Expected Output:**
```
True
True
True
False
True
False
```

You can also compare strings:
```python
print("apple" == "apple")     # True
print("apple" == "Apple")     # False (capitalization matters!)
print("banana" != "cherry")   # True
print("a" < "b")              # True (alphabetical order)
```
**Expected Output:**
```
True
False
True
True
```

---

## Boolean Values: True and False

When Python compares things, the answer is always one of two special values:
- `True` -- Yes! It's correct!
- `False` -- No! It's wrong!

These are called **Boolean values** (बूलियन — True किंवा False, फक्त दोन मूल्यांचा प्रकार) (named after mathematician George Boole).

```python
is_sunny = True
is_raining = False

print(is_sunny)
print(is_raining)
print(type(is_sunny))
```
**Expected Output:**
```
True
False
<class 'bool'>
```

You can store comparison results in variables:
```python
age = 15
can_drive = age >= 16

print(can_drive)   # False, because 15 is not >= 16
```
**Expected Output:**
```
False
```

---

## The `if` Statement

The `if` statement is the simplest decision-maker. It says: "If this condition is True, do this thing."

### How it works (like a flowchart):

```
     [Is the condition True?]
            /        \
          YES         NO
          /             \
   [Do this]      [Skip it]
```

### Syntax:
```python
if condition:
    # Do this (indented with 4 spaces!)
```

> **Super Important:** The code inside an `if` block must be **indented** (moved to the right with 4 spaces or 1 tab). This is how Python knows what belongs inside the `if`.

> **Why does indentation matter in Python?**
> Other programming languages (like Java or C++) use curly braces `{ }` to mark which lines belong inside an `if`:
> ```
> if (raining) {
>     stay_inside();   ← this line is "inside" because of { }
> }
> get_lunch();          ← this is "outside"
> ```
> Python's designers thought: "Programmers already indent their code to make it readable. Why not use that indentation as the *actual rule*?" So in Python, **the spaces in front of a line are not just for looks — they tell Python which lines belong together.** That's why getting indentation wrong is one of the most common beginner mistakes. Be careful! Use 4 spaces for each level.

```python
age = 10

if age >= 5:
    print("You can go to school!")
```
**Expected Output:**
```
You can go to school!
```

```python
temperature = 35

if temperature > 30:
    print("It's hot outside!")
    print("Don't forget to drink water!")
```
**Expected Output:**
```
It's hot outside!
Don't forget to drink water!
```

```python
score = 50

if score < 60:
    print("You need to study more.")

print("This line always runs, no matter what!")
```
**Expected Output:**
```
You need to study more.
This line always runs, no matter what!
```

Notice that the last `print` is **not indented** -- it's outside the `if` block, so it runs regardless.

---

## The `if-else` Statement

What if you want to do **one thing** when the condition is True and a **different thing** when it's False? Use `if-else`!

### Flowchart:
```
     [Is the condition True?]
            /        \
          YES         NO
          /             \
   [Do this]      [Do that instead]
```

```python
age = 12

if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```
**Expected Output:**
```
You are a minor.
```

```python
number = 7

if number % 2 == 0:
    print(f"{number} is even.")
else:
    print(f"{number} is odd.")
```
**Expected Output:**
```
7 is odd.
```

```python
password = "python123"
user_input = "python123"

if user_input == password:
    print("Access granted! Welcome!")
else:
    print("Wrong password. Try again.")
```
**Expected Output:**
```
Access granted! Welcome!
```

---

## The `if-elif-else` Statement

Sometimes you have **more than two** choices. That's where `elif` (short for "else if") comes in! You can have as many `elif` blocks as you need.

### Flowchart:
```
     [Condition 1 True?]
          /       \
        YES        NO
        /            \
  [Do this]    [Condition 2 True?]
                   /       \
                 YES        NO
                 /            \
           [Do this]    [Condition 3 True?]
                            /       \
                          YES        NO
                          /            \
                    [Do this]    [Do the else thing]
```

```python
score = 85

if score >= 90:
    print("Grade: A - Excellent!")
elif score >= 80:
    print("Grade: B - Great job!")
elif score >= 70:
    print("Grade: C - Good work!")
elif score >= 60:
    print("Grade: D - You passed!")
else:
    print("Grade: F - Study harder next time.")
```
**Expected Output:**
```
Grade: B - Great job!
```

> **Important:** Python checks conditions from **top to bottom** and stops at the **first** one that's True. Even if multiple conditions are true, only the first matching block runs.

```python
temperature = 25

if temperature >= 40:
    print("Extremely hot! Stay indoors!")
elif temperature >= 30:
    print("It's hot. Drink lots of water.")
elif temperature >= 20:
    print("Nice weather! Enjoy the day!")
elif temperature >= 10:
    print("A bit cool. Bring a jacket.")
else:
    print("It's cold! Bundle up!")
```
**Expected Output:**
```
Nice weather! Enjoy the day!
```

```python
day = "Saturday"

if day == "Monday":
    print("Ugh, start of the week.")
elif day == "Friday":
    print("TGIF! Almost weekend!")
elif day == "Saturday" or day == "Sunday":
    print("Weekend! Time to relax!")
else:
    print("Just another weekday.")
```
**Expected Output:**
```
Weekend! Time to relax!
```

---

## Which Shape Do I Use? `if` vs `elif` vs Many `if`s vs Nested `if`

This is one of the most confusing parts for beginners, so let's slow down. You have **four shapes** to choose from. Picking the right one matters!

### The four shapes side-by-side

| Shape | What it looks like | When to use it |
|---|---|---|
| **One `if` alone** | `if x:` (no else) | You want to do something **only** when the condition is true. Otherwise do nothing. |
| **`if` + `else`** | Two branches | The choice is **either/or**. Exactly one branch will run. |
| **`if` + `elif` + `else`** | A chain | You have **3 or more mutually exclusive** cases — only ONE should run. (e.g., grade A, B, C, D, F) |
| **Many separate `if`s** | Several `if` blocks, not chained | You want to check **multiple independent** things, where more than one could be true at the same time. |
| **Nested `if`** | `if` inside `if` | The **second question only makes sense if the first is true.** (e.g., "If you have money — and only then — ask how much.") |

### The trap: `elif` vs. separate `if`s

This is the #1 mistake beginners make. They look identical on the screen but behave very differently!

```python
# Version A: a CHAIN with elif (only ONE branch runs)
score = 95
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
```
**Expected Output:**
```
A
```

```python
# Version B: SEPARATE ifs (multiple branches can run!)
score = 95
if score >= 90:
    print("A")
if score >= 80:
    print("B")
if score >= 70:
    print("C")
```
**Expected Output:**
```
A
B
C
```

In Version A, Python checks `score >= 90`, finds it `True`, prints `"A"`, then **skips the rest of the chain**. In Version B, every `if` is checked independently, so all three are true and all three print!

> **Rule of thumb:** If only **one** answer should win, use `elif`. If you genuinely want to **check several unrelated things**, use separate `if`s.

### When to use `else` vs leave it off

You only need `else` when there is something to do for the "otherwise" case. If there's nothing to do otherwise, just leave `else` off — it's optional.

```python
# else is needed: we want different messages
if grade >= 60:
    print("You passed!")
else:
    print("You failed.")

# else is NOT needed: we only care about one case
if grade == 100:
    print("Perfect score!")
# (no else — if it's not 100, we don't print anything)
```

### When to nest vs use `and`

If the second check **only makes sense** when the first is true, nesting reads more clearly. Otherwise, combining with `and` is usually shorter.

```python
# Nesting reads naturally: "do you have money? if yes, how much?"
if has_money:
    if amount >= 100:
        print("Big meal!")

# But this same idea can be flattened with `and`:
if has_money and amount >= 100:
    print("Big meal!")
```

Both work. Nesting is clearer when there are different "else" branches at each level (as in the bigger example below).

---

## Nested `if` Statements

You can put an `if` inside another `if` -- like a decision inside a decision! This is called **nesting**.

Think of it like this: "If you have money, then check -- do you have enough for pizza or just enough for a snack?"

```python
has_money = True
amount = 50

if has_money:
    if amount >= 100:
        print("You can buy a big meal!")
    elif amount >= 30:
        print("You can buy a pizza!")
    else:
        print("You can buy a snack.")
else:
    print("Sorry, you need money to buy food.")
```
**Expected Output:**
```
You can buy a pizza!
```

```python
age = 15
has_id = True

if age >= 13:
    print("Age requirement met!")
    if has_id:
        print("ID verified. You may enter!")
    else:
        print("Please bring your ID next time.")
else:
    print("Sorry, you must be at least 13.")
```
**Expected Output:**
```
Age requirement met!
ID verified. You may enter!
```

> **Tip:** Try not to nest too deeply (more than 2-3 levels). Deeply nested code can be hard to read. Sometimes you can use logical operators instead!

---

## Logical Operators: `and`, `or`, `not`

Logical operators let you **combine** multiple conditions together.

### `and` -- Both Must Be True

The `and` (आणि — दोन्ही अटी खऱ्या असणे आवश्यक) operator is like needing BOTH a ticket AND an ID to enter a concert.

```python
age = 15
has_ticket = True

if age >= 12 and has_ticket:
    print("Welcome to the concert!")
else:
    print("Sorry, you can't enter.")
```
**Expected Output:**
```
Welcome to the concert!
```

| Condition A | Condition B | A `and` B |
|------------|------------|-----------|
| True | True | **True** |
| True | False | False |
| False | True | False |
| False | False | False |

### `or` -- At Least One Must Be True

The `or` (किंवा — कोणतीही एक अट खरी असली तरी पुरे) operator is like a restaurant that accepts cash OR card -- either one works!

```python
has_cash = False
has_card = True

if has_cash or has_card:
    print("You can pay for the meal!")
else:
    print("Sorry, no payment method available.")
```
**Expected Output:**
```
You can pay for the meal!
```

| Condition A | Condition B | A `or` B |
|------------|------------|----------|
| True | True | **True** |
| True | False | **True** |
| False | True | **True** |
| False | False | False |

### `not` -- Flip the Value

The `not` (नाही — अटीला उलट करणारा, True चे False करणे) operator is like saying "If it's NOT raining..." It turns True into False and False into True.

```python
is_raining = False

if not is_raining:
    print("Let's go to the park!")
else:
    print("Better stay inside.")
```
**Expected Output:**
```
Let's go to the park!
```

| Condition | `not` Condition |
|-----------|----------------|
| True | False |
| False | **True** |

---

## Combining Conditions

You can mix `and`, `or`, and `not` to create powerful conditions:

```python
age = 16
has_license = True
is_grounded = False

if age >= 16 and has_license and not is_grounded:
    print("You can drive the car!")
else:
    print("You can't drive right now.")
```
**Expected Output:**
```
You can drive the car!
```

```python
# Use parentheses to make complex conditions clear
day = "Saturday"
weather = "sunny"

if (day == "Saturday" or day == "Sunday") and weather == "sunny":
    print("Perfect day for the beach!")
```
**Expected Output:**
```
Perfect day for the beach!
```

---

## Real-World Examples

### Example 1: Age Checker

```python
age = 14

if age < 0:
    print("Invalid age!")
elif age < 3:
    print("You're a baby!")
elif age < 13:
    print("You're a kid!")
elif age < 18:
    print("You're a teenager!")
elif age < 65:
    print("You're an adult!")
else:
    print("You're a senior citizen!")
```
**Expected Output:**
```
You're a teenager!
```

### Example 2: Grade Calculator

```python
marks = 78
total = 100
percentage = (marks / total) * 100

print(f"Your percentage: {percentage}%")

if percentage >= 90:
    grade = "A+"
elif percentage >= 80:
    grade = "A"
elif percentage >= 70:
    grade = "B"
elif percentage >= 60:
    grade = "C"
elif percentage >= 50:
    grade = "D"
else:
    grade = "F"

print(f"Your grade: {grade}")

if percentage >= 50:
    print("Congratulations! You passed!")
else:
    print("Sorry, you did not pass. Keep studying!")
```
**Expected Output:**
```
Your percentage: 78.0%
Your grade: B
Congratulations! You passed!
```

### Example 3: Traffic Light Simulator

```python
light = "red"

if light == "red":
    print("STOP! Wait for the light to change.")
elif light == "yellow":
    print("CAUTION! Slow down, the light is about to change.")
elif light == "green":
    print("GO! You may proceed safely.")
else:
    print("ERROR: Unknown traffic light color!")
```
**Expected Output:**
```
STOP! Wait for the light to change.
```

### Example 4: Simple Calculator

```python
num1 = 10
num2 = 3
operation = "+"

if operation == "+":
    result = num1 + num2
    print(f"{num1} + {num2} = {result}")
elif operation == "-":
    result = num1 - num2
    print(f"{num1} - {num2} = {result}")
elif operation == "*":
    result = num1 * num2
    print(f"{num1} * {num2} = {result}")
elif operation == "/":
    if num2 != 0:
        result = num1 / num2
        print(f"{num1} / {num2} = {result}")
    else:
        print("Error: Cannot divide by zero!")
else:
    print("Unknown operation!")
```
**Expected Output:**
```
10 + 3 = 13
```

---

## Exercises

Try these on your own, then check the solutions!

---

### Exercise 1: Odd or Even Checker
Write a program that checks if a number is odd or even.

```
Input: 7
Output: "7 is odd"
```

<details>
<summary>Click to see the solution</summary>

```python
number = 7

if number % 2 == 0:
    print(f"{number} is even")
else:
    print(f"{number} is odd")
```
**Expected Output:**
```
7 is odd
```
</details>

---

### Exercise 2: Leap Year Checker
A year is a leap year if:
- It's divisible by 4
- BUT NOT by 100
- UNLESS it's also divisible by 400

```
Input: 2024
Output: "2024 is a leap year!"
```

<details>
<summary>Click to see the solution</summary>

```python
year = 2024

if (year % 400 == 0) or (year % 4 == 0 and year % 100 != 0):
    print(f"{year} is a leap year!")
else:
    print(f"{year} is NOT a leap year.")
```
**Expected Output:**
```
2024 is a leap year!
```
</details>

---

### Exercise 3: Ticket Pricing
- Children (under 5): Free
- Kids (5-12): $10
- Teens (13-17): $15
- Adults (18-64): $25
- Seniors (65+): $15

```
Input: age = 10
Output: "Ticket price: $10"
```

<details>
<summary>Click to see the solution</summary>

```python
age = 10

if age < 5:
    price = 0
    print(f"Ticket price: Free!")
elif age <= 12:
    price = 10
    print(f"Ticket price: ${price}")
elif age <= 17:
    price = 15
    print(f"Ticket price: ${price}")
elif age <= 64:
    price = 25
    print(f"Ticket price: ${price}")
else:
    price = 15
    print(f"Ticket price: ${price}")
```
**Expected Output:**
```
Ticket price: $10
```
</details>

---

### Exercise 4: Quiz Game
Create a simple one-question quiz. Ask a question, check the answer, and give feedback.

<details>
<summary>Click to see the solution</summary>

```python
print("=== Python Quiz ===")
print("Question: What is the capital of France?")
print("A) London")
print("B) Paris")
print("C) Berlin")
print("D) Madrid")

answer = "B"

if answer.upper() == "B":
    print("Correct! Paris is the capital of France!")
else:
    print(f"Wrong! You answered {answer}. The correct answer is B) Paris.")
```
**Expected Output:**
```
=== Python Quiz ===
Question: What is the capital of France?
A) London
B) Paris
C) Berlin
D) Madrid
Correct! Paris is the capital of France!
```
</details>

---

### Exercise 5: Positive, Negative, or Zero
Check if a number is positive, negative, or zero.

```
Input: -5
Output: "-5 is negative"
```

<details>
<summary>Click to see the solution</summary>

```python
number = -5

if number > 0:
    print(f"{number} is positive")
elif number < 0:
    print(f"{number} is negative")
else:
    print(f"{number} is zero")
```
**Expected Output:**
```
-5 is negative
```
</details>

---

### Exercise 6: Largest of Three Numbers
Find the largest among three numbers.

```
Input: a=10, b=25, c=15
Output: "The largest number is 25"
```

<details>
<summary>Click to see the solution</summary>

```python
a = 10
b = 25
c = 15

if a >= b and a >= c:
    largest = a
elif b >= a and b >= c:
    largest = b
else:
    largest = c

print(f"The largest number is {largest}")
```
**Expected Output:**
```
The largest number is 25
```
</details>

---

### Exercise 7: BMI Calculator
Calculate BMI (weight in kg / height in meters squared) and give the category.
- Under 18.5: Underweight
- 18.5 to 24.9: Normal
- 25 to 29.9: Overweight
- 30 and above: Obese

<details>
<summary>Click to see the solution</summary>

```python
weight = 65   # kg
height = 1.75  # meters

bmi = weight / (height ** 2)
print(f"Your BMI is: {bmi:.1f}")

if bmi < 18.5:
    print("Category: Underweight")
elif bmi < 25:
    print("Category: Normal weight")
elif bmi < 30:
    print("Category: Overweight")
else:
    print("Category: Obese")
```
**Expected Output:**
```
Your BMI is: 21.2
Category: Normal weight
```
</details>

---

### Exercise 8: Season Finder
Given a month number (1-12), print which season it is.
- 12, 1, 2: Winter
- 3, 4, 5: Spring
- 6, 7, 8: Summer
- 9, 10, 11: Autumn/Fall

<details>
<summary>Click to see the solution</summary>

```python
month = 4

if month in [12, 1, 2]:
    season = "Winter"
elif month in [3, 4, 5]:
    season = "Spring"
elif month in [6, 7, 8]:
    season = "Summer"
elif month in [9, 10, 11]:
    season = "Autumn/Fall"
else:
    season = "Invalid month!"

print(f"Month {month} is in {season}")
```
**Expected Output:**
```
Month 4 is in Spring
```
</details>

---

### Exercise 9: Password Strength Checker
Check if a password is strong. A strong password should be:
- At least 8 characters long
- Contain at least one uppercase letter
- Contain at least one digit

<details>
<summary>Click to see the solution</summary>

```python
password = "Hello123"

has_length = len(password) >= 8
has_upper = False
has_digit = False

for char in password:
    if char.isupper():
        has_upper = True
    if char.isdigit():
        has_digit = True

if has_length and has_upper and has_digit:
    print("Strong password!")
else:
    print("Weak password. It needs:")
    if not has_length:
        print("  - At least 8 characters")
    if not has_upper:
        print("  - At least one uppercase letter")
    if not has_digit:
        print("  - At least one digit")
```
**Expected Output:**
```
Strong password!
```
</details>

---

### Exercise 10: Rock, Paper, Scissors
Simulate a round of Rock, Paper, Scissors between two players.

<details>
<summary>Click to see the solution</summary>

```python
player1 = "rock"
player2 = "scissors"

print(f"Player 1 chose: {player1}")
print(f"Player 2 chose: {player2}")

if player1 == player2:
    print("It's a tie!")
elif (player1 == "rock" and player2 == "scissors") or \
     (player1 == "scissors" and player2 == "paper") or \
     (player1 == "paper" and player2 == "rock"):
    print("Player 1 wins!")
else:
    print("Player 2 wins!")
```
**Expected Output:**
```
Player 1 chose: rock
Player 2 chose: scissors
Player 1 wins!
```
</details>

---

### Exercise 11: Triangle Type Checker
Given three sides, determine if a triangle is equilateral (all sides equal), isosceles (two sides equal), or scalene (no sides equal).

<details>
<summary>Click to see the solution</summary>

```python
a = 5
b = 5
c = 8

# First check if it's a valid triangle
if a + b > c and b + c > a and a + c > b:
    if a == b == c:
        print("Equilateral triangle (all sides equal)")
    elif a == b or b == c or a == c:
        print("Isosceles triangle (two sides equal)")
    else:
        print("Scalene triangle (no sides equal)")
else:
    print("These sides don't form a valid triangle!")
```
**Expected Output:**
```
Isosceles triangle (two sides equal)
```
</details>

---

### Exercise 12: Day of the Week Planner
Given a day number (1=Monday to 7=Sunday), print the day and whether it's a weekday or weekend, plus a fun activity suggestion.

<details>
<summary>Click to see the solution</summary>

```python
day_number = 6

days = {1: "Monday", 2: "Tuesday", 3: "Wednesday",
        4: "Thursday", 5: "Friday", 6: "Saturday", 7: "Sunday"}

if day_number in days:
    day_name = days[day_number]
    print(f"Day {day_number} is {day_name}")

    if day_number <= 5:
        print("It's a weekday.")
        if day_number == 1:
            print("Suggestion: Start the week strong with some coding!")
        elif day_number == 5:
            print("Suggestion: Almost weekend! Finish your homework!")
        else:
            print("Suggestion: Keep up the good work!")
    else:
        print("It's the weekend!")
        if day_number == 6:
            print("Suggestion: Go play outside or work on a fun project!")
        else:
            print("Suggestion: Relax and get ready for the new week!")
else:
    print("Invalid day number! Please enter 1-7.")
```
**Expected Output:**
```
Day 6 is Saturday
It's the weekend!
Suggestion: Go play outside or work on a fun project!
```
</details>

---

## What's Next?

Awesome work! You now know how to make your programs **think** and **decide**. In the next lesson, we'll learn about **Loops** -- how to make your programs repeat things without writing the same code over and over!

Keep making decisions and keep coding!
