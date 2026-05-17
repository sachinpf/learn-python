# Exercises — Lesson 02: Variables

30 problems to make variables, `input()`, type conversions, and f-strings feel automatic. Use **only** what you learned in Lessons 01–02.

**No `if`, no loops, no lists, no functions.** Stick to basic arithmetic (`+`, `-`, `*`, `/`) — `%`, `//`, and `**` come in Lesson 03.

> **How to use this file:** read the problem, type your code, run it. Only click "Show solution" after you've genuinely tried. The struggle is where the learning happens.

Quick refresher *(संक्षिप्त उजळणी)*:

- A **variable** *(चल)* stores a **value** *(मूल्य)*. Create one with `name = "Sachin"`.
- The `=` is an **arrow pointing left** — the value on the right gets placed in the box on the left.
- The four basic **data types** *(डेटा प्रकार)* are: **string** *(स्ट्रिंग)*, **integer** *(पूर्णांक)*, **float / decimal** *(दशांश)*, **boolean** *(बूलियन)*.
- `type(x)` tells you what kind of thing `x` is.
- `input("prompt: ")` pauses the program and **always returns a string**, even when the user types digits.
- `int("10")` converts text to an integer; `float("3.5")` to a float; `str(10)` back to text.
- **f-strings** are the easy way: `f"My age is {age}"` puts the value of `age` inside the text.

---

## 🟢 Easy

### Problem 1: Store and Show

Create a variable called `language` and put the string `"Python"` inside it. Then print the variable.

**Expected output:**
```
Python
```

<details>
<summary>💡 Show solution</summary>

```python
language = "Python"
print(language)
```
**Teaching note:** The `=` is not the equals from math class — it means "put the value on the right into the box on the left." After this line, `language` is a labeled box holding `"Python"`.
</details>

---

### Problem 2: Three Boxes

Create three variables: `city = "Pune"`, `pin_code = 411001`, `is_metro = True`. Print all three on separate lines.

**Expected output:**
```
Pune
411001
True
```

<details>
<summary>💡 Show solution</summary>

```python
city = "Pune"
pin_code = 411001
is_metro = True

print(city)
print(pin_code)
print(is_metro)
```
**Teaching note:** Three different data types in three boxes — a string, an integer, and a boolean. Python doesn't mind mixing them. Notice `True` is capital-T; lowercase `true` would crash.
</details>

---

### Problem 3: Name vs `"name"`

Run this code and look carefully at the output. Then explain (out loud or in your head) why the two lines are different.

```python
name = "Aarav"
print(name)
print("name")
```

**Expected output:**
```
Aarav
name
```

<details>
<summary>💡 Show solution</summary>

**Why are they different?**

- `print(name)` — no quotes — Python looks up the variable and prints whatever's **inside** the box. The box holds `"Aarav"`.
- `print("name")` — with quotes — Python sees a string and prints it **literally**. It never even looks at the variable.

**Teaching note:** This is one of the most common beginner mix-ups. If you forget the quotes, Python tries to look up a variable that may not exist and crashes with `NameError`. If you add quotes when you didn't mean to, you get the literal word back. Quotes around something = treat it as text. No quotes = treat it as a name to look up.
</details>

---

### Problem 4: Replace What's Inside

Create `favorite_color = "Blue"` and print it. Then change the value to `"Green"` and print it again — using the same variable name both times.

**Expected output:**
```
Blue
Green
```

<details>
<summary>💡 Show solution</summary>

```python
favorite_color = "Blue"
print(favorite_color)

favorite_color = "Green"
print(favorite_color)
```
**Teaching note:** Reassignment doesn't cause a conflict. The second `=` simply throws away the old value and puts the new one in the box. The label `favorite_color` stays the same; only the contents change.
</details>

---

### Problem 5: What Type Am I?

Type and run this. Predict the output **before** running.

```python
print(type("Hello"))
print(type(42))
print(type(3.14))
print(type(False))
```

**Expected output:**
```
<class 'str'>
<class 'int'>
<class 'float'>
<class 'bool'>
```

<details>
<summary>💡 Show solution</summary>

**Teaching note:** `type()` is your detective tool. When code does something weird, `print(type(suspicious_variable))` often reveals the problem immediately — usually because something is a string when you thought it was a number, or vice versa.

The output format `<class 'str'>` looks a bit funny. The word `class` here just means "kind of thing." We'll meet classes properly much later.
</details>

