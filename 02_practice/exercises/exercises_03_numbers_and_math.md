# Exercises — Lesson 03: Numbers and Math

30 problems to make Python's math operators, the `math` module, and number-handling tricks feel automatic. Use **only** what you've learned in Lessons 01–03.

**No `if`, no loops, no lists, no functions, no string methods.** Stick to `print`, variables, `input`, type conversion, f-strings, and all the math.

> **How to use this file:** read the problem, type your code, run it. Only click "Show solution" after you've genuinely tried. The struggle is where the learning happens.

Quick refresher *(संक्षिप्त उजळणी)*:

- Arithmetic **operators**: `+` **addition** (बेरीज — दोन संख्या एकत्र करणे), `-` **subtraction** (वजाबाकी — एका संख्येतून दुसरी काढून घेणे), `*` **multiplication** (गुणाकार — संख्या ठराविक वेळा बेरीज करणे), `/` **division** (भागाकार — एक संख्या दुसऱ्याने भागणे).
- `//` is **floor division** — division that throws away the decimal: `15 // 4 = 3`.
- `%` is **modulus** (भागाकाराचा शेष — भागाकारानंतर उरलेली संख्या) — the leftover after division: `15 % 4 = 3`.
- `**` is **exponent** — power: `2 ** 3 = 8`.
- Python follows **PEMDAS**: parentheses → exponents → `*` `/` `//` `%` → `+` `-`. Use parentheses when in doubt.
- Shortcut updates: `x += 5` is short for `x = x + 5`. Same for `-=`, `*=`, `/=`.
- Built-ins: `abs(-7)` → `7`. `round(3.7)` → `4`. `round(3.14159, 2)` → `3.14`. `min(a, b, c)`, `max(a, b, c)`.
- The **`math` module** (मोड्यूल — कोडाची स्वतंत्र फाइल, जी import करता येते): `import math`, then `math.sqrt(25)` → `5.0`, `math.pi`, `math.ceil(3.2)`, `math.floor(3.9)`, `math.factorial(5)`.
- `/` **always returns a float**, even when it divides evenly: `10 / 2 = 5.0`. Use `//` if you want an integer.

---

## 🟢 Easy

### Problem 1: Quick Sum

Print the result of `42 + 58`. Don't use a variable — just put the math directly inside `print`.

**Expected output:**
```
100
```

<details>
<summary>💡 Show solution</summary>

```python
print(42 + 58)
```
**Teaching note:** Python evaluates the expression inside `print()` first, then prints the result. You can put any math expression there — `print` doesn't care whether it's a number, a string, or a calculation.
</details>

---

### Problem 2: Difference of Two Numbers

Store `apples_picked = 47` and `apples_eaten = 9`. Print how many apples are left.

**Expected output:**
```
38
```

<details>
<summary>💡 Show solution</summary>

```python
apples_picked = 47
apples_eaten = 9
apples_left = apples_picked - apples_eaten

print(apples_left)
```
**Teaching note:** Naming the result (`apples_left`) makes the code read like a sentence: "apples left equals apples picked minus apples eaten." You *could* squish it into `print(47 - 9)`, but naming intermediate values is what makes longer programs readable later.
</details>

---

### Problem 3: True Division vs Floor Division

Run these two lines and look at the output. Notice the difference.

```python
print(17 / 5)
print(17 // 5)
```

**Expected output:**
```
3.4
3
```

<details>
<summary>💡 Show solution</summary>

**Why the difference?**

- `/` is **true division** — gives you the real answer, including the decimal part. Always returns a **float** (notice the `.0` ending, even when the division is exact: `10 / 2 = 5.0`).
- `//` is **floor division** — "throw away anything after the decimal point." `17 ÷ 5 = 3.4`, drop the `.4`, you get `3`. Returns an **integer** when both inputs are integers.

