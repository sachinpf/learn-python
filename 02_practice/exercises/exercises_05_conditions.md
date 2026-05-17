# Exercises — Lesson 05: Conditions

30 problems to make `if`, `elif`, and `else` feel automatic. Use only what you've learned in Lessons 1–5 (variables, input, math, strings, and conditions). **No loops, no lists, no functions** — those come later!

> **How to use this file:** read the problem, type your code, run it. Only click "Show solution" after you've genuinely tried. The struggle is where the learning happens.

Brief refresher *(संक्षिप्त उजळणी)*:
- `if condition:` runs the block only when the condition is `True`
- `elif other_condition:` is checked **only if** the previous `if`/`elif` was `False`
- `else:` runs when nothing above matched
- Use `and`, `or`, `not` to combine conditions

---

## 🟢 Easy

### Problem 1: Even or Odd (hardcoded)

Given `number = 10`, print `"Even"` if it is even, otherwise print `"Odd"`. (Hint: `%` gives the remainder.)

**Expected output:**
```
Even
```

<details>
<summary>💡 Show solution</summary>

```python
number = 10
if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```
**Teaching note:** `number % 2` is `0` for even numbers and `1` for odd. That's the trick to remember.
</details>

---

### Problem 2: Adult or Minor

Set `age = 14`. Print `"Adult"` if age is 18 or above, else print `"Minor"`.

**Expected output:**
```
Minor
```

<details>
<summary>💡 Show solution</summary>

```python
age = 14
if age >= 18:
    print("Adult")
else:
    print("Minor")
```
**Teaching note:** `>=` means "greater than OR equal to". `age = 18` would also print "Adult".
</details>

---

### Problem 3: Bigger Number

Given `a = 7` and `b = 12`, print which one is bigger. If they are equal, print `"Equal"`.

**Expected output:**
```
12 is bigger
```

<details>
<summary>💡 Show solution</summary>

```python
a = 7
b = 12

if a > b:
    print(f"{a} is bigger")
elif b > a:
    print(f"{b} is bigger")
else:
    print("Equal")
```
**Teaching note:** Three cases → use `if` + `elif` + `else`. Notice `elif b > a` is only checked when `a > b` was False.
</details>

---

### Problem 4: Predict True or False

Without running the code, write down what each `print` will output. Then run it to check.

```python
print(10 > 5)
print(10 == 5)
print(10 != 5)
print(10 >= 10)
print("apple" == "Apple")
print(not True)
print(True and False)
print(True or False)
```

<details>
<summary>💡 Show solution</summary>

```
True
False
True
True
False
False
False
True
```
**Teaching note:** `==` is strict — uppercase vs lowercase counts! `not True` flips True to False. `and` needs BOTH to be True; `or` needs AT LEAST ONE.
</details>

---

### Problem 5: Letter Grade

Set `score = 85`. Print the letter grade using this scale:
- 90+ → `"A"`
- 80–89 → `"B"`
- 70–79 → `"C"`
- 60–69 → `"D"`
- below 60 → `"F"`

**Expected output:**
```
B
```

<details>
<summary>💡 Show solution</summary>

```python
score = 85

if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
elif score >= 60:
    print("D")
else:
    print("F")
```
**Teaching note:** Order matters! Python checks top-to-bottom and stops at the first match. If you wrote `>= 60` first, *every* passing score would print "D".
</details>

---

### Problem 6: Sign of a Number

Set `n = -3`. Print `"Positive"`, `"Negative"`, or `"Zero"`.

**Expected output:**
```
Negative
```

<details>
<summary>💡 Show solution</summary>

```python
n = -3

if n > 0:
    print("Positive")
elif n < 0:
    print("Negative")
else:
    print("Zero")
```
**Teaching note:** Zero is neither positive nor negative — that's why we need three branches.
</details>

---

### Problem 7: Password Check

Set `correct = "python123"` and ask the user for a password using `input()`. Print `"Access granted"` if it matches, else `"Access denied"`.

**Sample interaction:**
```
Enter password: python123
Access granted
```

<details>
<summary>💡 Show solution</summary>

```python
correct = "python123"
guess = input("Enter password: ")

if guess == correct:
    print("Access granted")
else:
    print("Access denied")
```
**Teaching note:** `input()` always returns a string, so comparing it to another string works directly. No conversion needed.
</details>

---

### Problem 8: Empty String?

