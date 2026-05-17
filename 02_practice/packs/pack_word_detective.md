# Pack 01: Word Detective 🕵️

Welcome, Detective. Your job is to investigate words — count their letters, find their secrets, decide whether two suspects are actually the same word in disguise.

This is a **themed pack** *(विषयाधारित संच)*. The problems get harder as you go, and they mix concepts from several lessons. You'll use:

- Strings & indexing *(स्ट्रिंग)* — Lesson 04
- Conditions *(अट)* — Lesson 05
- Loops *(लूप)* — Lesson 06
- Lists *(यादी)* — Lesson 07
- Dictionaries *(शब्दकोश)* — Lesson 08
- Functions *(फंक्शन)* — Lesson 09

If you haven't finished Lesson 09 yet, skip the last few problems and come back.

> **How to use this pack:** the cases get harder. Don't peek at a solution until you've genuinely tried. Even a wrong attempt teaches you something — that's how real detectives work.

---

## Case 1: The Long-Word Suspect 🟢

Some words are short. Some are long. A "long" word, you decide, is one with **more than 5 letters**.

Write a program that asks the detective for a word, then prints either `"Long word."` or `"Short word."`.

**Sample interaction:**
```
Enter a word: elephant
Long word.
```
```
Enter a word: cat
Short word.
```

<details>
<summary>💡 Show solution</summary>

```python
word = input("Enter a word: ")

if len(word) > 5:
    print("Long word.")
else:
    print("Short word.")
```
**Teaching note:** `len(word)` returns the number of characters in the string. A 5-letter word like `"apple"` will print `"Short word."` because `5 > 5` is `False`. Try `>= 5` if you want 5-letter words counted as long.
</details>

---

## Case 2: The Matching Bookends 🟢

A word has "matching bookends" if its **first letter equals its last letter** (ignoring case).

Examples: `"gag"`, `"Anna"`, `"level"` — all yes. `"hello"` — no.

Write a program that takes a word and reports `"Matching bookends!"` or `"No match."`.

**Sample interaction:**
```
Enter a word: level
Matching bookends!
```
```
Enter a word: hello
No match.
```

<details>
<summary>💡 Show solution</summary>

```python
word = input("Enter a word: ").lower()

if word[0] == word[-1]:
    print("Matching bookends!")
else:
    print("No match.")
```
**Teaching note:** `word[0]` is the first character; `word[-1]` is the last. The `-1` is a special trick — Python counts backwards from the end. We use `.lower()` so `"Anna"` and `"anna"` are treated the same. Without it, `"A" == "a"` is `False`.
</details>

---

## Case 3: The Vowel Census 🟢

Count how many vowels (`a`, `e`, `i`, `o`, `u`) are in a word. Case doesn't matter.

**Sample interaction:**
```
Enter a word: detective
Vowels: 4
```

<details>
<summary>💡 Show solution</summary>

```python
word = input("Enter a word: ").lower()
count = 0

for letter in word:
    if letter in "aeiou":
        count = count + 1

print(f"Vowels: {count}")
```
**Teaching note:** `letter in "aeiou"` is a slick trick — it checks if the letter exists inside the string `"aeiou"`. This is the same `in` you use with lists. The `count = count + 1` line is the classic "increment by one" pattern — you'll use it constantly.
</details>

---

## Case 4: The Mirror Word 🟡

Write a program that **reverses** the word the user types.

**Sample interaction:**
```
Enter a word: detective
Reversed: evitceted
```

<details>
<summary>💡 Show solution</summary>

```python
word = input("Enter a word: ")
reversed_word = word[::-1]
print(f"Reversed: {reversed_word}")
```
**Teaching note:** `word[::-1]` is slicing magic. The `::-1` means "take everything, stepping backwards by 1". You'll see it a lot in Python. If slicing feels weird, you can also build it with a loop:

```python
reversed_word = ""
for letter in word:
    reversed_word = letter + reversed_word
print(reversed_word)
```
Both work. The first is the "Pythonic" way; the second is the way most other languages do it.
</details>

---

## Case 5: The Palindrome 🟡

A **palindrome** *(पॅलिंड्रोम)* is a word that reads the same forwards and backwards. `"racecar"`, `"level"`, `"madam"`, `"noon"` — all palindromes.

Write a program that decides if a word is a palindrome. Ignore case.

**Sample interaction:**
```
Enter a word: Racecar
Palindrome!
```
```
Enter a word: detective
Not a palindrome.
```

<details>
<summary>💡 Show solution</summary>

```python
word = input("Enter a word: ").lower()

if word == word[::-1]:
    print("Palindrome!")
else:
    print("Not a palindrome.")
```
**Teaching note:** You already wrote the reverse in Case 4. Now you just compare. This is a huge idea in programming — **once you've solved a piece, you reuse it**. The `.lower()` matters: without it, `"Racecar"` (capital R) reversed is `"racecaR"`, which doesn't equal `"Racecar"`.