---

### Problem 6: The `x = x + 1` Trick

Create `points = 100`. Then update it three times — each time adding 50 to the **current value** — and print after each update.

**Expected output:**
```
100
150
200
250
```

<details>
<summary>💡 Show solution</summary>

```python
points = 100
print(points)

points = points + 50
print(points)

points = points + 50
print(points)

points = points + 50
print(points)
```
**Teaching note:** `points = points + 50` looks impossible if you read it like math (`100 = 100 + 50`? Never!). The trick: Python reads **the right side first**. It looks up `points` (currently 100), computes `100 + 50` = `150`, and **then** stores 150 back in `points`. Old gone, new in. This pattern is the heartbeat of every loop you'll ever write.
</details>

---

### Problem 7: Spot the Invalid Names

Look at this list of names. Some are valid Python variable names. Some are not. Without running anything, write down which ones would crash if you tried `__ = "value"`.

```
score
1st_place
high_score
my-score
_secret
high score
print
HighScore
```

<details>
<summary>💡 Show solution</summary>

**Invalid (would crash):**
- `1st_place` — names cannot start with a digit
- `my-score` — `-` is not allowed (Python reads it as "my minus score")
- `high score` — spaces are not allowed
- `print` — this is a built-in function name. It technically *works* but breaks `print()` afterwards, so treat it as off-limits

**Valid:**
- `score`, `high_score`, `_secret`, `HighScore`

**Teaching note:** Names must start with a letter or underscore, and may only contain letters, digits, and underscores after that. `HighScore` works, but Python's tradition is **snake_case** — `high_score` — for variable names. You will be the one reading your code six months from now; pick names that future-you will understand.
</details>

---

### Problem 8: f-string with One Variable

Create `hero = "Shivaji"`. Use an **f-string** to print `Hero of the day: Shivaji`.

**Expected output:**
```
Hero of the day: Shivaji
```

<details>
<summary>💡 Show solution</summary>

```python
hero = "Shivaji"
print(f"Hero of the day: {hero}")
```
**Teaching note:** The `f` before the opening quote tells Python "this string has variables in it." Anything inside `{}` is looked up and dropped into the text. Forget the `f` and the output becomes the literal `Hero of the day: {hero}` — Python won't know to swap the variable in.
</details>

---

### Problem 9: f-string with Two Variables

Given `student = "Diya"` and `marks = 92`, print exactly:

**Expected output:**
```
Diya scored 92 out of 100.
```

<details>
<summary>💡 Show solution</summary>

```python
student = "Diya"
marks = 92

print(f"{student} scored {marks} out of 100.")
```
**Teaching note:** You can put as many `{variable}` slots as you want inside an f-string. Notice that `92` is an integer — but the f-string handles it gracefully. No need to convert to string yourself. (Compare with concatenation in Problem 18, where you *would* need `str(marks)`.)
</details>

---

### Problem 10: Multiple Boxes, Same Value

Without using the `=` sign three separate times, set three variables `a`, `b`, `c` all to `0` on a single line. Print all three.

**Expected output:**
```
0
0
0
```

<details>
<summary>💡 Show solution</summary>

```python
a = b = c = 0

print(a)
print(b)
print(c)
```
**Teaching note:** Reading right-to-left: first `c` becomes `0`, then `b = c` (also 0), then `a = b` (also 0). Useful when you want a counter, a total, and a max all starting at zero — handy when you reach loops.
</details>

---

## 🟡 Medium

### Problem 11: Ask and Greet

Ask the user `What is your name? ` and store their answer. Then greet them.

**Sample interaction:**
```
What is your name? Priya
Welcome, Priya! Glad to see you.
```

<details>
<summary>💡 Show solution</summary>

```python
name = input("What is your name? ")
print(f"Welcome, {name}! Glad to see you.")
```
**Teaching note:** `input()` *(इनपुट)* shows the prompt, waits for the user to type and press Enter, then hands the typed text back as a string. The space at the end of the prompt (`"What is your name? "`) is a small kindness — it puts the user's cursor one space after the question mark, instead of glued to it.
</details>

---

### Problem 12: It Looks Like a Number, But...

Ask the user `Enter a number: ` and store the answer. Print the value AND its type.

**Sample interaction:**
```
Enter a number: 42
You typed: 42
Type: <class 'str'>
```