Ask the user for their name. If they typed nothing (just pressed Enter), print `"You didn't enter a name!"`. Otherwise print `"Hello, <name>!"`.

**Sample interaction:**
```
What is your name?
You didn't enter a name!
```

<details>
<summary>💡 Show solution</summary>

```python
name = input("What is your name? ")

if name == "":
    print("You didn't enter a name!")
else:
    print(f"Hello, {name}!")
```
**Teaching note:** An empty string `""` has length zero. You could also write `if len(name) == 0:` — same result.
</details>

---

### Problem 9: Day Message

Set `day = "Saturday"`. Print `"Weekend!"` if it's Saturday or Sunday, else print `"Weekday"`.

**Expected output:**
```
Weekend!
```

<details>
<summary>💡 Show solution</summary>

```python
day = "Saturday"

if day == "Saturday" or day == "Sunday":
    print("Weekend!")
else:
    print("Weekday")
```
**Teaching note:** Using `or` is cleaner than nested `if`s when two different values should give the same answer.
</details>

---

### Problem 10: Both Conditions

Set `has_ticket = True` and `has_id = True`. Print `"You may enter"` only if **both** are True. Otherwise print `"Sorry, you can't enter"`.

**Expected output:**
```
You may enter
```

<details>
<summary>💡 Show solution</summary>

```python
has_ticket = True
has_id = True

if has_ticket and has_id:
    print("You may enter")
else:
    print("Sorry, you can't enter")
```
**Teaching note:** When a variable already holds True/False, you don't need `== True`. Just use the variable directly in the condition. `if has_ticket and has_id:` is cleaner than `if has_ticket == True and has_id == True:`.
</details>

---

## 🟡 Medium

### Problem 11: Divisible by 3 AND 5

Set `n = 15`. Print `"FizzBuzz"` if `n` is divisible by both 3 and 5. Print `"Fizz"` if only by 3. Print `"Buzz"` if only by 5. Otherwise print the number.

**Expected output:**
```
FizzBuzz
```

<details>
<summary>💡 Show solution</summary>

```python
n = 15

if n % 3 == 0 and n % 5 == 0:
    print("FizzBuzz")
elif n % 3 == 0:
    print("Fizz")
elif n % 5 == 0:
    print("Buzz")
else:
    print(n)
```
**Teaching note:** The **most specific** condition (divisible by BOTH) must come first. If you checked `% 3 == 0` first, 15 would match "Fizz" and never reach "FizzBuzz".
</details>

---

### Problem 12: Leap Year (Simple Rule)

A year is a leap year (simple rule) if it is divisible by 4. Set `year = 2024` and print `"Leap year"` or `"Not a leap year"`.

**Expected output:**
```
Leap year
```

<details>
<summary>💡 Show solution</summary>

```python
year = 2024

if year % 4 == 0:
    print("Leap year")
else:
    print("Not a leap year")
```
**Teaching note:** The real leap-year rule has exceptions (divisible by 100 but not 400). Try implementing that as a bonus!
</details>

---

### Problem 13: Largest of Three

Given `a = 12`, `b = 7`, `c = 25`, print the largest number.

**Expected output:**
```
25 is the largest
```

<details>
<summary>💡 Show solution</summary>

```python
a, b, c = 12, 7, 25

if a >= b and a >= c:
    print(f"{a} is the largest")
elif b >= a and b >= c:
    print(f"{b} is the largest")
else:
    print(f"{c} is the largest")
```
**Teaching note:** For the largest, a number must be `>=` to *both* others. Using `>=` (not `>`) handles ties correctly.
</details>

---

### Problem 14: Even/Odd from User Input

Ask the user for a whole number. Print whether it's even or odd. Remember: `input()` returns a string!

**Sample interaction:**
```
Enter a number: 47
47 is odd
```

<details>
<summary>💡 Show solution</summary>

```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print(f"{number} is even")
else:
    print(f"{number} is odd")
```
**Teaching note:** `int(input(...))` converts the user's text into a number in one step. Without `int(...)`, `number % 2` would crash because you can't take the remainder of a string.
</details>

---

### Problem 15: Vowel or Consonant

Ask the user for a single letter. Print `"Vowel"` if it's a, e, i, o, or u (lowercase or uppercase). Otherwise print `"Consonant"`. If they entered something that's not a single letter, print `"Not a letter"`.

**Sample interaction:**
```
Enter a letter: E
Vowel
```

<details>
<summary>💡 Show solution</summary>