**Stretch:** Can you make it ignore spaces too, so `"never odd or even"` counts as a palindrome? (Hint: `word.replace(" ", "")`)
</details>

---

## Case 6: The Letter Frequency Report 🟡

For a given word, report how many times **each letter** appears. Show only the letters that actually appear.

**Sample interaction:**
```
Enter a word: banana
a: 3
b: 1
n: 2
```

<details>
<summary>💡 Show solution</summary>

```python
word = input("Enter a word: ").lower()
counts = {}

for letter in word:
    if letter in counts:
        counts[letter] = counts[letter] + 1
    else:
        counts[letter] = 1

for letter in sorted(counts):
    print(f"{letter}: {counts[letter]}")
```
**Teaching note:** This is the classic "counting things" pattern using a dictionary. You ask: "have I seen this letter before? If yes, add 1 to its count; if no, start it at 1." We use `sorted(counts)` so the output is in alphabetical order.

**Shortcut version** (once you know `.get()`):
```python
counts[letter] = counts.get(letter, 0) + 1
```
This replaces the whole `if/else`. We'll formally teach `.get()` later, but you can sneak it in if you're curious.
</details>

---

## Case 7: The Anagram Investigation 🟡

Two words are **anagrams** *(ॲनाग्राम)* if they use **exactly the same letters**, just in a different order. `"listen"` and `"silent"` — anagrams. `"detective"` and `"detected"` — not anagrams.

Write a program that takes two words and reports whether they're anagrams. Ignore case and spaces.

**Sample interaction:**
```
Enter first word: listen
Enter second word: silent
Anagrams!
```
```
Enter first word: hello
Enter second word: world
Not anagrams.
```

<details>
<summary>💡 Show solution</summary>

```python
first = input("Enter first word: ").lower().replace(" ", "")
second = input("Enter second word: ").lower().replace(" ", "")

if sorted(first) == sorted(second):
    print("Anagrams!")
else:
    print("Not anagrams.")
```
**Teaching note:** This is the **clever** solution. `sorted("listen")` returns `['e', 'i', 'l', 'n', 's', 't']`. `sorted("silent")` returns the same list. If the sorted letters match, the words are anagrams. Always.

**Why this works:** anagram = same letters, different order. Sorting both makes the order go away, so all that's left is "same letters?"

**The longer way** would be to count every letter in each word (like Case 6) and compare the dictionaries. That also works, but sorting is two lines shorter.
</details>

---

## Case 8: The Hidden Word 🟡

Sometimes one word is hidden inside another. `"cat"` is hidden inside `"concatenate"`. `"art"` is hidden inside `"start"`.

Write a program that asks for two words: a `secret` and a `text`. Report whether the `secret` is hidden anywhere inside the `text`.

**Sample interaction:**
```
Enter the secret word: cat
Enter the text: concatenate
Found 'cat' inside 'concatenate'!
```
```
Enter the secret word: dog
Enter the text: hotdog
Found 'dog' inside 'hotdog'!
```
```
Enter the secret word: fish
Enter the text: detective
'fish' is not in 'detective'.
```

<details>
<summary>💡 Show solution</summary>

```python
secret = input("Enter the secret word: ").lower()
text = input("Enter the text: ").lower()

if secret in text:
    print(f"Found '{secret}' inside '{text}'!")
else:
    print(f"'{secret}' is not in '{text}'.")
```
**Teaching note:** The `in` operator works on strings too — not just lists. `"cat" in "concatenate"` is `True` because the *substring* `cat` appears inside it. This is one of those small Python features that saves you 5 lines of code in a real project.
</details>

---

## Case 9: Caesar's Whisper 🔴

Caesar — the Roman emperor — sent secret messages by shifting every letter by 3 places. `A` became `D`, `B` became `E`, `C` became `F`, and so on. This is called a **Caesar cipher** *(सीझर सिफर — एक प्रकारचा गुप्त संदेश)*.

Write a program that takes a word and a number `shift`, then prints the encoded version. Assume lowercase letters only, and the shift wraps around (so shifting `"z"` by `1` gives `"a"`).

**Sample interaction:**
```
Enter a word: hello
Enter shift: 3
Encoded: khoor
```
```
Enter a word: zebra
Enter shift: 1
Encoded: afcsb
```

<details>
<summary>💡 Show solution</summary>

```python
word = input("Enter a word: ").lower()
shift = int(input("Enter shift: "))
encoded = ""

for letter in word:
    original_position = ord(letter) - ord("a")
    new_position = (original_position + shift) % 26
    new_letter = chr(new_position + ord("a"))
    encoded = encoded + new_letter

print(f"Encoded: {encoded}")
```
**Teaching note:** Two new ideas here:

