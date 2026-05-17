# Lesson 06: Loops - Making Your Code Repeat!

Imagine you have to write "I will practice coding" on a board 100 times. Would you rather write it out 100 times by hand, or tell someone "write this sentence 100 times"? That's exactly what **loops** (लूप — कोडचा भाग पुन्हा पुन्हा चालवणे) do -- they tell Python to **repeat** something as many times as you want!

---

## What Are Loops? Why Do We Need Them?

A **loop** is a way to repeat a block of code multiple times without rewriting it.

### Without loops (painful!):
```python
print("Hello!")
print("Hello!")
print("Hello!")
print("Hello!")
print("Hello!")
```

### With a loop (smart!):
```python
for i in range(5):
    print("Hello!")
```

**Expected Output (both versions):**
```
Hello!
Hello!
Hello!
Hello!
Hello!
```

Same result, way less typing! Now imagine if you needed to print it 1000 times -- loops make that just as easy!

**Real-life loop examples:**
- Brushing each tooth (repeat for every tooth)
- Climbing stairs (repeat: step up, step up, step up...)
- Dealing cards in a game (repeat: deal one card to each player)

Python has two types of loops: **`for` loops** (for लूप — ठराविक वेळा किंवा यादीवर फिरणारा लूप) and **`while` loops** (while लूप — अट खरी असेपर्यंत चालू राहणारा लूप).

---

## The `for` Loop with `range()`

A `for` loop is perfect when you **know how many times** you want to repeat something. The `range()` function generates a sequence of numbers.

### `range(stop)` -- Count from 0 up to (but not including) stop

```python
for i in range(5):
    print(i)
```
**Expected Output:**
```
0
1
2
3
4
```

> Notice: `range(5)` gives you 0, 1, 2, 3, 4 -- that's **5 numbers**, starting from 0. The stop number (5) is NOT included, just like string slicing!

> **Wait, why does it stop at 4?** Two reasons make this easier once you get used to it:
> 1. **It matches the count.** `range(5)` produces exactly **5 numbers**. If you write `range(100)`, you get exactly 100 numbers. The number you pass = the count of numbers you get. Super easy to predict.
> 2. **Python lists start at 0.** When you have a list with 5 items, their positions are 0, 1, 2, 3, 4 — **not** 1, 2, 3, 4, 5. So `range(5)` produces *exactly the positions of a 5-item list*. That's not an accident — it's a deliberate design choice that fits Python perfectly.
>
> If you really want 1 to 5, write `range(1, 6)` — start from 1, stop *before* 6.

```python
for i in range(3):
    print(f"Round {i + 1}: Fight!")
```
**Expected Output:**
```
Round 1: Fight!
Round 2: Fight!
Round 3: Fight!
```

### `range(start, stop)` -- Count from start up to (but not including) stop

```python
for i in range(1, 6):
    print(i)
```
**Expected Output:**
```
1
2
3
4
5
```

```python
for i in range(5, 11):
    print(f"{i} x 2 = {i * 2}")
```
**Expected Output:**
```
5 x 2 = 10
6 x 2 = 12
7 x 2 = 14
8 x 2 = 16
9 x 2 = 18
10 x 2 = 20
```

### `range(start, stop, step)` -- Count with a custom step size

```python
# Count by 2s
for i in range(0, 11, 2):
    print(i)
```
**Expected Output:**
```
0
2
4
6
8
10
```

```python
# Count by 5s
for i in range(5, 51, 5):
    print(i, end=" ")
```
**Expected Output:**
```
5 10 15 20 25 30 35 40 45 50
```

```python
# Count backwards!
for i in range(10, 0, -1):
    print(i)
print("Blast off!")
```
**Expected Output:**
```
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
Blast off!
```

```python
# Count down by 3s
for i in range(30, 0, -3):
    print(i, end=" ")
```
**Expected Output:**
```
30 27 24 21 18 15 12 9 6 3
```

---

## Looping Through Strings

A `for` loop can go through each character of a string, one at a time. This is called **iterating** (फिरवणे — लूपमधून प्रत्येक घटक एक-एक करून पाहणे) over the string.

```python
word = "Python"
for letter in word:
    print(letter)
```
**Expected Output:**
```
P
y
t
h
o
n
```

