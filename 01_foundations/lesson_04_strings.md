# Lesson 04: Strings - Playing with Text!

Welcome to the wonderful world of **strings** (स्ट्रिंग — अवतरण चिन्हांतील अक्षरांची मालिका)! If numbers are the math side of Python, strings are the **language** side. Every time you see text on a screen -- a name, a message, a story -- that's a string in action!

---

## What Are Strings?

A **string** is simply **text data**. It's a sequence of characters -- letters, numbers, symbols, spaces -- all wrapped up together.

Think of a string like a **friendship bracelet** made of letter beads. Each bead is one character, and together they spell out something meaningful!

```python
name = "Python"
greeting = "Hello, World!"
emoji_text = "I love coding! :)"
```

Strings can hold:
- Letters: `"abcdef"`
- Numbers (as text!): `"12345"`
- Symbols: `"@#$%!"`
- Spaces: `"hello world"`
- A mix of everything: `"My age is 10!"`

> **Important:** The number `42` and the string `"42"` are NOT the same thing! One is a number you can do math with, and the other is text that just looks like a number.

```python
print(42 + 8)       # 50 (math!)
print("42" + "8")   # 428 (text joined together!)
```

**Expected Output:**
```
50
428
```

---

## Creating Strings

You can create strings using **single quotes**, **double quotes**, or **triple quotes**. They all work!

### Single Quotes
```python
message = 'Hello, Python!'
print(message)
```
**Expected Output:**
```
Hello, Python!
```

### Double Quotes
```python
message = "Hello, Python!"
print(message)
```
**Expected Output:**
```
Hello, Python!
```

### When to Use Which?

Use double quotes when your text has an apostrophe (single quote) inside:
```python
sentence = "It's a beautiful day!"
print(sentence)
```
**Expected Output:**
```
It's a beautiful day!
```

Use single quotes when your text has double quotes inside:
```python
sentence = 'She said "wow!" loudly.'
print(sentence)
```
**Expected Output:**
```
She said "wow!" loudly.
```

### Triple Quotes (for multiline strings)

When you want text that spans **multiple lines**, use triple quotes (`"""` or `'''`):

```python
poem = """Roses are red,
Violets are blue,
Python is awesome,
And so are you!"""

print(poem)
```
**Expected Output:**
```
Roses are red,
Violets are blue,
Python is awesome,
And so are you!
```

Triple quotes are super handy for poems, paragraphs, or any long text!

```python
address = '''123 Coding Street
Python City, PY 12345
Computerland'''

print(address)
```
**Expected Output:**
```
123 Coding Street
Python City, PY 12345
Computerland
```

---

## String Length: `len()`

Want to know how many characters are in a string? Use the `len()` **function** (फंक्शन — नाव दिलेला, एक काम करणारा कोडाचा गट)! It counts **every** character, including spaces and symbols.

```python
word = "Python"
print(len(word))
```
**Expected Output:**
```
6
```

```python
sentence = "I love coding!"
print(len(sentence))
```
**Expected Output:**
```
14
```

```python
# Spaces count too!
text = "a b c"
print(len(text))
```
**Expected Output:**
```
5
```

```python
# Even an empty string has a length
empty = ""
print(len(empty))
```
**Expected Output:**
```
0
```

---

## Accessing Characters with Indexing

Every character in a string has a **position number** called an **index**. Think of it like seats in a movie theater -- each seat has a number!

**Here's the catch:** Python starts counting from **0**, not 1!

```
String:  P   y   t   h   o   n
Index:   0   1   2   3   4   5
```

### Positive Indexing (counting from the left)

```python
word = "Python"
print(word[0])   # First character
print(word[1])   # Second character
print(word[5])   # Sixth (last) character
```
**Expected Output:**
```
P
y
n
```

### Negative Indexing (counting from the right)

Python also lets you count **backwards** using negative numbers! This is super useful when you want the last character.

```
String:  P    y    t    h    o    n
Index:  -6   -5   -4   -3   -2   -1
```

```python
word = "Python"
print(word[-1])   # Last character
print(word[-2])   # Second to last
print(word[-6])   # First character (same as word[0])
```
**Expected Output:**
```
n
o
P
```

Think of negative indexing like a **countdown from the end**. `-1` is always the last character, `-2` is the one before that, and so on.

