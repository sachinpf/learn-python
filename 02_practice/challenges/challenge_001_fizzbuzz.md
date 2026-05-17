# Challenge 001: FizzBuzz 🧩

**Difficulty:** 🟢 Beginner-friendly
**Prerequisites:** Lessons 01–06 (variables, conditions, loops)
**Time:** 15–25 minutes

> **About challenges:** one puzzle per file. Try the problem first. If you're stuck, peek at Hint 1. Still stuck? Hint 2. The full solution is at the bottom — but **don't read it until you've genuinely tried.** Struggling is where the learning happens.

---

## The Problem

Write a program that prints the numbers from **1 to 20**, one per line. But:

- If a number is a multiple of **3**, print `"Fizz"` instead of the number.
- If a number is a multiple of **5**, print `"Buzz"` instead of the number.
- If a number is a multiple of **both 3 and 5**, print `"FizzBuzz"` instead of the number.

That's it. Simple to describe. Trickier to get right.

**Expected output:**

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
```

Try to write it before scrolling. Really. The fun of this puzzle dies if you peek too early.

---

## Why this puzzle is famous

FizzBuzz is one of the most well-known beginner puzzles in the world. It looks easy — and it is, once you see the trick. But it has a **classic trap** that catches almost everyone the first time. We'll talk about the trap in the "Why this matters" section at the bottom. For now: try it.

---

## 💭 Hint 1 — Gentle nudge

<details>
<summary>Click to reveal Hint 1</summary>

You need two tools from your earlier lessons:

- A **loop** *(लूप)* that counts from 1 to 20.
- A way to ask "is this number a multiple of 3?" The same trick from Lesson 05 works: the **modulus** *(भागाकाराचा शेष)* operator `%`.

Reminder:
- `n % 3 == 0` is `True` when `n` is divisible by 3.
- `n % 5 == 0` is `True` when `n` is divisible by 5.
- `range(1, 21)` gives you the numbers 1, 2, 3, ..., 20. (Remember: `range` stops **before** the second number.)

Now try again with these in mind.

</details>

---

## 💭 Hint 2 — More specific

<details>
<summary>Click to reveal Hint 2</summary>

You need **three** decisions inside your loop, not two:

1. Is it a multiple of both 3 and 5? → print `"FizzBuzz"`
2. Is it a multiple of 3 only? → print `"Fizz"`
3. Is it a multiple of 5 only? → print `"Buzz"`
4. Otherwise → print the number itself.

The **order matters!** If you check "multiple of 3" first, then `15` will print `"Fizz"` — never reaching the FizzBuzz check.

Sketch the structure first (without finishing the code):

```python
for n in range(1, 21):
    if ...:
        print("FizzBuzz")
    elif ...:
        print("Fizz")
    elif ...:
        print("Buzz")
    else:
        print(...)
```

Fill in the `...` parts. You're closer than you think.

</details>

---

## 💭 Hint 3 — Almost the answer

<details>
<summary>Click to reveal Hint 3</summary>

The condition for "multiple of both 3 and 5" is:

```python
if n % 3 == 0 and n % 5 == 0:
```

Once that branch is checked **first**, the rest is just two more checks. The whole program is about 9 lines including the `for` loop.

One more nudge: when you `print(n)`, Python prints the number directly — you don't need `str(n)` or `f"{n}"`. `print` handles numbers fine.

If you're really stuck after this, the solution is below. But try **one more time** first.

</details>

---

## ✅ Solution

<details>
<summary>Click to reveal the full solution</summary>

```python
for n in range(1, 21):
    if n % 3 == 0 and n % 5 == 0:
        print("FizzBuzz")
    elif n % 3 == 0:
        print("Fizz")
    elif n % 5 == 0:
        print("Buzz")
    else:
        print(n)
```

**Walk-through:**

1. `range(1, 21)` produces the numbers 1 through 20. (Lesson 06 reminder: the second number is the **stop**, not the last value.)
2. For each `n`, Python checks the conditions **in order, top to bottom**, and runs **only the first one** that's `True`.
3. The `and` in the first condition is what makes `15` print `"FizzBuzz"`. Both halves must be `True`.
4. If none of the conditions match, the `else` prints the number itself.

**Trace through n = 15 to convince yourself:**

| Check | Result |
|---|---|
| `15 % 3 == 0 and 15 % 5 == 0` | `True and True` → `True` ✅ — print `"FizzBuzz"` and skip the rest |

**Trace through n = 9:**

| Check | Result |
|---|---|
| `9 % 3 == 0 and 9 % 5 == 0` | `True and False` → `False` ❌ |
| `9 % 3 == 0` | `True` ✅ — print `"Fizz"` and skip the rest |

**Trace through n = 7:**

| Check | Result |
|---|---|
| `7 % 3 == 0 and 7 % 5 == 0` | `False` ❌ |
| `7 % 3 == 0` | `False` ❌ |
| `7 % 5 == 0` | `False` ❌ |
| `else` | ✅ — print `7` |

That's the whole puzzle.

</details>

---

## 🤔 The trap (and why this puzzle is interview-famous)

<details>
<summary>Click to reveal — read AFTER you've solved it</summary>

The most common wrong first attempt looks like this:

```python
for n in range(1, 21):
    if n % 3 == 0:
        print("Fizz")
    elif n % 5 == 0:
        print("Buzz")
    elif n % 3 == 0 and n % 5 == 0:
        print("FizzBuzz")
    else:
        print(n)