```python
# Count vowels in a word
word = "programming"
vowel_count = 0

for letter in word:
    if letter in "aeiou":
        vowel_count += 1

print(f"'{word}' has {vowel_count} vowels.")
```
**Expected Output:**
```
'programming' has 3 vowels.
```

```python
# Print each letter with its index
word = "Hello"
for i in range(len(word)):
    print(f"Index {i}: {word[i]}")
```
**Expected Output:**
```
Index 0: H
Index 1: e
Index 2: l
Index 3: l
Index 4: o
```

---

## The `while` Loop

A `while` loop keeps running **as long as a condition is True**. It's like a guard at a door who keeps asking "Is the condition still true?" -- if yes, do the code again. If no, stop.

### Basic while loop:

```python
count = 1

while count <= 5:
    print(f"Count is: {count}")
    count += 1      # Don't forget this! Otherwise the loop runs forever!

print("Done counting!")
```
**Expected Output:**
```
Count is: 1
Count is: 2
Count is: 3
Count is: 4
Count is: 5
Done counting!
```

> **DANGER! Infinite Loop!** If you forget to change the condition so it eventually becomes False, the loop will run FOREVER. Always make sure your while loop has a way to stop!

> **The Golden Rule of `while` loops:** Every `while` loop **must** contain code that eventually makes the condition `False`. If you can't point to that line, you have a bug. In the example above, `count += 1` is that line — without it, `count` would stay 1 forever and the program would never end. (If you accidentally make one, press **Ctrl+C** in the terminal to stop the program.)

```python
# Doubling a number until it exceeds 1000
number = 1

while number <= 1000:
    print(number)
    number *= 2   # Double the number each time
```
**Expected Output:**
```
1
2
4
8
16
32
64
128
256
512
1024
```
Wait -- 1024 is greater than 1000! It still printed because `number` was 512 when the condition was checked (512 <= 1000 is True), and then it was doubled to 1024 and printed. The condition is checked **before** each round.

Let's trace through it more carefully:

```python
# A countdown timer
seconds = 5

while seconds > 0:
    print(f"{seconds}...")
    seconds -= 1

print("Time's up!")
```
**Expected Output:**
```
5...
4...
3...
2...
1...
Time's up!
```

### while loop with user-like simulation:

```python
# Keep asking until the right answer is given
secret = "python"
guess = ""
attempts = 0

while guess != secret:
    # Simulating guesses
    if attempts == 0:
        guess = "html"
    elif attempts == 1:
        guess = "ruby"
    else:
        guess = "python"

    attempts += 1
    if guess != secret:
        print(f"'{guess}' is wrong. Try again!")

print(f"Correct! You guessed it in {attempts} attempts!")
```
**Expected Output:**
```
'html' is wrong. Try again!
'ruby' is wrong. Try again!
Correct! You guessed it in 3 attempts!
```

---

## When to Use `for` vs `while`

| Use `for` when... | Use `while` when... |
|---|---|
| You know how many times to loop | You don't know how many times to loop |
| You're going through a sequence | You're waiting for a condition to change |
| Counting from A to B | Repeating until something happens |

**for example:** Print numbers 1 to 10 --> Use `for`
**while example:** Keep guessing until you get it right --> Use `while`

```python
# FOR: I know I want exactly 5 stars
for i in range(5):
    print("*", end="")
print()
```
**Expected Output:**
```
*****
```

```python
# WHILE: Keep halving until we get below 1
number = 100
while number >= 1:
    print(number, end=" ")
    number /= 2
```
**Expected Output:**
```
100 50.0 25.0 12.5 6.25 3.125 1.5625
```

---

## `break` -- Escape the Loop!

The `break` (थांबवणे — लूप पूर्ण व्हायच्या आधीच बाहेर पडणे) statement is like an emergency exit. It **immediately stops** the loop, even if the condition is still True or there are more items to go through.

```python
for i in range(1, 11):
    if i == 6:
        print("Found 6! Breaking out!")
        break
    print(i)
```
**Expected Output:**
```
1
2
3
4
5
Found 6! Breaking out!
```

```python
# Search for a letter in a word
word = "programming"
search = "g"

for i in range(len(word)):
    if word[i] == search:
        print(f"Found '{search}' at index {i}!")
        break
```
**Expected Output:**
```
Found 'g' at index 3!
```

