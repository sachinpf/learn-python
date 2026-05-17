# Exercises — Lesson 01: Hello, World!

20 problems to make `print()`, strings, and escape characters feel automatic. Use **only** what you learned in Lesson 01: `print()`, single/double/triple quotes, commas inside `print`, blank `print()`, escape sequences `\n` `\t` `\\` `\"` `\'`, and comments.

**No variables yet. No `input()`. No math. No `if`. No loops.** Those start in Lesson 02 and after.

> **How to use this file:** read the problem, type your code, run it. Only click "Show solution" after you've genuinely tried. The struggle is where the learning happens.

Quick refresher *(संक्षिप्त उजळणी)*:

- `print("text")` displays text on the screen.
- A `string` (स्ट्रिंग — अवतरण चिन्हांतील अक्षरांची मालिका) is text wrapped in `"..."` or `'...'`.
- `print()` with nothing inside makes a **blank line**.
- `print("a", "b")` prints `a b` — comma adds a space.
- Escape: `\n` = new line, `\t` = tab, `\\` = backslash, `\"` = double-quote inside double-quoted string.
- Lines starting with `#` are **comments** (टिप्पणी — Python दुर्लक्षित करणारा माणसासाठीचा मजकूर) — Python ignores them. They're for humans.

---

## 🟢 Easy

### Problem 1: Hello, You

Print exactly this:

**Expected output:**
```
Hello, World!
```

<details>
<summary>💡 Show solution</summary>

```python
print("Hello, World!")
```
**Teaching note:** The classic first program. Every Python file you ever write will have at least one `print()` somewhere. Note the lowercase `print` — `Print` and `PRINT` will crash.
</details>

---

### Problem 2: Three Lines, Three Calls

Print three lines using three separate `print()` calls:

**Expected output:**
```
Line one.
Line two.
Line three.
```

<details>
<summary>💡 Show solution</summary>

```python
print("Line one.")
print("Line two.")
print("Line three.")
```
**Teaching note:** Every `print()` automatically jumps to a new line at the end. That's why three calls produce three lines without you doing anything extra.
</details>

---

### Problem 3: Two Words, One Call

Print `Hello World` (with one space between the words) using **one** `print()` call and the comma trick.

**Expected output:**
```
Hello World
```

<details>
<summary>💡 Show solution</summary>

```python
print("Hello", "World")
```
**Teaching note:** Commas inside `print()` automatically insert one space between items. Notice you didn't have to type the space yourself — Python added it.
</details>

---

### Problem 4: Mixed Strings and Numbers

Print `I am 10 years old.` using one `print()` call with three comma-separated items: a string, a number, and a string.

**Expected output:**
```
I am 10 years old.
```

<details>
<summary>💡 Show solution</summary>

```python
print("I am", 10, "years old.")
```
**Teaching note:** `print()` happily mixes strings and numbers when you separate them with commas. The number `10` doesn't need quotes because it's a number, not text.
</details>

---

### Problem 5: A Blank Line in the Middle

Print three lines, with a **blank line** between the second and third.

**Expected output:**
```
Top.
Middle.

Bottom.
```

<details>
<summary>💡 Show solution</summary>

```python
print("Top.")
print("Middle.")
print()
print("Bottom.")
```
**Teaching note:** `print()` with nothing inside the parentheses is the cleanest way to make a blank line. Useful when you want to space out sections in a long output.
</details>

---

### Problem 6: Single Quotes vs Double Quotes

Print this exact line using **single quotes** for the outer string:

**Expected output:**
```
Python is fun!
```

<details>
<summary>💡 Show solution</summary>

```python
print('Python is fun!')
```
**Teaching note:** Python doesn't care whether you use `'...'` or `"..."` — they behave identically. The choice only matters when your text itself contains a quote (see Problem 11).
</details>

---

### Problem 7: A Comment Is Not Printed

Type and run this exactly. Predict what you'll see **before** running.

```python
# print("This line is a comment.")
print("This line is real.")
```

**Expected output:**
```
This line is real.
```

<details>
<summary>💡 Show solution</summary>

**What you should see:** only `This line is real.`

**Teaching note:** A `#` at the start of a line tells Python "ignore everything after me on this line." Comments are notes for humans — Python skips them completely. Even though it has `print(...)` inside, the `#` makes Python ignore the whole line.
</details>

---

### Problem 8: Two Comments, Two Prints

Write a program with **two** comments and **two** print statements. The comments should briefly describe what each print does. Run it and confirm only the prints appear.

**Expected output (example):**
```
Hello.
Goodbye.
```

<details>
<summary>💡 Show solution</summary>

```python
# Greeting line
print("Hello.")
# Farewell line
print("Goodbye.")
```
**Teaching note:** Comments earn their keep when a future-you (or a teammate) reads the code six months later. Don't write a comment that just repeats the code — write one that explains *why* you did something, or *what* the next chunk does.
</details>

---

## 🟡 Medium

### Problem 9: New Line Inside a String