```python
name = "Sachin"
print(name[0])     # S
print(name[-1])    # n
print(name[3])     # h
print(name[-3])    # h  (same character!)
```
**Expected Output:**
```
S
n
h
h
```

---

## String Slicing

Slicing lets you grab a **piece** of a string -- like cutting a slice of pizza! You specify where to start and where to stop.

### Basic Slicing: `[start:end]`

```python
word = "Python"
print(word[0:3])   # Characters from index 0 up to (but NOT including) 3
print(word[2:5])   # Characters from index 2 up to (but NOT including) 5
```
**Expected Output:**
```
Pyt
tho
```

> **Remember:** The `end` index is NOT included! Think of it as a fence -- you go up to the fence but don't cross it.

### Shortcuts in Slicing

```python
word = "Python"

# Leave out the start -- goes from the beginning
print(word[:3])    # Same as word[0:3]

# Leave out the end -- goes to the end
print(word[3:])    # Same as word[3:6]

# Leave out both -- copies the whole string!
print(word[:])     # Same as word[0:6]
```
**Expected Output:**
```
Pyt
hon
Python
```

### Slicing with Step: `[start:end:step]`

The step tells Python how many characters to skip. The default step is 1 (every character).

```python
word = "Python"

# Every other character
print(word[0:6:2])   # Start at 0, go to 6, step by 2

# Every other character (shortcut)
print(word[::2])
```
**Expected Output:**
```
Pto
Pto
```

```python
# Reverse a string with step -1!
word = "Python"
print(word[::-1])
```
**Expected Output:**
```
nohtyP
```

That's right -- `[::-1]` is a magic trick to **reverse any string**!

```python
name = "hello"
print(name[::-1])    # olleh

numbers = "12345"
print(numbers[::-1]) # 54321
```
**Expected Output:**
```
olleh
54321
```

---

## String Methods

Strings come with a bunch of **built-in superpowers** called **methods**. These are like tools in a toolbox -- each one does something useful to your string.

> **Important:** String methods create a NEW string. They don't change the original!

---

### `.upper()` -- Make Everything UPPERCASE

Turns all letters into capital letters.

```python
name = "python"
print(name.upper())
```
**Expected Output:**
```
PYTHON
```

```python
message = "hello world"
print(message.upper())
```
**Expected Output:**
```
HELLO WORLD
```

```python
# The original string doesn't change!
word = "quiet"
loud = word.upper()
print(word)   # Still "quiet"
print(loud)   # "QUIET"
```
**Expected Output:**
```
quiet
QUIET
```

---

### `.lower()` -- Make Everything lowercase

Turns all letters into small letters.

```python
name = "PYTHON"
print(name.lower())
```
**Expected Output:**
```
python
```

```python
shout = "STOP SHOUTING!"
print(shout.lower())
```
**Expected Output:**
```
stop shouting!
```

```python
# Great for comparing words regardless of capitalization
user_input = "YES"
if user_input.lower() == "yes":
    print("You said yes!")
```
**Expected Output:**
```
You said yes!
```

---

### `.title()` -- Capitalize The First Letter Of Each Word

Makes the string look like a book title.

```python
name = "harry potter"
print(name.title())
```
**Expected Output:**
```
Harry Potter
```

```python
sentence = "the quick brown fox"
print(sentence.title())
```
**Expected Output:**
```
The Quick Brown Fox
```

```python
full_name = "sachin tendulkar"
print(full_name.title())
```
**Expected Output:**
```
Sachin Tendulkar
```

---

### `.strip()` -- Remove Extra Spaces from Both Ends

Like trimming the edges of a photo -- removes spaces (and newlines) from the beginning and end.

```python
messy = "   hello   "
print(messy.strip())
print(len(messy))           # 11 (with spaces)
print(len(messy.strip()))   # 5 (without spaces)
```
**Expected Output:**
```
hello
11
5
```

```python
# Also removes newlines and tabs
text = "\n  welcome  \n"
print(text.strip())
```
**Expected Output:**
```
welcome
```

```python
# You can also strip specific characters
stars = "***hello***"
print(stars.strip("*"))
```
**Expected Output:**
```
hello
```

> **Tip:** There's also `.lstrip()` (left side only) and `.rstrip()` (right side only).

---

### `.replace()` -- Swap Out Parts of a String

Finds a piece of text and replaces it with something else.

```python
sentence = "I love cats"
new_sentence = sentence.replace("cats", "dogs")
print(new_sentence)
```
**Expected Output:**
```
I love dogs
```