```python
# break in a while loop
number = 1
while True:    # This looks like it would run forever...
    print(number)
    number += 1
    if number > 5:
        break  # ...but break saves us!
```
**Expected Output:**
```
1
2
3
4
5
```

---

## `continue` -- Skip and Move On

The `continue` (पुढे चालू ठेवणे — सध्याची आवृत्ती सोडून लगेच पुढच्या आवृत्तीकडे जाणे) statement skips the **rest of the current round** and jumps to the next one. It's like saying "Never mind this one, next please!"

```python
for i in range(1, 11):
    if i % 3 == 0:
        continue     # Skip multiples of 3
    print(i)
```
**Expected Output:**
```
1
2
4
5
7
8
10
```

```python
# Print only consonants (skip vowels)
word = "programming"
for letter in word:
    if letter in "aeiou":
        continue
    print(letter, end="")
print()
```
**Expected Output:**
```
prgrmmng
```

```python
# Skip negative numbers when summing
numbers = [5, -3, 8, -1, 10, -7, 3]
total = 0

for num in numbers:
    if num < 0:
        continue   # Skip negative numbers
    total += num

print(f"Sum of positive numbers: {total}")
```
**Expected Output:**
```
Sum of positive numbers: 26
```

---

## Nested Loops -- Loops Inside Loops!

A **nested loop** is a loop inside another loop. The inner loop runs completely for **each** round of the outer loop.

Think of it like the hours on a clock: for each hour (outer loop), the minute hand goes around 60 times (inner loop).

### Basic nested loop:

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"({i},{j})", end=" ")
    print()   # New line after each row
```
**Expected Output:**
```
(1,1) (1,2) (1,3)
(2,1) (2,2) (2,3)
(3,1) (3,2) (3,3)
```

### Pattern Printing -- The Fun Part!

#### Right Triangle (stars)
```python
rows = 5
for i in range(1, rows + 1):
    print("*" * i)
```
**Expected Output:**
```
*
**
***
****
*****
```

#### Inverted Triangle
```python
rows = 5
for i in range(rows, 0, -1):
    print("*" * i)
```
**Expected Output:**
```
*****
****
***
**
*
```

#### Number Triangle
```python
rows = 5
for i in range(1, rows + 1):
    for j in range(1, i + 1):
        print(j, end=" ")
    print()
```
**Expected Output:**
```
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

#### Square of Stars
```python
size = 5
for i in range(size):
    print("* " * size)
```
**Expected Output:**
```
* * * * *
* * * * *
* * * * *
* * * * *
* * * * *
```

#### Hollow Square
```python
size = 5
for i in range(size):
    for j in range(size):
        if i == 0 or i == size - 1 or j == 0 or j == size - 1:
            print("*", end=" ")
        else:
            print(" ", end=" ")
    print()
```
**Expected Output:**
```
* * * * *
*       *
*       *
*       *
* * * * *
```

#### Pyramid (centered triangle)
```python
rows = 5
for i in range(1, rows + 1):
    spaces = " " * (rows - i)
    stars = "* " * i
    print(spaces + stars)
```
**Expected Output:**
```
    *
   * *
  * * *
 * * * *
* * * * *
```

#### Diamond
```python
rows = 5

# Upper half
for i in range(1, rows + 1):
    spaces = " " * (rows - i)
    stars = "* " * i
    print(spaces + stars)

# Lower half
for i in range(rows - 1, 0, -1):
    spaces = " " * (rows - i)
    stars = "* " * i
    print(spaces + stars)
```
**Expected Output:**
```
    *
   * *
  * * *
 * * * *
* * * * *
 * * * *
  * * *
   * *
    *
```

---

## Loop with `else`

Python has a unique feature: you can add an `else` block after a loop! The `else` block runs when the loop finishes **normally** (without hitting a `break`).

```python
for i in range(1, 6):
    print(i)
else:
    print("Loop completed successfully!")
```
**Expected Output:**
```
1
2
3
4
5
Loop completed successfully!
```

```python
# When break IS triggered, else does NOT run
for i in range(1, 6):
    if i == 3:
        print("Breaking!")
        break
    print(i)
else:
    print("This won't print because we used break.")
```
**Expected Output:**
```
1
2
Breaking!
```