Print these two words on two lines using **one** `print()` call (no commas, no semicolons — just `\n`).

**Expected output:**
```
Up
Down
```

<details>
<summary>💡 Show solution</summary>

```python
print("Up\nDown")
```
**Teaching note:** `\n` inside a string means "start a new line here." It's two characters in your code (`\` and `n`), but Python turns it into one invisible line-break character when the string is printed.
</details>

---

### Problem 10: A Four-Line Poem

Print this 4-line poem using **one** `print()` call and `\n`.

**Expected output:**
```
Roses are red,
Violets are blue,
Python is awesome,
And so are you!
```

<details>
<summary>💡 Show solution</summary>

```python
print("Roses are red,\nViolets are blue,\nPython is awesome,\nAnd so are you!")
```
**Teaching note:** This works, but it's a bit hard to read when the line gets long. Multiple `print()` calls — or **triple quotes** (Problem 14) — are usually nicer for long blocks of text. All three approaches are valid; pick whichever is clearest.
</details>

---

### Problem 11: A Quote Inside a String

Print this exact sentence — note the double quotes inside it:

**Expected output:**
```
She said, "Hello!" and waved.
```

<details>
<summary>💡 Show solution</summary>

```python
print('She said, "Hello!" and waved.')
```
**Teaching note:** Use **single quotes outside** when your text contains **double quotes inside**. The opposite also works:

```python
print("She said, \"Hello!\" and waved.")
```
The `\"` "escapes" the inner double quotes so Python doesn't think the string has ended. Both versions produce the same output — the first reads more naturally.
</details>

---

### Problem 12: An Apostrophe Inside a String

Print this exact sentence — note the apostrophe in `It's`:

**Expected output:**
```
It's a beautiful day.
```

<details>
<summary>💡 Show solution</summary>

```python
print("It's a beautiful day.")
```
**Teaching note:** Use **double quotes outside** when your text contains **a single quote/apostrophe inside**. Trying `print('It's a beautiful day.')` will crash because Python thinks the string ended at the apostrophe in `It`.

The escape version `print('It\'s a beautiful day.')` also works, but the double-quote version is easier to read.
</details>

---

### Problem 13: Both Kinds of Quotes in One String

Print this exact sentence — it has **both** kinds of quotes inside.

**Expected output:**
```
She said, "It's amazing!"
```

<details>
<summary>💡 Show solution</summary>

```python
print("She said, \"It's amazing!\"")
```
**Or equivalently:**
```python
print('She said, "It\'s amazing!"')
```
**Teaching note:** When both quote types appear inside the string, you **must** escape at least one of them, no matter which type you pick for the outside. There's no way around it. (Until Lesson 04, when we'll meet a third option: triple quotes.)
</details>

---

### Problem 14: Triple Quotes for a Block

Use **triple quotes** to print this whole address block in one `print()` call. Don't use `\n`.

**Expected output:**
```
Sachin Fegade
Plot 42, Green Lane
Pune, 411001
```

<details>
<summary>💡 Show solution</summary>

```python
print("""Sachin Fegade
Plot 42, Green Lane
Pune, 411001""")
```
**Teaching note:** Triple-quoted strings (तीन अवतरण चिन्हे — `"""` किंवा `'''`, अनेक ओळींची स्ट्रिंग) preserve line breaks exactly as you type them. Great for poems, addresses, or any block of text where line breaks matter. Watch the closing `"""` — don't accidentally add a stray newline before it, or you'll get an empty trailing line.
</details>

---

### Problem 15: Backslash on Screen

Print this exact line — it contains a real backslash character.

**Expected output:**
```
The path is C:\Users\Sachin
```

<details>
<summary>💡 Show solution</summary>

```python
print("The path is C:\\Users\\Sachin")
```
**Teaching note:** Since `\` is the escape character, you need `\\` to print a single backslash. Try `print("C:\Users")` and see what happens — `\U` is interpreted as an escape sequence, and you'll get a strange-looking error or weird output. The double-backslash rule keeps everything predictable.
</details>

---

### Problem 16: Tab-Aligned Table

Use `\t` to print this 3-column table. Use multiple `print()` calls.

**Expected output (columns roughly aligned):**
```
Name	Age	City
Aarav	11	Pune
Diya	10	Mumbai
```

<details>
<summary>💡 Show solution</summary>

```python
print("Name\tAge\tCity")
print("Aarav\t11\tPune")
print("Diya\t10\tMumbai")
```
**Teaching note:** `\t` is a **tab character** (टॅब — मोठी रिक्त जागा देणारा वर्ण `\t`). It moves the cursor to the next "tab stop" — usually 4 or 8 spaces over. It's the easiest way to make rough columns. For perfectly aligned columns, there are fancier tools you'll meet later — but `\t` is good enough for most beginner programs.
</details>

---

## 🔴 Hard

### Problem 17: Rectangle Frame

Print a rectangle frame **5 wide and 3 tall** using `*` characters. The inside should be empty (spaces).

**Expected output:**
```
*****
*   *
*****
```

<details>
<summary>💡 Show solution</summary>

```python
print("*****")
print("*   *")
print("*****")
```
**Teaching note:** No loops or variables yet — just three direct lines. Notice the middle line has three spaces between the two stars. Counting characters carefully is a real beginner skill; it gets easier with practice.
</details>

---

### Problem 18: Right-Pointing Arrow

Print a right-pointing arrow shape.

**Expected output:**
```
*
**
***
****
***
**
*
```

<details>
<summary>💡 Show solution</summary>

```python
print("*")
print("**")
print("***")
print("****")
print("***")
print("**")
print("*")
```
**Teaching note:** Seven separate `print()` calls. Boring? Maybe. But this is the only way you can do it right now — once you learn loops in Lesson 06, you'll be able to draw the same shape in 2 lines. That contrast is the whole reason loops exist.
</details>

---

### Problem 19: ASCII Cat

Print this little cat face. Be careful with quotes and slashes.

**Expected output:**
```
 /\_/\