```python
letter = input("Enter a letter: ")

# .lower() converts to lowercase so we only check 5 vowels
lowered = letter.lower()

if len(letter) != 1 or not letter.isalpha():
    print("Not a letter")
elif lowered == "a" or lowered == "e" or lowered == "i" or lowered == "o" or lowered == "u":
    print("Vowel")
else:
    print("Consonant")
```
**Teaching note:** Instead of writing 10 conditions (5 lowercase + 5 uppercase), we lowercase the input first and check 5. `.isalpha()` returns True only if the string contains letters.
</details>

---

### Problem 16: Triangle Validity

Given three side lengths `a = 3`, `b = 4`, `c = 5`, print `"Valid triangle"` if **the sum of any two sides is greater than the third**. Otherwise print `"Not a triangle"`.

**Expected output:**
```
Valid triangle
```

<details>
<summary>💡 Show solution</summary>

```python
a, b, c = 3, 4, 5

if a + b > c and a + c > b and b + c > a:
    print("Valid triangle")
else:
    print("Not a triangle")
```
**Teaching note:** All three conditions must be true at once — that's what `and` is for. This is called the **triangle inequality** and it's a real math rule.
</details>

---

### Problem 17: Tiered Discount

A shop offers discounts based on how much you spend:
- ₹1000 or more → 20% off
- ₹500–999 → 10% off
- ₹100–499 → 5% off
- below ₹100 → no discount

Set `amount = 750`. Print the discount percentage.

**Expected output:**
```
10% off
```

<details>
<summary>💡 Show solution</summary>

```python
amount = 750

if amount >= 1000:
    print("20% off")
elif amount >= 500:
    print("10% off")
elif amount >= 100:
    print("5% off")
else:
    print("No discount")
```
**Teaching note:** Start with the highest threshold. Since Python stops at the first match, you don't need to write `amount >= 500 and amount < 1000` — the `elif` already implies "we didn't match the first one".
</details>

---

### Problem 18: BMI Category

BMI = weight (kg) ÷ (height (m))². Categories:
- below 18.5 → `"Underweight"`
- 18.5 to 24.9 → `"Normal"`
- 25 to 29.9 → `"Overweight"`
- 30 and above → `"Obese"`

Given `weight = 60.0` and `height = 1.65`, compute BMI and print the category.

**Expected output (BMI ≈ 22.04):**
```
BMI: 22.04
Normal
```

<details>
<summary>💡 Show solution</summary>

```python
weight = 60.0
height = 1.65

bmi = weight / (height ** 2)
print(f"BMI: {bmi:.2f}")     # :.2f means 2 decimal places

if bmi < 18.5:
    print("Underweight")
elif bmi < 25:
    print("Normal")
elif bmi < 30:
    print("Overweight")
else:
    print("Obese")
```
**Teaching note:** `height ** 2` is height squared. `{bmi:.2f}` is a formatting trick that rounds to 2 decimal places — handy for printing money or measurements.
</details>

---

### Problem 19: Username AND Password

Set the correct values to `correct_user = "admin"` and `correct_pass = "1234"`. Ask the user for both. Print `"Login successful"` only if BOTH match. Otherwise print `"Login failed"`. If only the username matched, also print `"(wrong password)"`. If only the password matched, also print `"(wrong username)"`.

**Sample interaction:**
```
Username: admin
Password: 9999
Login failed
(wrong password)
```

<details>
<summary>💡 Show solution</summary>

```python
correct_user = "admin"
correct_pass = "1234"

user = input("Username: ")
pwd = input("Password: ")

if user == correct_user and pwd == correct_pass:
    print("Login successful")
else:
    print("Login failed")
    if user == correct_user:
        print("(wrong password)")
    elif pwd == correct_pass:
        print("(wrong username)")
```
**Teaching note:** Notice the **nested** `if` inside the `else`. We only ask "what specifically went wrong?" *after* we know the login failed. Nesting reads naturally here.
</details>

---

### Problem 20: Rock Paper Scissors (One Round)

Set `player = "rock"` and `computer = "scissors"`. Print `"Player wins"`, `"Computer wins"`, or `"Tie"`. Remember: rock beats scissors, scissors beats paper, paper beats rock.

**Expected output:**
```
Player wins
```

<details>
<summary>💡 Show solution</summary>