A practical use -- searching for something:
```python
# Check if a number is prime
number = 17
is_prime = True

for i in range(2, number):
    if number % i == 0:
        print(f"{number} is NOT prime. It's divisible by {i}.")
        is_prime = False
        break
else:
    print(f"{number} IS a prime number!")
```
**Expected Output:**
```
17 IS a prime number!
```

---

## Common Loop Patterns

These are patterns you'll use over and over again. Learn them well!

### Pattern 1: Counting

```python
# Count how many even numbers are between 1 and 20
count = 0
for i in range(1, 21):
    if i % 2 == 0:
        count += 1
print(f"There are {count} even numbers between 1 and 20.")
```
**Expected Output:**
```
There are 10 even numbers between 1 and 20.
```

### Pattern 2: Summing (Accumulating)

```python
# Sum of numbers from 1 to 100
total = 0
for i in range(1, 101):
    total += i
print(f"Sum of 1 to 100 = {total}")
```
**Expected Output:**
```
Sum of 1 to 100 = 5050
```

### Pattern 3: Finding the Minimum

```python
numbers = [34, 12, 45, 7, 23, 89, 2, 56]
minimum = numbers[0]   # Start by assuming the first number is the smallest

for num in numbers:
    if num < minimum:
        minimum = num

print(f"The smallest number is: {minimum}")
```
**Expected Output:**
```
The smallest number is: 2
```

### Pattern 4: Finding the Maximum

```python
numbers = [34, 12, 45, 7, 23, 89, 2, 56]
maximum = numbers[0]

for num in numbers:
    if num > maximum:
        maximum = num

print(f"The largest number is: {maximum}")
```
**Expected Output:**
```
The largest number is: 89
```

### Pattern 5: Building a New String/List

```python
# Build a string with only uppercase letters
text = "Hello World 123"
result = ""

for char in text:
    if char.isupper():
        result += char

print(f"Uppercase letters: {result}")
```
**Expected Output:**
```
Uppercase letters: HW
```

---

## Exercises

Time to practice! Try each one on your own before peeking at the solution.

---

### Exercise 1: Multiplication Table
Print the multiplication table for a given number (1 through 10).

```
Input: 7
Output:
7 x 1 = 7
7 x 2 = 14
... (up to 10)
```

<details>
<summary>Click to see the solution</summary>

```python
number = 7

print(f"--- Multiplication Table for {number} ---")
for i in range(1, 11):
    print(f"{number} x {i} = {number * i}")
```
**Expected Output:**
```
--- Multiplication Table for 7 ---
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```
</details>

---

### Exercise 2: Star Pattern -- Right Triangle
Print a right triangle pattern with the given number of rows.

```
Rows: 5
Output:
*
**
***
****
*****
```

<details>
<summary>Click to see the solution</summary>

```python
rows = 5

for i in range(1, rows + 1):
    print("*" * i)
```
**Expected Output:**
```
*
**
***
****
*****
```
</details>

---

### Exercise 3: Number Guessing Game
The secret number is 42. Simulate guesses and tell if each guess is too high, too low, or correct.

<details>
<summary>Click to see the solution</summary>

```python
secret = 42
guesses = [25, 50, 40, 45, 42]
attempt = 0

for guess in guesses:
    attempt += 1
    print(f"Attempt {attempt}: You guessed {guess}")

    if guess < secret:
        print("  Too low! Try higher.")
    elif guess > secret:
        print("  Too high! Try lower.")
    else:
        print(f"  CORRECT! You got it in {attempt} attempts!")
        break
```
**Expected Output:**
```
Attempt 1: You guessed 25
  Too low! Try higher.
Attempt 2: You guessed 50
  Too high! Try lower.
Attempt 3: You guessed 40
  Too low! Try higher.
Attempt 4: You guessed 45
  Too high! Try lower.
Attempt 5: You guessed 42
  CORRECT! You got it in 5 attempts!
```
</details>

---

### Exercise 4: Countdown Timer
Print a countdown from 10 to 1 with a "Blast off!" at the end.

<details>
<summary>Click to see the solution</summary>