<details>
<summary>💡 Show solution</summary>

```python
answer = input("Enter a number: ")
print(f"You typed: {answer}")
print(f"Type: {type(answer)}")
```
**Teaching note:** This is the single biggest surprise of Lesson 02. Even though the user **typed** `42`, the variable holds the **string** `"42"`. `input()` cannot read minds — it always returns text and leaves the conversion to you. The next two problems show why this matters.
</details>

---

### Problem 13: The Trap (run it and watch it crash)

Type and run this code. It will crash. Read the error message and try to figure out *why*.

```python
age = input("How old are you? ")
next_year = age + 1
print(next_year)
```

<details>
<summary>💡 Show solution</summary>

**What happens:**
```
How old are you? 10
TypeError: can only concatenate str (not "int") to str
```

**Why it crashes:** `input()` returned the string `"10"`, not the integer `10`. When Python sees `"10" + 1`, it doesn't know what you mean — adding a number to text isn't defined. So it stops and yells.

**Teaching note:** Read this error message slowly. *"can only concatenate str (not 'int') to str"* is Python saying "you tried to add an int to a string, and that's not allowed." Almost every beginner hits this in their first hour. The fix is the next problem.
</details>

---

### Problem 14: Fix the Trap

Now make the previous program work: ask the user's age and print **next year's age**.

**Sample interaction:**
```
How old are you? 10
Next year you will be 11
```

<details>
<summary>💡 Show solution</summary>

```python
age = int(input("How old are you? "))
next_year = age + 1
print(f"Next year you will be {next_year}")
```
**Teaching note:** `int(...)` *(पूर्णांक मध्ये बदलणे)* converts a string of digits into an integer. The shortcut `int(input(...))` does both steps on one line: ask for input, then convert.

**Watch out!** If the user types `"ten"` (letters) instead of `10`, `int()` crashes with `ValueError`. For now we trust the user. Lesson 11 (error handling) shows how to handle this gracefully.
</details>

---

### Problem 15: Two Numbers, One Sum

Ask the user for two numbers. Print their sum.

**Sample interaction:**
```
First number: 7
Second number: 8
The sum is 15
```

<details>
<summary>💡 Show solution</summary>

```python
a = int(input("First number: "))
b = int(input("Second number: "))
total = a + b
print(f"The sum is {total}")
```
**Teaching note:** Two separate `input()` calls, each converted to an integer. If you forget either `int()`, you'll concatenate strings instead of adding numbers — `"7" + "8"` becomes `"78"`, not `15`. Try removing one of the `int()`s and see what happens. Surprises are the best teachers.
</details>

---

### Problem 16: Build a Fence

Ask the user for a length (number of fence sections) and print a fence made of `|--` repeated that many times.

**Sample interaction:**
```
How long is the fence? 4
|--|--|--|--
```

<details>
<summary>💡 Show solution</summary>

```python
length = int(input("How long is the fence? "))
print("|--" * length)
```
**Teaching note:** `"|--" * 4` returns `"|--|--|--|--"`. Multiplying a string by a number repeats it. This is one of Python's friendliest surprises — exact same `*` you use for math, doing something completely different (but sensible) when one side is a string.

**Watch out!** `"|--" * 4` works. `4 * "|--"` works the same way. But `"|--" * "4"` (with the 4 in quotes) crashes — you can't multiply a string by a string. The number must be an actual `int`, which is why we used `int(input(...))`.
</details>

---

### Problem 17: Mini Receipt

Set `item = "Notebook"`, `price = 45`, `quantity = 3`. Use f-strings (with math inside) to print:

**Expected output:**
```
Item     : Notebook
Price    : 45
Quantity : 3
Total    : 135
```

<details>
<summary>💡 Show solution</summary>

```python
item = "Notebook"
price = 45
quantity = 3

print(f"Item     : {item}")
print(f"Price    : {price}")
print(f"Quantity : {quantity}")
print(f"Total    : {price * quantity}")
```
**Teaching note:** You can put **any expression** inside `{}`, not just a plain variable. `{price * quantity}` is evaluated first (= 135), then dropped into the text. Cleaner than computing `total = price * quantity` on a separate line — though that's also valid, and sometimes easier to read.
</details>

---

### Problem 18: Convert Before You Add