**Teaching note:** Use `/` when you want a precise answer (sharing chocolates fairly), `//` when you want a whole-number answer (how many full buses can I fill?). They look almost identical but solve different problems. Pick the one that fits the question.
</details>

---

### Problem 4: The Leftover

Use the **modulus** operator `%` to find the remainder when `100` is divided by `7`. Print it.

**Expected output:**
```
2
```

<details>
<summary>💡 Show solution</summary>

```python
print(100 % 7)
```
**Teaching note:** `100 ÷ 7 = 14` with a remainder of `2`. The `%` operator hands you that remainder directly. It's one of the most useful operators in programming — you'll use it for "every Nth item," "even or odd," "is X a multiple of Y," and lots more once you reach Lesson 05.
</details>

---

### Problem 5: Powers of Two

Compute `2` raised to the power of `10` using `**` and print it.

**Expected output:**
```
1024
```

<details>
<summary>💡 Show solution</summary>

```python
print(2 ** 10)
```
**Teaching note:** `2 ** 10` means `2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2`. Computer people memorize this one — `2 ** 10 = 1024` shows up everywhere (a kilobyte, a kibibyte, RAM sizes). `**` is Python's "to the power of" operator, not `^` like some calculators.
</details>

---

### Problem 6: Order of Operations

Predict what each line prints **before** running it. Then run.

```python
print(2 + 3 * 4)
print((2 + 3) * 4)
print(10 - 6 / 2)
print(2 ** 3 + 1)
```

**Expected output:**
```
14
20
7.0
9
```

<details>
<summary>💡 Show solution</summary>

**Walk through each one:**