```python
# Replace all occurrences
text = "ha ha ha"
print(text.replace("ha", "ho"))
```
**Expected Output:**
```
ho ho ho
```

```python
# Remove something by replacing with empty string
messy = "h.e.l.l.o"
clean = messy.replace(".", "")
print(clean)
```
**Expected Output:**
```
hello
```

---

### `.find()` -- Search for Text Inside a String

Returns the **index** (position) where the text is found. Returns `-1` if not found.

```python
sentence = "Hello, World!"
print(sentence.find("World"))
```
**Expected Output:**
```
7
```

```python
sentence = "Hello, World!"
print(sentence.find("Python"))
```
**Expected Output:**
```
-1
```

```python
# Find starts searching from the beginning
text = "banana"
print(text.find("a"))     # Finds the FIRST "a"
print(text.find("na"))    # Finds "na" starting at index 2
```
**Expected Output:**
```
1
2
```

---

### `.count()` -- Count How Many Times Something Appears

```python
sentence = "banana"
print(sentence.count("a"))
```
**Expected Output:**
```
3
```

```python
text = "she sells sea shells"
print(text.count("s"))
print(text.count("sh"))
print(text.count("sells"))
```
**Expected Output:**
```
5
2
1
```

```python
# Count spaces to figure out word count (roughly)
sentence = "I love to code in Python"
spaces = sentence.count(" ")
print(f"Approximately {spaces + 1} words")
```
**Expected Output:**
```
Approximately 6 words
```

---

### `.startswith()` -- Does the String Start with...?

Returns `True` or `False`.

```python
filename = "photo.jpg"
print(filename.startswith("photo"))
print(filename.startswith("video"))
```
**Expected Output:**
```
True
False
```

```python
url = "https://www.python.org"
print(url.startswith("https"))
print(url.startswith("http"))
```
**Expected Output:**
```
True
True
```

```python
greeting = "Hello there!"
print(greeting.startswith("Hello"))
print(greeting.startswith("hello"))   # Case matters!
```
**Expected Output:**
```
True
False
```

---

### `.endswith()` -- Does the String End with...?

Returns `True` or `False`.

```python
filename = "report.pdf"
print(filename.endswith(".pdf"))
print(filename.endswith(".txt"))
```
**Expected Output:**
```
True
False
```

```python
email = "student@school.edu"
print(email.endswith(".edu"))
print(email.endswith(".com"))
```
**Expected Output:**
```
True
False
```

```python
sentence = "What a great day!"
print(sentence.endswith("!"))
print(sentence.endswith("?"))
```
**Expected Output:**
```
True
False
```

---

### `.split()` -- Break a String into a List of Pieces

Splits a string wherever it finds the separator (default is spaces).

```python
sentence = "I love Python"
words = sentence.split()
print(words)
```
**Expected Output:**
```
['I', 'love', 'Python']
```

```python
# Split by comma
data = "apple,banana,cherry"
fruits = data.split(",")
print(fruits)
```
**Expected Output:**
```
['apple', 'banana', 'cherry']
```

```python
# Split by dash
date = "2026-04-18"
parts = date.split("-")
print(parts)
print(f"Year: {parts[0]}, Month: {parts[1]}, Day: {parts[2]}")
```
**Expected Output:**
```
['2026', '04', '18']
Year: 2026, Month: 04, Day: 18
```

---

### `.join()` -- Glue a List of Strings Together

The opposite of `.split()`! You call it on the **separator** string.

```python
words = ["I", "love", "Python"]
sentence = " ".join(words)
print(sentence)
```
**Expected Output:**
```
I love Python
```

```python
# Join with dashes
parts = ["2026", "04", "18"]
date = "-".join(parts)
print(date)
```
**Expected Output:**
```
2026-04-18
```

```python
# Join with nothing (squish them together)
letters = ["P", "y", "t", "h", "o", "n"]
word = "".join(letters)
print(word)
```
**Expected Output:**
```
Python
```

---

## Checking if Something Is in a String: The `in` Keyword

The `in` keyword is like asking "Is this hiding somewhere inside that string?"

```python
sentence = "I love Python programming"

print("Python" in sentence)
print("Ruby" in sentence)
print("love" in sentence)
```
**Expected Output:**
```
True
False
True
```