Make the next-year program **without** using f-strings — use `+` concatenation instead. (You'll need `str()` somewhere.)

**Sample interaction:**
```
How old are you? 10
Next year you will be 11
```

<details>
<summary>💡 Show solution</summary>

```python
age = int(input("How old are you? "))
next_year = age + 1
print("Next year you will be " + str(next_year))
```
**Teaching note:** Concatenation with `+` only works when **both sides are strings**. `next_year` is an integer, so we wrap it in `str(...)` to turn it into the text `"11"` before joining. Compare with the f-string version (Problem 14):

```python
print(f"Next year you will be {next_year}")
```
The f-string handles the conversion automatically. That's why most modern Python uses f-strings.
</details>

---

### Problem 19: Decimal Income

Ask the user for an hourly wage (in rupees, with a decimal) and the number of hours worked. Print the total earnings.

**Sample interaction:**
```
Hourly wage: 125.50
Hours worked: 6
Total earned: 753.0 rupees
```

<details>
<summary>💡 Show solution</summary>

```python
wage = float(input("Hourly wage: "))
hours = float(input("Hours worked: "))
total = wage * hours
print(f"Total earned: {total} rupees")
```
**Teaching note:** Use `float()` *(दशांश मध्ये बदलणे)* when the user might type a decimal. `float("125.50")` becomes `125.5`. `int()` would crash on `"125.50"` because `int` means *whole* number. When in doubt, `float()` is the safer choice for "real-world" numbers like prices, distances, and weights.
</details>

---

### Problem 20: Type Mix-Up

Predict the output of each line, then run it to check.

```python
print(5 + 5)
print("5" + "5")
print(5 * 3)
print("5" * 3)
print(type(5 / 2))
print(type(5))
```

<details>
<summary>💡 Show solution</summary>

**Expected output:**
```
10
55
15
555
<class 'float'>
<class 'int'>
```

**Teaching note:** Six small surprises:
1. `5 + 5` → numbers add → `10`
2. `"5" + "5"` → strings concatenate → `"55"`
3. `5 * 3` → number times number → `15`
4. `"5" * 3` → string times number → repetition → `"555"`
5. `5 / 2` → division **always** returns a float in Python (even when it divides evenly: `4 / 2` is `2.0`, not `2`)
6. `5` (no division) is a plain int

The same `+` and `*` operators behave differently depending on what's on each side. Python looks at the types and picks the right meaning. **Knowing the types in your head as you read code is half the battle in debugging.**
</details>

---

## 🔴 Hard

### Problem 21: Birthday Card

Ask the user for their name and their age. Print a 5-line birthday card.

**Sample interaction:**
```
Your name: Sachin
Your age: 10

*****************************
* Happy Birthday, Sachin!  *
* You are now 10 years old *
* Have an amazing year!    *
*****************************
```

<details>
<summary>💡 Show solution</summary>

```python
name = input("Your name: ")
age = int(input("Your age: "))

print()
print("*****************************")
print(f"* Happy Birthday, {name}!  *")
print(f"* You are now {age} years old *")
print("* Have an amazing year!    *")
print("*****************************")
```
**Teaching note:** The alignment of the `*` on the right side will only stay perfect if the name and age are short enough. Try `Madhusudan` and you'll see the box go crooked. That's a real problem programmers face — and the proper fix uses **f-string formatting tricks** (`{name:<20}` to pad to 20 characters) which you'll meet later. For now, "looks reasonable for short names" is good enough.
</details>

---

### Problem 22: Garden Path

A square garden has a side of `side` metres. Ask the user for the side length (could be decimal). Compute and print:
- the **perimeter** *(परिमिती)* — the distance around the garden
- the **area** *(क्षेत्रफळ)* — the surface inside the garden

**Sample interaction:**
```
Side length (m): 4.5
Perimeter: 18.0 m
Area: 20.25 sq m
```

<details>
<summary>💡 Show solution</summary>

```python
side = float(input("Side length (m): "))
perimeter = 4 * side
area = side * side

print(f"Perimeter: {perimeter} m")
print(f"Area: {area} sq m")
```
**Teaching note:** A square's perimeter is `4 × side`; area is `side × side`. We used `float()` because the user might type something like `4.5`. Notice that `4 * 4.5` is `18.0` — when an `int` and a `float` are multiplied, the result is a `float`. Python "promotes" the int to keep precision.

A small extension: Lesson 03 will introduce `**` for powers, so `side ** 2` could replace `side * side`. Both give the same answer.
</details>

---

### Problem 23: Bill Splitter

Three friends shared a bill. Ask for the total bill amount. Compute and print each person's share.

**Sample interaction:**
```
Total bill: 750
Each person pays: 250.0
```

<details>
<summary>💡 Show solution</summary>

```python
bill = float(input("Total bill: "))
people = 3
per_person = bill / people

print(f"Each person pays: {per_person}")
```
**Teaching note:** `/` always produces a `float`, even when the division is exact. `750 / 3` is `250.0`, not `250`. If you wanted a cleaner-looking output, you could try `int(per_person)` — but that throws away the decimal, which is wrong when the bill doesn't divide evenly (e.g. `751 / 3`). f-strings have a built-in way to control decimal places (`{per_person:.2f}`) that you'll learn naturally over time.
</details>

---

### Problem 24: Years to a Goal

Ask the user for their current age and a target age. Print how many years they have to get there.

**Sample interaction:**
```
Your age now: 12
Target age: 60
Years to go: 48
```

<details>
<summary>💡 Show solution</summary>

```python
age_now = int(input("Your age now: "))
target = int(input("Target age: "))
years = target - age_now

print(f"Years to go: {years}")
```
**Teaching note:** Nothing tricky — just two inputs, two `int()` conversions, one subtraction. The point of this problem is **building the habit**: every time `input()` produces something that needs math, wrap it in `int()` or `float()`. Forgetting it is the single most common bug at this stage.

**Watch out!** If the user types `target = 8` and `age_now = 12`, the answer is `-4` — they've already passed the target. The math still works, but the output is a little funny ("Years to go: -4"). Properly handling that needs `if`/`else` from Lesson 05.
</details>

---

### Problem 25: Speed Calculator

A car travels a `distance` (in km) in a given `time` (in hours). Ask the user for both, then print the **speed** in km/h.

**Sample interaction:**
```
Distance (km): 240
Time (hours): 4
Speed: 60.0 km/h
```

<details>
<summary>💡 Show solution</summary>

```python
distance = float(input("Distance (km): "))
time = float(input("Time (hours): "))
speed = distance / time

print(f"Speed: {speed} km/h")
```
**Teaching note:** Real units, real formula: speed = distance ÷ time. We use `float()` because real journeys aren't always whole numbers of hours.

**Watch out!** If the user types `0` for time, the program crashes with `ZeroDivisionError`. Dividing by zero is undefined — Python won't guess what you meant. Properly guarding against this needs `if` (Lesson 05).
</details>

---

### Problem 26: Mad Cricket Story

Ask the user for: a player's name, a bowler's name, a number of runs, and a stadium name. Print a 3-line story using **all four** values.

**Sample interaction:**
```
Batter's name: Rohit
Bowler's name: Bumrah
Runs scored: 87
Stadium: Wankhede

At Wankhede, Rohit scored 87 runs.
Bumrah bowled some great overs against him.
What a thrilling match!
```

<details>
<summary>💡 Show solution</summary>

```python
batter = input("Batter's name: ")
bowler = input("Bowler's name: ")
runs = int(input("Runs scored: "))
stadium = input("Stadium: ")

print()
print(f"At {stadium}, {batter} scored {runs} runs.")
print(f"{bowler} bowled some great overs against him.")
print("What a thrilling match!")
```
**Teaching note:** Four inputs, three of them strings (no `int()` needed) and one integer (needs `int()`). Notice we used `print()` to insert a blank line between the questions and the story — a small touch that makes the output feel polished. Real programs lean on small touches like this all the time.
</details>

---

## 🌟 Stretch

### Problem 27: Predict the Output — Snapshot

Without running this, write down what `y` will print. Then run it to check.

```python
x = 10
y = x
x = 99
print(y)
```

<details>
<summary>💡 Show solution</summary>

**Expected output:**
```
10
```

**Why?** Read line by line:
1. `x = 10` — the box `x` holds `10`.
2. `y = x` — Python looks up `x` (currently 10) and puts that value `10` into the box `y`. **It does not link the boxes together.** `y` now has its own copy.
3. `x = 99` — the box `x` is changed. The box `y` is untouched.
4. `print(y)` — `y` still holds `10`.

**Teaching note:** Many beginners expect `y` to "follow" `x` and become `99`. It doesn't, because numbers (and strings, booleans, floats) are copied at the moment of assignment. They are **immutable** — once made, they don't change; you can only swap the box's contents out for a new value. (Lists, which you'll meet in Lesson 07, behave differently — and that surprise is its own famous trap.)
</details>