- `2 + 3 * 4` → `*` first, so `3 * 4 = 12`, then `2 + 12 = 14`.
- `(2 + 3) * 4` → parentheses first, `2 + 3 = 5`, then `5 * 4 = 20`. Parens **override** the normal order.
- `10 - 6 / 2` → `/` first, `6 / 2 = 3.0` (true division gives a float), then `10 - 3.0 = 7.0`.
- `2 ** 3 + 1` → `**` first (it's even higher than `*`), `2 ** 3 = 8`, then `8 + 1 = 9`.

**Teaching note:** PEMDAS in Python: **P**arentheses → **E**xponents → `*` `/` `//` `%` → `+` `-`. When unsure, **add parentheses** — they cost nothing and make your intent obvious to anyone reading the code.
</details>

---

### Problem 7: Update with `+=`

Start with `score = 0`. Add `10` to it using `+=`. Then add `25` more. Print the final score.

**Expected output:**
```
35
```

<details>
<summary>💡 Show solution</summary>

```python
score = 0
score += 10
score += 25

print(score)
```
**Teaching note:** `score += 10` is shorthand for `score = score + 10`. It reads as "increase score by 10." There's also `-=`, `*=`, `/=` for the other operators. You'll lean on `+=` heavily once we hit loops in Lesson 06.
</details>

---

### Problem 8: Absolute Value

A thermometer reads `-12` degrees. Use `abs()` to print just the size of the number (without the sign).

**Expected output:**
```
12
```

<details>
<summary>💡 Show solution</summary>

```python
temperature = -12
print(abs(temperature))
```
**Teaching note:** `abs()` is short for "absolute value" — distance from zero, ignoring sign. `abs(-12) = 12`, `abs(12) = 12`, `abs(0) = 0`. Useful when you only care about *how big* a difference is, not which direction.
</details>

---

### Problem 9: Rounding a Price

A bill comes to `175.4567` rupees. Use `round()` to round it to **2 decimal places**. Print the rounded value.

**Expected output:**
```
175.46
```

<details>
<summary>💡 Show solution</summary>

```python
bill = 175.4567
print(round(bill, 2))
```
**Teaching note:** `round(x, n)` rounds `x` to `n` decimal places. Without the second number, `round(x)` rounds to the nearest whole. Money usually wants 2 decimals; scientific work might want 6.
</details>

---

### Problem 10: Smallest and Largest

Given `min(8, 3, 11, 5, 2)` and `max(8, 3, 11, 5, 2)`, print both — the smallest first, then the largest.

**Expected output:**
```
2
11
```

<details>
<summary>💡 Show solution</summary>

```python
print(min(8, 3, 11, 5, 2))
print(max(8, 3, 11, 5, 2))
```
**Teaching note:** `min()` and `max()` accept as many numbers as you want and return the smallest / largest. They also work on a list (you'll see that in Lesson 07). Saves writing a comparison chain by hand.
</details>

---

## 🟡 Medium

### Problem 11: Rectangle Area

Ask the user for the **length** and **width** of a rectangle (both whole numbers). Print the area.

**Sample interaction:**
```
Length: 8
Width: 5
Area: 40
```

<details>
<summary>💡 Show solution</summary>

```python
length = int(input("Length: "))
width = int(input("Width: "))
area = length * width

print(f"Area: {area}")
```
**Teaching note:** `input()` always hands you a **string** — even when the user types `8`. `int(...)` converts that string into a number you can multiply. Without the `int(...)` wrapper, `length * width` would crash because Python doesn't multiply strings together.
</details>

---

### Problem 12: Rectangle Perimeter

Same rectangle, same inputs. This time print the **perimeter** (परिमिती — आकाराभोवती फिरताना मिळणारी एकूण लांबी) — the distance around the outside.

**Sample interaction:**
```
Length: 8
Width: 5
Perimeter: 26
```

<details>
<summary>💡 Show solution</summary>

```python
length = int(input("Length: "))
width = int(input("Width: "))
perimeter = 2 * (length + width)

print(f"Perimeter: {perimeter}")
```
**Teaching note:** Notice the parentheses around `length + width`. Without them, Python would do `2 * length + width` — multiply by 2 first, then add width. Wrong answer! Parentheses force the addition to happen first, *then* the multiplication. PEMDAS in action.
</details>

---

### Problem 13: Circle Area

Ask the user for a **radius** (a decimal number — use `float()`). Use `math.pi` and `**` to compute the area. Print it rounded to 2 decimals.

**Formula:** `area = π × radius²`

**Sample interaction:**
```
Radius: 5
Area: 78.54
```

<details>
<summary>💡 Show solution</summary>

```python
import math

radius = float(input("Radius: "))
area = math.pi * radius ** 2

print(f"Area: {round(area, 2)}")
```
**Teaching note:** Three new ideas in one line. `import math` makes the `math` module available — you do it **once**, usually at the top of your file. `math.pi` is the value of π (not a function, so no parentheses). `radius ** 2` is `radius × radius`. Python evaluates `radius ** 2` first (PEMDAS — exponent before multiplication), then multiplies by `math.pi`.
</details>

---

### Problem 14: Last Digit of a Number

Use `%` to find the last digit of `73486`. Print it. (Hint: any number `% 10` gives its last digit.)

**Expected output:**
```
6
```

<details>
<summary>💡 Show solution</summary>

```python
number = 73486
last_digit = number % 10

print(last_digit)
```
**Teaching note:** `73486 ÷ 10 = 7348` remainder `6`. The `% 10` trick is everywhere in programming: peeling digits off a number, checking the last digit of a phone number, generating short codes, etc. Pair it with `// 10` (which chops off the last digit) and you can dismantle any number digit by digit.
</details>

---

### Problem 15: Minutes to Hours and Minutes

Ask the user for a number of **total minutes**. Convert and print as hours + minutes.

**Sample interaction:**
```
Total minutes: 215
3 hours and 35 minutes
```

<details>
<summary>💡 Show solution</summary>

```python
total = int(input("Total minutes: "))
hours = total // 60
minutes = total % 60

print(f"{hours} hours and {minutes} minutes")
```
**Teaching note:** The classic `//` + `%` pair. `//` gives the **whole** part (how many full 60s fit), `%` gives the **leftover** (what's left after the whole 60s). Same trick works for seconds → minutes:seconds, days → weeks+days, paisa → rupees+paisa.
</details>

---

### Problem 16: Tip Calculator

Ask the user for the **bill amount** (rupees, as a float) and the **tip percentage** (as an integer). Print the tip and the total.

**Sample interaction:**
```
Bill: 480.00
Tip %: 12
Tip: 57.6
Total: 537.6
```

<details>
<summary>💡 Show solution</summary>

```python
bill = float(input("Bill: "))
tip_percent = int(input("Tip %: "))

tip = bill * tip_percent / 100
total = bill + tip

print(f"Tip: {tip}")
print(f"Total: {total}")
```
**Teaching note:** Reading `bill * tip_percent / 100`: Python goes left-to-right when operators have the same precedence — first `bill * tip_percent`, then divide by 100. Same answer either way because multiplication and division are associative here. Good habit: name your intermediate values (`tip`) so the formula reads top-to-bottom like a recipe.
</details>

---

### Problem 17: Average of Three Numbers

Ask for three test scores (integers). Print the average as a float, rounded to 1 decimal place.

**Sample interaction:**
```
Score 1: 88
Score 2: 92
Score 3: 79
Average: 86.3
```

<details>
<summary>💡 Show solution</summary>

```python
a = int(input("Score 1: "))
b = int(input("Score 2: "))
c = int(input("Score 3: "))

average = (a + b + c) / 3

print(f"Average: {round(average, 1)}")
```
**Teaching note:** Don't forget the parentheses around `a + b + c`. Without them, Python would do `c / 3` first (because `/` is higher precedence than `+`) and then add — wrong answer! Always group the sum with parentheses when dividing.
</details>

---

### Problem 18: Kilometers to Miles

Ask the user for a distance in **kilometers** (float). Convert to **miles** using the multiplier `0.621371`. Print rounded to 2 decimals.

**Sample interaction:**
```
Kilometers: 12.5
Miles: 7.77
```

<details>
<summary>💡 Show solution</summary>

```python
km = float(input("Kilometers: "))
miles = km * 0.621371

print(f"Miles: {round(miles, 2)}")
```
**Teaching note:** Unit conversions are just one multiplication — the trick is *which* number. `0.621371` is "miles per kilometer." If you wanted the other direction (miles → km), the multiplier would be `1.609344` (kilometers per mile). Conversion factors are surprisingly important in real software: nearly every science, engineering, or finance program does this somewhere.
</details>

---

### Problem 19: Celsius to Fahrenheit

Ask the user for a temperature in **Celsius** (float). Convert to **Fahrenheit** and print.

**Formula:** `F = (C × 9/5) + 32`

**Sample interaction:**
```
Celsius: 37
Fahrenheit: 98.6
```

<details>
<summary>💡 Show solution</summary>

```python
celsius = float(input("Celsius: "))
fahrenheit = (celsius * 9/5) + 32

print(f"Fahrenheit: {fahrenheit}")
```
**Teaching note:** The parentheses around `(celsius * 9/5)` aren't strictly required (multiplication and division already happen before `+`) — but they make the formula match what people write on a whiteboard. Code that mirrors the math people already know is code that's easier to trust.
</details>

---

### Problem 20: Square Root

Ask the user for a non-negative number. Use `math.sqrt()` to print its square root.

**Sample interaction:**
```
Number: 169
Square root: 13.0
```

<details>
<summary>💡 Show solution</summary>

```python
import math

number = float(input("Number: "))
root = math.sqrt(number)

print(f"Square root: {root}")
```
**Teaching note:** `math.sqrt()` always returns a float — `math.sqrt(169) = 13.0`, not `13`. If you want an integer, wrap it in `int()`: `int(math.sqrt(169))` → `13`. Note that `math.sqrt()` crashes on negative numbers (with `ValueError`); Lesson 11 will cover how to handle that.
</details>

---

## 🔴 Hard

### Problem 21: Hypotenuse of a Right Triangle

Ask for the two shorter sides (`a` and `b`) of a right triangle. Compute the hypotenuse using the Pythagorean theorem.

**Formula:** `c = √(a² + b²)`

**Sample interaction:**
```
Side a: 3
Side b: 4
Hypotenuse: 5.0
```

<details>
<summary>💡 Show solution</summary>

```python
import math

a = float(input("Side a: "))
b = float(input("Side b: "))

c = math.sqrt(a ** 2 + b ** 2)

print(f"Hypotenuse: {c}")
```
**Teaching note:** Four operations in one line — read it carefully. `a ** 2` first (exponent is highest precedence), then `b ** 2`, then `+`, then `math.sqrt()` wraps the whole sum. You could split this into steps if it helps: `a_squared = a ** 2`, `b_squared = b ** 2`, `c = math.sqrt(a_squared + b_squared)`. Both styles are fine.
</details>

---

### Problem 22: BMI Calculator

Ask the user for weight (in kg) and height (in meters). Compute and print BMI rounded to 1 decimal place.

**Formula:** `BMI = weight ÷ height²`

**Sample interaction:**
```
Weight (kg): 62
Height (m): 1.72
BMI: 21.0
```

<details>
<summary>💡 Show solution</summary>

```python
weight = float(input("Weight (kg): "))
height = float(input("Height (m): "))

bmi = weight / (height ** 2)

print(f"BMI: {round(bmi, 1)}")
```
**Teaching note:** Without the parentheses, `weight / height ** 2` would compute `height ** 2` first (exponents beat division) and then divide — which actually gives the right answer here! But the parentheses make the intent visible: "divide by (height squared)." When the math is non-obvious, parens are documentation.
</details>

---

### Problem 23: Simple Interest

Ask for **principal** (rupees, float), **rate** (percent per year, float), and **time** (years, int). Compute the simple interest and the total amount.

**Formula:** `SI = (P × R × T) / 100`

**Sample interaction:**
```
Principal: 10000
Rate (% per year): 7.5
Time (years): 3
Interest: 2250.0
Total: 12250.0
```

<details>
<summary>💡 Show solution</summary>

```python
principal = float(input("Principal: "))
rate = float(input("Rate (% per year): "))
time = int(input("Time (years): "))

interest = (principal * rate * time) / 100
total = principal + interest

print(f"Interest: {interest}")
print(f"Total: {total}")
```
**Teaching note:** Three inputs, two of them floats (because money and rates aren't whole numbers) and one integer (years). Choosing the right converter for each input is part of writing correct programs — using `int()` for the rate would have crashed the user typing `7.5`.
</details>

---

### Problem 24: Coin Splitter

Ask the user for an amount in **paisa** (1 rupee = 100 paisa). Print how many rupees and how many leftover paisa.

**Sample interaction:**
```
Amount (paisa): 1247
12 rupees and 47 paisa
```

<details>
<summary>💡 Show solution</summary>

```python
paisa = int(input("Amount (paisa): "))
rupees = paisa // 100
leftover = paisa % 100

print(f"{rupees} rupees and {leftover} paisa")
```
**Teaching note:** Same trick as the minutes/hours problem — `//` for the whole part (how many full 100s), `%` for the leftover. This pattern shows up wherever you have a "small unit" and a "big unit": cents↔dollars, inches↔feet, seconds↔minutes. Once you see it, you'll see it everywhere.
</details>

---

### Problem 25: Seconds to H:M:S

Ask for a number of **total seconds** (integer). Print as `H:MM:SS` — hours, minutes, seconds, separated by colons.

**Sample interaction:**
```
Total seconds: 7384
2:3:4
```

<details>
<summary>💡 Show solution</summary>

```python
total = int(input("Total seconds: "))

hours = total // 3600
remaining = total % 3600
minutes = remaining // 60
seconds = remaining % 60

print(f"{hours}:{minutes}:{seconds}")
```
**Teaching note:** Two passes of the `//` + `%` trick. First, peel off the hours (3600 seconds in an hour). Then take what's left and peel off the minutes. Whatever survives is seconds. Naming the intermediate value `remaining` makes the two-step logic readable. (For nicely zero-padded output like `2:03:04`, you'd use f-string formatting tricks — but those come later.)
</details>

---

### Problem 26: Compound Operations

Start with `total = 100`. Apply these operations **in order** using shortcut operators (`+=`, `-=`, `*=`, `/=`):

1. Add 50.
2. Multiply by 2.
3. Subtract 30.
4. Divide by 4.

Print the final value of `total`.

**Expected output:**
```
67.5
```

<details>
<summary>💡 Show solution</summary>

```python
total = 100
total += 50      # 150
total *= 2       # 300
total -= 30      # 270
total /= 4       # 67.5

print(total)
```
**Teaching note:** Trace the value mentally as you read down. Notice the final result is `67.5`, not `67` — `/=` is true division and turns `total` into a float, even though we started with an integer. Once a number becomes a float, it usually stays a float for the rest of its life in that variable.
</details>

---

## 🌟 Stretch

### Problem 27: Predict the Output — Tricky Division

For each line, **predict** the output, then run to check. For each one, can you say in one sentence *why*?

```python
print(10 / 3)
print(10 // 3)
print(10 % 3)
print(-10 // 3)
print(10 / 2)
```

<details>
<summary>💡 Show solution</summary>

**Expected output:**
```
3.3333333333333335
3
1
-4
5.0
```

**Why each one:**

- `10 / 3` → true division, full decimal. The trailing `...5` instead of `...3` is a *floating-point* artifact — see Problem 29.
- `10 // 3` → floor division, drop the decimal. `3`.
- `10 % 3` → remainder. `10 = 3·3 + 1`, so `1`.
- `-10 // 3` → here's the trap. Floor division rounds **toward negative infinity**, not toward zero. `-10 / 3 = -3.333...`, and the next *lower* integer is `-4`. Not `-3` like you might expect. This trips up almost everyone.
- `10 / 2` → exact division but still a float (`5.0`, not `5`). `/` is always-float, no exceptions.

**Teaching note:** Tiny operators, big surprises. The negative floor-division behavior is a deliberate design choice in Python — it keeps `a // b * b + a % b == a` true for negative numbers too. Doesn't matter for most beginner code, but worth knowing it exists.
</details>

---

### Problem 28: The Float Surprise

Run this and look closely:

```python
print(0.1 + 0.2)
print(0.1 + 0.2 == 0.3)
```

**Expected output:**
```
0.30000000000000004
False
```

Wait — `0.1 + 0.2` is supposed to be `0.3`, right? Why isn't it?

<details>
<summary>💡 Show solution</summary>

**Why this happens (the short version):**

Computers store numbers in **binary** (base 2). Decimals like `0.1` and `0.2` don't have an exact representation in binary — same way `1/3` doesn't have an exact decimal representation (`0.333...` goes on forever). The computer stores the closest binary approximation, and when you add two approximations, the tiny errors add up.

**This is not a Python bug.** It happens in *every* programming language that uses floating-point math: JavaScript, C, Java, Go, Excel — all of them. It's a fundamental fact about how decimal numbers are stored on computers.

**What to do about it:**

- For "close enough" comparisons, use `round(0.1 + 0.2, 10) == round(0.3, 10)` — round both sides to N decimal places first.
- For money: store as **integer paisa** (or cents) instead of float rupees. Whole-number math is exact.
- For most beginner work: just be aware the tiny extra digits exist. They won't cause issues until you start comparing floats with `==`.

**Teaching note:** This is the #1 "why is my program lying to me?" moment for new programmers. The answer isn't "Python is broken" — it's "computers can't store every decimal exactly." Worth knowing before it bites you.
</details>

---

### Problem 29: Quick Stats Card

Ask the user for their **height in cm** (float) and **weight in kg** (float). Print a small "stats card" with:

- Height in meters (`cm / 100`), rounded to 2 decimals
- BMI, rounded to 1 decimal
- Height squared in meters, rounded to 3 decimals

**Sample interaction:**
```
Height (cm): 165
Weight (kg): 58
--- Stats ---
Height (m): 1.65
Height² (m²): 2.722
BMI: 21.3
```

<details>
<summary>💡 Show solution</summary>

```python
height_cm = float(input("Height (cm): "))
weight = float(input("Weight (kg): "))

height_m = height_cm / 100
height_squared = height_m ** 2
bmi = weight / height_squared

print("--- Stats ---")
print(f"Height (m): {round(height_m, 2)}")
print(f"Height² (m²): {round(height_squared, 3)}")
print(f"BMI: {round(bmi, 1)}")
```
**Teaching note:** Notice we computed `height_squared` once and reused it. We could have written `bmi = weight / (height_m ** 2)` and skipped that line — but naming the intermediate value makes the report card line easier (`Height²` reuses it). Real code constantly chooses between "shorter" and "clearer" — clearer usually wins.
</details>

---

### Problem 30: Round-Trip Math Puzzle

Ask the user for any integer `n`. Compute and print **three** things on three lines:

1. `n` doubled, then halved (with `/`) — should give `n` back, but as a float.
2. `n` squared, then square-rooted using `math.sqrt` — should give the absolute value of `n`, as a float.
3. `n` raised to the power `0` — what does this give?

**Sample interaction:**
```
n: 7
Doubled-then-halved: 7.0
Squared-then-rooted: 7.0
n to the 0: 1
```

Try it with `n = -5` too. Does line 2 still give `5.0`? Why?

<details>
<summary>💡 Show solution</summary>

```python
import math

n = int(input("n: "))

print(f"Doubled-then-halved: {(n * 2) / 2}")
print(f"Squared-then-rooted: {math.sqrt(n ** 2)}")
print(f"n to the 0: {n ** 0}")
```

**With `n = -5`:**
```
Doubled-then-halved: -5.0
Squared-then-rooted: 5.0
n to the 0: 1
```

**Why line 2 flips the sign:** `(-5) ** 2 = 25` (negative times negative = positive), and `math.sqrt(25) = 5.0`. So squaring then square-rooting acts like `abs()` — it loses the original sign. Mathematically, `√(x²) = |x|`, not `x`.

**Why anything to the power 0 is 1:** It's a math convention that makes the rules of exponents stay consistent. Python sticks to it: `5 ** 0 = 1`, `(-5) ** 0 = 1`, even `0 ** 0 = 1` (which is actually disputed in math but Python picks `1`).

**Teaching note:** Two small puzzles that show the math doesn't always *undo* the way you'd expect. Programs trip on this all the time — taking an "inverse" of an operation only works when the operation hasn't thrown information away. Squaring throws away the sign.
</details>

---

## What you practiced 🎓

- All seven arithmetic operators: `+`, `-`, `*`, `/`, `//`, `%`, `**`
- Order of operations and when to override it with parentheses
- Shortcut operators: `+=`, `-=`, `*=`, `/=`
- Built-in math helpers: `abs`, `round`, `min`, `max`
- The `math` module: `math.pi`, `math.sqrt`
- The `//` + `%` pair for splitting "total" into "whole + leftover" units
- Choosing `int()` vs `float()` based on whether the user might type a decimal
- The float surprise (`0.1 + 0.2 != 0.3`) and *why* — important to know before it bites

**Up next:** Lesson 04 exercises — strings, indexing, slicing, and methods. Words become as much fun to slice and dice as numbers.