```python
# Use it in an if statement
food = "chocolate cake"

if "chocolate" in food:
    print("Yum! It has chocolate!")

if "vanilla" not in food:
    print("No vanilla here.")
```
**Expected Output:**
```
Yum! It has chocolate!
No vanilla here.
```

```python
# Check if a letter is a vowel
letter = "e"
if letter in "aeiou":
    print(f"{letter} is a vowel!")
```
**Expected Output:**
```
e is a vowel!
```

---

## String Repetition with `*`

You can repeat a string by multiplying it with a number!

```python
print("ha" * 3)
print("Go! " * 4)
print("-" * 30)
```
**Expected Output:**
```
hahaha
Go! Go! Go! Go!
------------------------------
```

```python
# Make a simple border
border = "=" * 20
print(border)
print("   WELCOME!   ")
print(border)
```
**Expected Output:**
```
====================
   WELCOME!
====================
```

```python
# Fun patterns
for i in range(1, 6):
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

---

## String Concatenation (Joining Strings with `+`)

You can glue strings together using the `+` sign:

```python
first = "Hello"
second = "World"
together = first + " " + second
print(together)
```
**Expected Output:**
```
Hello World
```

```python
name = "Sachin"
greeting = "Hi, " + name + "! Welcome!"
print(greeting)
```
**Expected Output:**
```
Hi, Sachin! Welcome!
```

---

## Quick Reference Table

| Method | What It Does | Example |
|--------|-------------|---------|
| `len(s)` | Length of string | `len("hello")` -> `5` |
| `s.upper()` | ALL CAPS | `"hello".upper()` -> `"HELLO"` |
| `s.lower()` | all lowercase | `"HELLO".lower()` -> `"hello"` |
| `s.title()` | Title Case | `"hello world".title()` -> `"Hello World"` |
| `s.strip()` | Remove edge spaces | `" hi ".strip()` -> `"hi"` |
| `s.replace(a,b)` | Replace a with b | `"cat".replace("c","b")` -> `"bat"` |
| `s.find(x)` | Find position of x | `"hello".find("l")` -> `2` |
| `s.count(x)` | Count x in string | `"banana".count("a")` -> `3` |
| `s.startswith(x)` | Starts with x? | `"hello".startswith("he")` -> `True` |
| `s.endswith(x)` | Ends with x? | `"hello".endswith("lo")` -> `True` |
| `s.split(x)` | Split by x | `"a-b".split("-")` -> `["a","b"]` |
| `x.join(list)` | Join list with x | `"-".join(["a","b"])` -> `"a-b"` |

---

## Exercises

Time to practice! Try these on your own first, then check the solutions below.

---

### Exercise 1: Reverse a String
Write a program that takes a word and prints it backwards.

```
Input: "hello"
Output: "olleh"
```

<details>
<summary>Click to see the solution</summary>

```python
word = "hello"
reversed_word = word[::-1]
print(reversed_word)
```
**Expected Output:**
```
olleh
```
</details>

---

### Exercise 2: Count the Vowels
Write a program that counts the number of vowels (a, e, i, o, u) in a given string.

```
Input: "Python Programming"
Output: 4
```

<details>
<summary>Click to see the solution</summary>

```python
text = "Python Programming"
count = 0

for char in text.lower():
    if char in "aeiou":
        count += 1

print(f"Number of vowels: {count}")
```
**Expected Output:**
```
Number of vowels: 4
```
</details>

---

### Exercise 3: Secret Code (Caesar Cipher)
Create a simple secret code where each letter is replaced by the next letter in the alphabet. (a->b, b->c, ... z->a)

```
Input: "hello"
Output: "ifmmp"
```

<details>
<summary>Click to see the solution</summary>

```python
message = "hello"
secret = ""

for char in message:
    if char.isalpha():
        if char == 'z':
            secret += 'a'
        elif char == 'Z':
            secret += 'A'
        else:
            secret += chr(ord(char) + 1)
    else:
        secret += char

print(f"Original: {message}")
print(f"Secret code: {secret}")
```
**Expected Output:**
```
Original: hello
Secret code: ifmmp
```
</details>

---

### Exercise 4: Palindrome Checker
Check if a word reads the same forwards and backwards (like "racecar" or "madam").

```
Input: "racecar"
Output: "racecar is a palindrome!"
```

<details>
<summary>Click to see the solution</summary>

```python
word = "racecar"

if word == word[::-1]:
    print(f"{word} is a palindrome!")