---

### Problem 28: The Swap

Set `a = "left"` and `b = "right"`. Swap their values **in a single line of code** without using a third variable. Print both before and after.

**Expected output:**
```
Before: a = left, b = right
After:  a = right, b = left
```

<details>
<summary>💡 Show solution</summary>

```python
a = "left"
b = "right"
print(f"Before: a = {a}, b = {b}")

a, b = b, a

print(f"After:  a = {a}, b = {b}")
```
**Teaching note:** `a, b = b, a` is one of Python's elegant gifts. In most other languages this swap takes three lines and a temporary variable:

```python
temp = a
a = b
b = temp
```

Python's **multiple assignment** evaluates the entire right side first (`b, a` → `"right", "left"`) and then unpacks it into the left side. The result: `a` and `b` trade values in one move.
</details>

---

### Problem 29: Predict the Output — Multiple Assignment

Without running this, write down the output. Then run it.

```python
a, b, c = 1, 2, 3
print(a, b, c)

a, b, c = c, a, b
print(a, b, c)
```

<details>
<summary>💡 Show solution</summary>

**Expected output:**
```
1 2 3
3 1 2
```

**Why?** After the first line, `a = 1`, `b = 2`, `c = 3`. 

For the second line, Python first **freezes the right side** as the tuple `(3, 1, 2)` (using the *current* values of `c`, `a`, `b`). Then it unpacks: `a` gets `3`, `b` gets `1`, `c` gets `2`. Print confirms it.