```python
for i in range(10, 0, -1):
    print(f"{i}...")

print("BLAST OFF!")
```
**Expected Output:**
```
10...
9...
8...
7...
6...
5...
4...
3...
2...
1...
BLAST OFF!
```
</details>

---

### Exercise 5: FizzBuzz
Print numbers from 1 to 30. But:
- If the number is divisible by 3, print "Fizz"
- If divisible by 5, print "Buzz"
- If divisible by both 3 and 5, print "FizzBuzz"
- Otherwise, print the number

<details>
<summary>Click to see the solution</summary>

```python
for i in range(1, 31):
    if i % 3 == 0 and i % 5 == 0:
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```
**Expected Output:**
```
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
16
17
Fizz
19
Buzz
Fizz
22
23
Fizz
Buzz
26
Fizz
28
29
FizzBuzz
```
</details>

---

### Exercise 6: Sum of Digits
Calculate the sum of all digits in a number.

```
Input: 12345
Output: 15 (because 1+2+3+4+5 = 15)
```

<details>
<summary>Click to see the solution</summary>

```python
number = 12345
digit_sum = 0

for digit in str(number):
    digit_sum += int(digit)

print(f"Sum of digits in {number} = {digit_sum}")
```
**Expected Output:**
```
Sum of digits in 12345 = 15
```
</details>

---

### Exercise 7: Factorial Calculator
Calculate the factorial of a number. Factorial of 5 = 5 x 4 x 3 x 2 x 1 = 120.

```
Input: 5
Output: 120
```

<details>
<summary>Click to see the solution</summary>

```python
number = 5
factorial = 1

for i in range(1, number + 1):
    factorial *= i

print(f"{number}! = {factorial}")
```
**Expected Output:**
```
5! = 120
```
</details>

---

### Exercise 8: Pyramid Pattern
Print a centered pyramid with the given number of rows.

```
Rows: 5
Output:
    *
   ***
  *****
 *******
*********
```

<details>
<summary>Click to see the solution</summary>

```python
rows = 5

for i in range(1, rows + 1):
    spaces = " " * (rows - i)
    stars = "*" * (2 * i - 1)
    print(spaces + stars)
```
**Expected Output:**
```
    *
   ***
  *****
 *******
*********
```
</details>

---

### Exercise 9: Reverse a Number
Reverse the digits of a given number using a while loop.

```
Input: 12345
Output: 54321
```

<details>
<summary>Click to see the solution</summary>

```python
number = 12345
reversed_num = 0

temp = number
while temp > 0:
    digit = temp % 10           # Get the last digit
    reversed_num = reversed_num * 10 + digit  # Add it to the result
    temp = temp // 10           # Remove the last digit

print(f"Original: {number}")
print(f"Reversed: {reversed_num}")
```
**Expected Output:**
```
Original: 12345
Reversed: 54321
```
</details>

---

### Exercise 10: Prime Number Checker
Check if a given number is prime. A prime number is only divisible by 1 and itself.

```
Input: 29
Output: "29 is a prime number!"
```

<details>
<summary>Click to see the solution</summary>

```python
number = 29

if number < 2:
    print(f"{number} is not a prime number.")
else:
    is_prime = True
    for i in range(2, int(number ** 0.5) + 1):
        if number % i == 0:
            is_prime = False
            print(f"{number} is NOT a prime number. It's divisible by {i}.")
            break

    if is_prime:
        print(f"{number} is a prime number!")
```
**Expected Output:**
```
29 is a prime number!
```
</details>

---

### Exercise 11: Print All Prime Numbers from 1 to 50
Use nested loops to find and print all prime numbers between 1 and 50.

<details>
<summary>Click to see the solution</summary>

```python
print("Prime numbers from 1 to 50:")

for num in range(2, 51):
    is_prime = True
    for i in range(2, int(num ** 0.5) + 1):
        if num % i == 0:
            is_prime = False
            break
    if is_prime:
        print(num, end=" ")

print()
```
**Expected Output:**
```
Prime numbers from 1 to 50:
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47
```
</details>

---

### Exercise 12: Diamond Number Pattern
Print a diamond made of numbers.

```
Rows: 4
Output:
   1
  121
 12321
1234321
 12321
  121
   1
```

<details>
<summary>Click to see the solution</summary>