else:
    print(f"{word} is NOT a palindrome.")
```
**Expected Output:**
```
racecar is a palindrome!
```
</details>

---

### Exercise 5: Word Counter
Count the number of words in a sentence.

```
Input: "I love to code in Python every day"
Output: 8 words
```

<details>
<summary>Click to see the solution</summary>

```python
sentence = "I love to code in Python every day"
words = sentence.split()
print(f"Number of words: {len(words)}")
```
**Expected Output:**
```
Number of words: 8
```
</details>

---

### Exercise 6: Replace Spaces with Dashes
Take a sentence and replace all spaces with dashes to make a URL-like slug.

```
Input: "My Awesome Blog Post"
Output: "my-awesome-blog-post"
```

<details>
<summary>Click to see the solution</summary>

```python
title = "My Awesome Blog Post"
slug = title.lower().replace(" ", "-")
print(slug)
```
**Expected Output:**
```
my-awesome-blog-post
```
</details>

---

### Exercise 7: Initials Maker
Given a full name, print the initials (first letter of each word in uppercase).

```
Input: "sachin ramesh tendulkar"
Output: "S.R.T."
```

<details>
<summary>Click to see the solution</summary>

```python
full_name = "sachin ramesh tendulkar"
words = full_name.split()
initials = ""

for word in words:
    initials += word[0].upper() + "."

print(initials)
```
**Expected Output:**
```
S.R.T.
```
</details>

---

### Exercise 8: String Statistics
Given a string, print how many uppercase letters, lowercase letters, digits, and spaces it has.

```
Input: "Hello World 123"
```

<details>
<summary>Click to see the solution</summary>

```python
text = "Hello World 123"
upper = 0
lower = 0
digits = 0
spaces = 0

for char in text:
    if char.isupper():
        upper += 1
    elif char.islower():
        lower += 1
    elif char.isdigit():
        digits += 1
    elif char == " ":
        spaces += 1

print(f"Uppercase: {upper}")
print(f"Lowercase: {lower}")
print(f"Digits: {digits}")
print(f"Spaces: {spaces}")
```
**Expected Output:**
```
Uppercase: 2
Lowercase: 8
Digits: 3
Spaces: 2
```
</details>

---

### Exercise 9: Pig Latin Converter
Convert a word to Pig Latin: move the first letter to the end and add "ay".

```
Input: "python"
Output: "ythonpay"
```

<details>
<summary>Click to see the solution</summary>

```python
word = "python"
pig_latin = word[1:] + word[0] + "ay"
print(f"{word} -> {pig_latin}")
```
**Expected Output:**
```
python -> ythonpay
```
</details>

---

### Exercise 10: Censor a Word
Replace a specific word in a sentence with asterisks (same length as the word).

```
Input: sentence = "I think math is boring", word to censor = "boring"
Output: "I think math is ******"
```

<details>
<summary>Click to see the solution</summary>

```python
sentence = "I think math is boring"
censor_word = "boring"

replacement = "*" * len(censor_word)
censored = sentence.replace(censor_word, replacement)
print(censored)
```
**Expected Output:**
```
I think math is ******
```
</details>

---

### Exercise 11: Alternating Caps
Convert a string so that every other character is uppercase.

```
Input: "hello world"
Output: "hElLo wOrLd"
```

<details>
<summary>Click to see the solution</summary>

```python
text = "hello world"
result = ""

for i in range(len(text)):
    if i % 2 == 1:
        result += text[i].upper()
    else:
        result += text[i].lower()

print(result)
```
**Expected Output:**
```
hElLo wOrLd
```
</details>

---

### Exercise 12: Email Validator (Simple)
Check if a string looks like a basic email (has exactly one `@` and at least one `.` after the `@`).

```
Input: "student@school.com"
Output: "Valid email!"
```

<details>
<summary>Click to see the solution</summary>

```python
email = "student@school.com"

if email.count("@") == 1:
    parts = email.split("@")
    if "." in parts[1]:
        print("Valid email!")
    else:
        print("Invalid email - missing dot after @")
else:
    print("Invalid email - must have exactly one @")
```
**Expected Output:**
```
Valid email!
```
</details>

---

## What's Next?

Great job making it through strings! You now have the power to manipulate text in all sorts of creative ways. In the next lesson, we'll learn about **Conditions** -- how to make your programs make decisions!

Keep practicing and have fun with strings!