**Teaching note:** This is the same idea as the two-variable swap, scaled up. As long as the number of names on the left matches the number of values on the right, Python will happily pair them. You can use this trick to rotate three counters, swap any pair in a triple, or simply make a chunk of assignments fit on one line.
</details>

---

### Problem 30: Build a Personal Stats Line

Ask the user for: their name, their birth year, their height (in feet, decimal), and whether they like Python (`true` or `false` — your program will accept lowercase).

Print a single line that summarises everything. Use **f-strings with math inside** to compute their age (assume the current year is 2026).

**Sample interaction:**
```
Name: Aarav
Birth year: 2014
Height (feet): 4.6
Like Python (true/false)? true

Aarav is 12 years old, 4.6 feet tall, and Python-fan = true.
```

<details>
<summary>💡 Show solution</summary>

```python
name = input("Name: ")
birth_year = int(input("Birth year: "))
height = float(input("Height (feet): "))
likes_python = input("Like Python (true/false)? ")

print()
print(f"{name} is {2026 - birth_year} years old, {height} feet tall, and Python-fan = {likes_python}.")
```
**Teaching note:** Three things to notice in this one line:

1. **f-string math.** `{2026 - birth_year}` is evaluated *inside* the f-string — no need for a separate `age = ...` line.
2. **`likes_python` is a string, not a bool.** The user types `"true"` (text). A real boolean would be `True` (capital T, no quotes). For now, we keep it as text. (Lesson 05 + 11 will show how to convert `"true"` → `True` properly.)
3. **Mixing four types in one f-string** — `str` (`name`), `int` (computed age), `float` (`height`), and another `str` (`likes_python`). f-strings handle them all without complaint. This is exactly why f-strings replaced concatenation: with `+` you'd need `str(2026 - birth_year)` and `str(height)`, and the line would be twice as long.
</details>

---

## What you practiced 🎓

| Tool | Where it came from |
|---|---|
| `variable = value` assignment | Lesson 02 |
| `print(variable)` vs `print("variable")` | Lesson 02 |
| Reassignment, including `x = x + 1` | Lesson 02 |
| `type()` to inspect values | Lesson 02 |
| `int()`, `float()`, `str()` conversions | Lesson 02 |
| `input()` always returning a string | Lesson 02 |
| `+` for concatenation, `*` for repetition | Lesson 02 |
| f-strings with variables and math inside | Lesson 02 |
| Multiple assignment + the swap trick | Lesson 02 |

If any of these feel shaky, head back to `01_foundations/lesson_02_variables.md` for a refresher, then return.

**Next:** `exercises_03_numbers_and_math.md` — operators, order of operations, modulus, exponents, and the `math` module.