```python
rows = 4

# Upper half (including middle)
for i in range(1, rows + 1):
    spaces = " " * (rows - i)

    # Numbers going up
    nums_up = ""
    for j in range(1, i + 1):
        nums_up += str(j)

    # Numbers going down
    nums_down = ""
    for j in range(i - 1, 0, -1):
        nums_down += str(j)

    print(spaces + nums_up + nums_down)

# Lower half
for i in range(rows - 1, 0, -1):
    spaces = " " * (rows - i)

    nums_up = ""
    for j in range(1, i + 1):
        nums_up += str(j)

    nums_down = ""
    for j in range(i - 1, 0, -1):
        nums_down += str(j)

    print(spaces + nums_up + nums_down)
```
**Expected Output:**
```
   1
  121
 12321
1234321
 12321
  121
   1
```
</details>

---

### Exercise 13: Simple ATM Simulator
Simulate an ATM with a balance of $1000. Process a list of withdrawals and show the balance after each one. Stop if the balance runs out.

<details>
<summary>Click to see the solution</summary>

```python
balance = 1000
withdrawals = [200, 150, 300, 500, 100]

print(f"Starting balance: ${balance}")
print("-" * 30)

for amount in withdrawals:
    if amount > balance:
        print(f"Cannot withdraw ${amount}. Insufficient funds!")
        print(f"Current balance: ${balance}")
        break
    else:
        balance -= amount
        print(f"Withdrew: ${amount} | Remaining: ${balance}")

print("-" * 30)
print(f"Final balance: ${balance}")
```
**Expected Output:**
```
Starting balance: $1000
------------------------------
Withdrew: $200 | Remaining: $800
Withdrew: $150 | Remaining: $650
Withdrew: $300 | Remaining: $350
Cannot withdraw $500. Insufficient funds!
Current balance: $350
------------------------------
Final balance: $350
```
</details>

---

### Exercise 14: Fibonacci Sequence
Print the first N numbers of the Fibonacci sequence. Each number is the sum of the two before it: 0, 1, 1, 2, 3, 5, 8, 13, ...

```
Input: N = 10
Output: 0 1 1 2 3 5 8 13 21 34
```

<details>
<summary>Click to see the solution</summary>

```python
n = 10
a = 0
b = 1

print(f"First {n} Fibonacci numbers:")
for i in range(n):
    print(a, end=" ")
    a, b = b, a + b   # a becomes b, and b becomes a+b (the next number)

print()
```
**Expected Output:**
```
First 10 Fibonacci numbers:
0 1 1 2 3 5 8 13 21 34
```
</details>

---

### Exercise 15: Collatz Conjecture
Start with any positive number. If it's even, divide by 2. If it's odd, multiply by 3 and add 1. Repeat until you reach 1. Count the steps!

```
Input: 6
Output: 6 -> 3 -> 10 -> 5 -> 16 -> 8 -> 4 -> 2 -> 1 (8 steps)
```

<details>
<summary>Click to see the solution</summary>

```python
number = 6
steps = 0
original = number

print(number, end="")

while number != 1:
    if number % 2 == 0:
        number = number // 2
    else:
        number = number * 3 + 1
    steps += 1
    print(f" -> {number}", end="")

print(f"\nStarting from {original}, it took {steps} steps to reach 1!")
```
**Expected Output:**
```
6 -> 3 -> 10 -> 5 -> 16 -> 8 -> 4 -> 2 -> 1
Starting from 6, it took 8 steps to reach 1!
```
</details>

---

## Quick Summary

| Concept | What It Does |
|---------|-------------|
| `for i in range(n)` | Repeat n times (0 to n-1) |
| `for i in range(a, b)` | Count from a to b-1 |
| `for i in range(a, b, step)` | Count from a to b-1 with step |
| `for char in string` | Go through each character |
| `while condition` | Repeat while condition is True |
| `break` | Exit the loop immediately |
| `continue` | Skip to the next iteration |
| `for/while...else` | Run else block if loop completes without break |

---

## What's Next?

You've mastered loops -- one of the most powerful tools in programming! You can now make your code repeat, count, search, and create amazing patterns. In the next lesson, we'll explore **Lists** -- a way to store multiple pieces of data together!

Keep looping and keep learning!