1. `ord("a")` returns `97` — the **code number** Python uses for the letter `"a"`. `ord("b")` is `98`, and so on. So `ord(letter) - ord("a")` converts any letter into a position 0–25.
2. `chr(97)` returns `"a"` — the reverse. `chr()` takes a code number and gives back the letter.
3. `% 26` is the wrap-around trick. After `"z"` (position 25), the next position is 26 — but `26 % 26` is `0`, which is `"a"`. Magic.

This case is harder than the others because it asks you to think about letters as **numbers**. That's a real-detective move.
</details>

---

## Case 10: The Anagram Squad 🔴

Given a list of words, group them so that **anagrams stick together**.

```python
words = ["listen", "silent", "enlist", "google", "gooegl", "hello", "world", "dlrow"]
```

Expected output (the exact order of groups can vary; the contents shouldn't):
```
['listen', 'silent', 'enlist']
['google', 'gooegl']
['hello']
['world', 'dlrow']
```

<details>
<summary>💡 Show solution</summary>

```python
words = ["listen", "silent", "enlist", "google", "gooegl", "hello", "world", "dlrow"]
groups = {}

for word in words:
    key = "".join(sorted(word))
    if key in groups:
        groups[key].append(word)
    else:
        groups[key] = [word]

for group in groups.values():
    print(group)
```
**Teaching note:** The trick: **all anagrams of the same word have the same sorted-letter sequence**. So we use the sorted letters as the **key** in a dictionary. Every word that sorts to `"eilnst"` lands in the same bucket.

- `sorted(word)` gives a list like `['e', 'i', 'l', 'n', 's', 't']`.
- `"".join(...)` glues that list into the string `"eilnst"` — we need a string because lists can't be dictionary keys.

This is a real interview question, and you just solved it. Detective level: ⭐⭐⭐⭐⭐.
</details>

---

## Case 11: Build Your Own Tool 🌟 (Stretch)

You now have several word-investigation tools. Wrap them into **functions** and combine them.

Build:

```python
def is_palindrome(word): ...
def is_anagram(a, b): ...
def vowel_count(word): ...
def hidden_in(secret, text): ...
```

Then write a tiny menu program:

```
Word Detective Tool
1. Check palindrome
2. Check anagram
3. Count vowels
4. Find hidden word
5. Quit
Pick: 1
Enter a word: racecar
Palindrome!
```

<details>
<summary>💡 Show solution</summary>

```python
def is_palindrome(word):
    word = word.lower()
    return word == word[::-1]

def is_anagram(a, b):
    a = a.lower().replace(" ", "")
    b = b.lower().replace(" ", "")
    return sorted(a) == sorted(b)

def vowel_count(word):
    return sum(1 for letter in word.lower() if letter in "aeiou")

def hidden_in(secret, text):
    return secret.lower() in text.lower()


def main():
    while True:
        print("\nWord Detective Tool")
        print("1. Check palindrome")
        print("2. Check anagram")
        print("3. Count vowels")
        print("4. Find hidden word")
        print("5. Quit")
        choice = input("Pick: ")

        if choice == "1":
            word = input("Enter a word: ")
            print("Palindrome!" if is_palindrome(word) else "Not a palindrome.")
        elif choice == "2":
            a = input("First word: ")
            b = input("Second word: ")
            print("Anagrams!" if is_anagram(a, b) else "Not anagrams.")
        elif choice == "3":
            word = input("Enter a word: ")
            print(f"Vowels: {vowel_count(word)}")
        elif choice == "4":
            secret = input("Secret word: ")
            text = input("Text: ")
            print("Found!" if hidden_in(secret, text) else "Not found.")
        elif choice == "5":
            print("Goodbye, Detective.")
            break
        else:
            print("Pick 1–5.")


main()
```
**Teaching note:** Notice three new things:

1. Each `def` does **one job** — that's good function design.
2. `return ... if ... else ...` (in `is_palindrome`) is a one-line `if/else`. Cleaner when the branches are short.
3. The `sum(1 for letter in word if ...)` in `vowel_count` is a **generator expression** — a tiny loop in one line. It's a tool you'll grow into. Don't worry if it feels alien yet.

The menu loop pattern (`while True: ... if choice == "5": break`) is something you'll use in nearly every interactive program.
</details>

---

## What you practiced 🎓

| Tool you used | Where it came from |
|---|---|
| `len()`, indexing, slicing | Lesson 04 |
| `if / elif / else` | Lesson 05 |
| `for letter in word:` | Lesson 06 |
| `in` operator (substring) | Lesson 04 / 07 |
| Dictionaries for counting | Lesson 08 |
| `sorted()`, `.join()` | Lesson 07 / 04 |
| Functions, return | Lesson 09 |
| `ord()`, `chr()` (new!) | Bonus — Caesar cipher |

If anything here felt shaky, that's a signal to revisit that lesson's `exercises_NN_*.md` file before moving to the next pack.

**Next pack suggestion:** Math Wizard Pack — primes, Fibonacci, and number tricks.