```python
player = "rock"
computer = "scissors"

if player == computer:
    print("Tie")
elif (player == "rock" and computer == "scissors") or \
     (player == "scissors" and computer == "paper") or \
     (player == "paper" and computer == "rock"):
    print("Player wins")
else:
    print("Computer wins")
```
**Teaching note:** Check ties **first** — it's the simplest case. The backslash `\` lets a long condition span multiple lines without Python getting confused.
</details>

---

## 🔴 Hard

### Problem 21: Which Quadrant?

Given a point `(x, y)` on a graph, print which quadrant it's in:
- Both positive → `"Quadrant 1"`
- x negative, y positive → `"Quadrant 2"`
- Both negative → `"Quadrant 3"`
- x positive, y negative → `"Quadrant 4"`
- On an axis → `"On an axis"`

Test with `x = -2, y = 5`.

**Expected output:**
```
Quadrant 2
```

<details>
<summary>💡 Show solution</summary>

```python
x = -2
y = 5

if x == 0 or y == 0:
    print("On an axis")
elif x > 0 and y > 0:
    print("Quadrant 1")
elif x < 0 and y > 0:
    print("Quadrant 2")
elif x < 0 and y < 0:
    print("Quadrant 3")
else:
    print("Quadrant 4")
```
**Teaching note:** Handle the **special case** (on an axis) first. If you don't, `x = 0, y = 5` would match `y > 0` and incorrectly land in Quadrant 1 or 2.
</details>

---

### Problem 22: Valid Date?

Given a day, month, and year, print `"Valid date"` or `"Invalid date"`. Use these rules:
- Month must be 1–12
- Day must be at least 1
- Months 1, 3, 5, 7, 8, 10, 12 have 31 days
- Months 4, 6, 9, 11 have 30 days
- February has 28 days (ignore leap years for now)

Test with `day = 31, month = 4, year = 2024`.

**Expected output:**
```
Invalid date
```

<details>
<summary>💡 Show solution</summary>

```python
day = 31
month = 4
year = 2024

valid = True

if month < 1 or month > 12:
    valid = False
elif day < 1:
    valid = False
elif month == 2 and day > 28:
    valid = False
elif (month == 4 or month == 6 or month == 9 or month == 11) and day > 30:
    valid = False
elif day > 31:
    valid = False

if valid:
    print("Valid date")
else:
    print("Invalid date")
```
**Teaching note:** A common trick: use a **flag variable** (`valid = True`) and flip it to `False` when something goes wrong. The final `if valid:` then checks the overall result. This pattern scales when you have many rules.
</details>

---

### Problem 23: What Can You Do?

Ask the user for their age. Print all the things they can do based on these rules:
- 5 or older → can start school
- 13 or older → can use most social media
- 16 or older → can get a learner's license (in many places)
- 18 or older → can vote (in most countries)
- 21 or older → adult in every country

If they can do *none* of these, print `"Too young for any of these milestones"`.

**Sample interaction:**
```
Enter your age: 14
Can start school
Can use most social media
```

<details>
<summary>💡 Show solution</summary>

```python
age = int(input("Enter your age: "))

printed_anything = False

if age >= 5:
    print("Can start school")
    printed_anything = True
if age >= 13:
    print("Can use most social media")
    printed_anything = True
if age >= 16:
    print("Can get a learner's license")
    printed_anything = True
if age >= 18:
    print("Can vote")
    printed_anything = True
if age >= 21:
    print("Adult everywhere")
    printed_anything = True

if not printed_anything:
    print("Too young for any of these milestones")
```
**Teaching note:** This is a perfect example of when to use **separate `if`s** instead of `elif`. We *want* multiple branches to fire — a 25-year-old should see all five! If you used `elif`, only the first match would print.
</details>

---

### Problem 24: Movie Ticket Eligibility

A movie has a rating (`"U"`, `"UA"`, `"A"`). Given the viewer's `age` and whether they are `with_adult` (True/False), decide if they can watch:
- `"U"` → everyone can watch
- `"UA"` → under 12 needs an adult
- `"A"` → 18+ only, no exceptions

Test with `rating = "UA"`, `age = 10`, `with_adult = True`.

**Expected output:**
```
Allowed
```

<details>
<summary>💡 Show solution</summary>

```python
rating = "UA"
age = 10
with_adult = True

if rating == "U":
    print("Allowed")
elif rating == "UA":
    if age >= 12 or with_adult:
        print("Allowed")
    else:
        print("Need an adult")
elif rating == "A":
    if age >= 18:
        print("Allowed")
    else:
        print("Adults only")
else:
    print("Unknown rating")
```
**Teaching note:** Nesting an `if` inside an `elif` reads cleanly when the rules differ per category. Notice the `else` at the bottom catches typos like `rating = "PG"` — a safety net.
</details>