```

It looks correct! It reads correct! But it's **wrong**. Run it and you'll see `"Fizz"` where `"FizzBuzz"` should be — and `"FizzBuzz"` will **never** appear.

**Why?** When `n = 15`:

- `15 % 3 == 0` is `True` → Python prints `"Fizz"` and **stops checking the rest**.
- The `elif n % 3 == 0 and n % 5 == 0` branch is never reached.

The fix is the one in the solution: put the **most specific** check (`both`) at the top, and the more general checks below.

> **Watch out!** With `if / elif / else`, only **the first matching branch** runs. Order them from **most specific to most general**, or specific cases will never get their turn.

This is the lesson FizzBuzz secretly teaches. It's why FizzBuzz is famous: it's a 30-second test that reveals whether someone has internalized this pattern. If you got the order right on your first try, you're already ahead of most beginners.

</details>

---

## 🌱 Stretch goals

If you finished the basic version, try these variants. They add up to good practice without much code.

<details>
<summary>Stretch 1: Make the range configurable</summary>

Ask the user for the upper limit instead of hardcoding `20`.

```
Enter the upper limit: 30
1
2
Fizz
...
```

```python
limit = int(input("Enter the upper limit: "))
for n in range(1, limit + 1):
    if n % 3 == 0 and n % 5 == 0:
        print("FizzBuzz")
    elif n % 3 == 0:
        print("Fizz")
    elif n % 5 == 0:
        print("Buzz")
    else:
        print(n)
```
**Note:** `limit + 1` because `range` stops *before* the second number — and you want `limit` itself included.
</details>

<details>
<summary>Stretch 2: Custom Fizz and Buzz words</summary>

Let the user pick their own words instead of `"Fizz"` and `"Buzz"`.

```
Word for multiples of 3: Apple
Word for multiples of 5: Mango
1
2
Apple
4
Mango
AppleMango
...
```

This forces you to use f-strings or concatenation for the combined case. There's more than one good way to handle it.

</details>

<details>
<summary>Stretch 3: Three-way FizzBuzzBazz</summary>

Add a third rule: multiples of 7 print `"Bazz"`. Now you have **eight** possible cases (every combination of "is/isn't multiple of 3, 5, 7"). Try to write it cleanly.

**Hint:** Build the output as a string. Start with `""`, append `"Fizz"` if divisible by 3, append `"Buzz"` if divisible by 5, append `"Bazz"` if divisible by 7. If the string is still empty at the end, print the number instead. This is a much more elegant approach than 8 nested `if`s — and it's the trick interviewers love to see.

```python
for n in range(1, 30):
    word = ""
    if n % 3 == 0:
        word += "Fizz"
    if n % 5 == 0:
        word += "Buzz"
    if n % 7 == 0:
        word += "Bazz"
    print(word if word else n)
```

Notice these are **three separate `if`s**, not `elif`s. All three can run for the same number — that's how `"FizzBuzz"` builds up automatically.

</details>

---

## 🎯 Why this matters

You just practiced three skills that show up in every program you'll ever write:

1. **Choosing the right order for `if/elif/else`** — the trap that makes FizzBuzz famous. Specific cases first; general cases later.
2. **Using `%` as a "divisibility check"** — this idea will return in dozens of problems: even/odd, leap years, time conversions, alternating row colors, you name it.
3. **Building the output incrementally** (Stretch 3) — once your problem has more than 3–4 cases, listing every combination explodes. Building the result piece by piece scales much better.

If you want a tiny experiment: try FizzBuzz with your own twist. **FizzBuzzMath**: print `"Math"` for primes, `"Buzz"` for multiples of 5, both for prime-multiples-of-5. You won't believe how quickly small variations turn into real programs.

That's the secret of programming. Most "real" programs are FizzBuzz problems wearing different hats.

---

**Next challenge suggestion:** Challenge 002 — "The Guessing Game" (uses loops, conditions, and `random`).