( o.o )
 > ^ <
```

<details>
<summary>💡 Show solution</summary>

```python
print(" /\\_/\\")
print("( o.o )")
print(" > ^ <")
```
**Teaching note:** Every `\` you want on screen must be typed as `\\`. The first line has two of them, so you need `\\` twice. The other characters (`/`, `(`, `o`, `.`, `>`, `^`, `<`, spaces) need no special treatment.

> **Watch out!** A common mistake is forgetting one `\\` and writing `"\_/"`. `\_` isn't a defined escape sequence — newer Python versions warn you about it, older ones silently let it through. Always use `\\` for a literal backslash.
</details>

---

### Problem 20: Mixed-Quote Quotation Block

Print this exact 4-line quotation, using **triple quotes** for the whole block.

**Expected output:**
```
The teacher said:
"Read the line 'Hello, World!' aloud."
We all replied:
'Hello, World!'
```

<details>
<summary>💡 Show solution</summary>

```python
print("""The teacher said:
"Read the line 'Hello, World!' aloud."
We all replied:
'Hello, World!'""")
```
**Teaching note:** Triple quotes are the lifesaver here. Inside `"""..."""`, both `'` and `"` can appear freely without escaping. Without triple quotes you'd be drowning in `\'` and `\"`. This is the third good reason to use triple quotes, alongside multi-line text (Problem 14) and docstrings (you'll meet those in Lesson 09).
</details>

---

## 🌟 Stretch

### Problem 21: Print a Diamond

Print a diamond made of stars, 5 lines tall.

**Expected output:**
```
  *
 ***
*****
 ***
  *
```

<details>
<summary>💡 Show solution</summary>

```python
print("  *")
print(" ***")
print("*****")
print(" ***")
print("  *")
```
**Teaching note:** Count the leading spaces carefully:
- `"  *"` → 2 spaces, 1 star
- `" ***"` → 1 space, 3 stars
- `"*****"` → 0 spaces, 5 stars

The top half and bottom half mirror each other. This counts-and-mirrors thinking is the foundation of every shape-drawing program you'll ever write.
</details>

---

### Problem 22: Predict the Output

Without running this, write down on paper what you think the output will be. Then run it to check.

```python
print("a", "b", "c")
print("a" "b" "c")
print("a\tb\tc")
print("a\nb\nc")
print()
print("End.")
```

<details>
<summary>💡 Show solution</summary>

**Expected output:**
```
a b c
abc
a	b	c
a
b
c

End.
```

**Teaching note:** Four sneaky details in one problem.

1. `print("a", "b", "c")` — commas insert a space → `a b c`.
2. `print("a" "b" "c")` — **no commas**! Two strings written next to each other (with no operator between) get **glued together** by Python. This is called **string concatenation by adjacency** (शेजारी जोडणी — दोन स्ट्रिंग्स शेजारी ठेवून आपोआप जोडल्या जाणे) and it surprises almost everyone. Result: `abc`.
3. `print("a\tb\tc")` — tabs between letters.
4. `print("a\nb\nc")` — newlines between letters, so each letter goes on its own line.
5. `print()` — blank line.
6. `print("End.")` — final word.

If you predicted all six right, you've really understood this lesson. If not, that's exactly why we did this exercise.
</details>

---

## What you practiced 🎓

| Tool | Where it came from |
|---|---|
| `print()` with text | Lesson 01 |
| Commas inside `print()` | Lesson 01 |
| Blank line with `print()` | Lesson 01 |
| Single, double, triple quotes | Lesson 01 |
| Escape sequences (`\n`, `\t`, `\\`, `\"`, `\'`) | Lesson 01 |
| Comments with `#` | Lesson 01 |
| Counting characters carefully (ASCII art) | Bonus |

If anything here felt shaky, revisit `01_foundations/lesson_01_hello_world.md`, then come back.

**Next:** `exercises_02_variables.md` — types, `input()`, and f-strings.