---

### Problem 25: Simple Tax Calculator

A country's income tax (yearly, in ₹):
- First ₹2,50,000 → 0% (no tax)
- ₹2,50,001 to ₹5,00,000 → 5% on the part above ₹2,50,000
- ₹5,00,001 to ₹10,00,000 → 5% on ₹2,50,000 + 20% on the part above ₹5,00,000
- Above ₹10,00,000 → 5% on ₹2,50,000 + 20% on ₹5,00,000 + 30% on the rest

Set `income = 750000`. Print the tax owed.

**Expected output:**
```
Tax: 62500.0
```

<details>
<summary>💡 Show solution</summary>

```python
income = 750000

if income <= 250000:
    tax = 0
elif income <= 500000:
    tax = (income - 250000) * 0.05
elif income <= 1000000:
    tax = (250000 * 0.05) + (income - 500000) * 0.20
else:
    tax = (250000 * 0.05) + (500000 * 0.20) + (income - 1000000) * 0.30

print(f"Tax: {tax}")
```
**Teaching note:** Real tax systems are **slab-based** (also called marginal): only the *portion* of income in each slab is taxed at that rate. That's why ₹7,50,000 doesn't just pay 20% × 7,50,000 — only the part above ₹5,00,000 is taxed at 20%.
</details>

---

### Problem 26: Greeting by Hour

Ask the user for the current hour (0–23). Print:
- 5–11 → `"Good morning!"`
- 12–16 → `"Good afternoon!"`
- 17–20 → `"Good evening!"`
- 21–4 (including 0–4) → `"Good night!"`

If they enter a number outside 0–23, print `"Invalid hour"`.

**Sample interaction:**
```
Enter hour (0-23): 14
Good afternoon!
```

<details>
<summary>💡 Show solution</summary>

```python
hour = int(input("Enter hour (0-23): "))

if hour < 0 or hour > 23:
    print("Invalid hour")
elif hour >= 5 and hour <= 11:
    print("Good morning!")
elif hour >= 12 and hour <= 16:
    print("Good afternoon!")
elif hour >= 17 and hour <= 20:
    print("Good evening!")
else:
    print("Good night!")
```
**Teaching note:** "Night" wraps around midnight (21–4), which is awkward to express as one range. Putting it in the `else` is the cleanest trick — anything that didn't match the earlier ranges *must* be night.
</details>

---

### Problem 27: Simple Calculator

Ask the user for two numbers and an operation (`"+"`, `"-"`, `"*"`, `"/"`). Print the result. Handle division by zero by printing `"Cannot divide by zero"`. If the operation is anything else, print `"Unknown operation"`.

**Sample interaction:**
```
First number: 10
Second number: 0
Operation (+ - * /): /
Cannot divide by zero
```

<details>
<summary>💡 Show solution</summary>

```python
a = float(input("First number: "))
b = float(input("Second number: "))
op = input("Operation (+ - * /): ")

if op == "+":
    print(a + b)
elif op == "-":
    print(a - b)
elif op == "*":
    print(a * b)
elif op == "/":
    if b == 0:
        print("Cannot divide by zero")
    else:
        print(a / b)
else:
    print("Unknown operation")
```
**Teaching note:** We use `float()` instead of `int()` so the calculator supports decimal numbers too. Nesting the division-by-zero check inside the `"/"` branch keeps the logic clean — we only worry about that case when actually dividing.
</details>

---

## ⭐ Stretch

### Problem 28: Number Guess — Too High or Too Low?

Set `secret = 42`. Ask the user for **one** guess. Print:
- `"Too low!"` if their guess is less than the secret
- `"Too high!"` if greater
- `"You got it!"` if exactly right
- Bonus: if they're within 5 of the answer (above or below), add `" (Getting warm!)"` on the same line.

**Sample interaction:**
```
Guess the secret number: 40
Too low! (Getting warm!)
```

<details>
<summary>💡 Show solution</summary>

```python
secret = 42
guess = int(input("Guess the secret number: "))

if guess == secret:
    print("You got it!")
else:
    # Figure out direction and warmness
    if guess < secret:
        message = "Too low!"
    else:
        message = "Too high!"

    # abs() gives the distance no matter the direction
    if abs(guess - secret) <= 5:
        message = message + " (Getting warm!)"

    print(message)
```
**Teaching note:** `abs()` returns the absolute value — handy for "distance" without caring about direction. Notice how we **build up** the message string in pieces, then print once at the end. This pattern (compute → then print) is much cleaner than scattering `print` calls everywhere.
</details>

---

### Problem 29: Chinese Zodiac

Ask the user for a birth year. Compute `year % 12` and print the zodiac animal:
- 0 → Monkey, 1 → Rooster, 2 → Dog, 3 → Pig, 4 → Rat, 5 → Ox, 6 → Tiger, 7 → Rabbit, 8 → Dragon, 9 → Snake, 10 → Horse, 11 → Goat

**Sample interaction:**
```
Birth year: 2010
Tiger
```

<details>
<summary>💡 Show solution</summary>

```python
year = int(input("Birth year: "))
remainder = year % 12

if remainder == 0:
    print("Monkey")
elif remainder == 1:
    print("Rooster")
elif remainder == 2:
    print("Dog")
elif remainder == 3:
    print("Pig")
elif remainder == 4:
    print("Rat")
elif remainder == 5:
    print("Ox")
elif remainder == 6:
    print("Tiger")
elif remainder == 7:
    print("Rabbit")
elif remainder == 8:
    print("Dragon")
elif remainder == 9:
    print("Snake")
elif remainder == 10:
    print("Horse")
else:
    print("Goat")
```
**Teaching note:** This works, but it's *long*. Once you learn **dictionaries** in Lesson 08, you'll be able to do the same thing in 2 lines! Sometimes seeing the long version first helps you appreciate why better tools exist.
</details>

---

### Problem 30: Choose Your Own Adventure

Build a tiny branching story. Use multiple `input()` and `if`/`elif`/`else`. At least 3 decision points, each leading somewhere different. Some endings should be reachable only by specific combinations. Be creative — make it about a dragon, a haunted house, a math test, whatever you want!

There is **no single correct answer**. Below is one example to get you started; yours should be different.

<details>
<summary>💡 Show one possible solution</summary>

```python
print("You wake up in a dark forest. There's a path going LEFT and a path going RIGHT.")
choice1 = input("Which way? (left/right): ").lower()

if choice1 == "left":
    print("You find a sleeping dragon. There's gold around it!")
    choice2 = input("Do you SNEAK past or GRAB the gold? (sneak/grab): ").lower()
    if choice2 == "sneak":
        print("You escape safely and find a village. THE END (good ending)")
    elif choice2 == "grab":
        print("The dragon wakes up. You are toast. THE END (bad ending)")
    else:
        print("You stand frozen. The dragon eventually wakes up anyway. THE END")

elif choice1 == "right":
    print("You reach a river. There's a rickety bridge and a boat.")
    choice2 = input("Take the BRIDGE or the BOAT? (bridge/boat): ").lower()
    if choice2 == "bridge":
        choice3 = input("Halfway across, a troll appears. FIGHT or RUN? (fight/run): ").lower()
        if choice3 == "fight":
            print("You bravely defeat the troll. THE END (hero ending)")
        else:
            print("You make it back. Safe but story is short. THE END")
    elif choice2 == "boat":
        print("The boat has a hole. You swim back. Try again tomorrow. THE END")
    else:
        print("You stand at the riverbank forever. THE END")

else:
    print("You stand frozen. A bird poops on your head. THE END")
```
**Teaching note:** This problem mixes **everything** from Lesson 05 — `if`/`elif`/`else`, nested conditions, `.lower()` to be forgiving of casing, and a default `else` branch as a safety net for unexpected input. Real-world programs (chatbots, games, forms) are mostly made of decisions like these.
</details>

---

## What you've practiced

You worked through `if`, `elif`, `else`, comparison operators, logical operators (`and`, `or`, `not`), nested conditions, flag variables, top-down evaluation, when to use `elif` vs separate `if`s, and how to structure decision trees. That's the entire surface area of Lesson 05.

**Next up:** when you're ready, head to [`exercises_06_loops.md`](exercises_06_loops.md) (coming soon) to drill loops.

Or jump to a different format:
- 🎯 [Themed packs](../packs/) — apply conditions in cross-topic puzzles
- 💡 [Did you know?](../did_you_know/) — read about *why* indentation matters
- 🧩 [Challenges](../challenges/) — one puzzle at a time, with progressive hints
