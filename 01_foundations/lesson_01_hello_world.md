# Lesson 01: Hello, World! - Your First Python Program

---

## Welcome, Future Programmer!

You are about to learn something amazing. By the end of this lesson, you will have written your very first computer program. How cool is that?

Let's get started!

---

## What Is Programming?

Imagine you have a robot standing in front of you. This robot is super powerful -- it can do math, draw pictures, play music, and so much more. But there is one catch: **the robot only does what you tell it to do**, and you have to tell it in a language it understands.

**Programming** is the art of giving **instructions** (सूचना — संगणकाला सांगितलेले एक काम) to a **computer** (संगणक — माहिती हाताळणारे यंत्र), step by step, in a language it can understand.

Think of it like writing a recipe for cooking:

1. Take a bowl.
2. Add 2 cups of flour.
3. Add 1 cup of sugar.
4. Mix everything together.

If you skip a step or write something confusing, the recipe will not work. Computers are the same way -- they follow your instructions **exactly** as you write them. They will not guess what you meant!

> **Fun Fact:** A set of instructions written for a computer is called a **program** (प्रोग्राम — संगणकाला दिलेल्या सूचनांचा संच) or **code** (कोड — प्रोग्रामिंग भाषेत लिहिलेल्या सूचना).

---

## What Is Python?

**Python** (पायथन — एक सोपी प्रोग्रामिंग भाषा) is a **programming language** (प्रोग्रामिंग भाषा — संगणकाशी बोलण्याची भाषा) -- one of the many "languages" you can use to talk to a computer.

Just like people speak English, Hindi, Spanish, or French, computers can understand different programming languages. Python is one of the most popular ones!

### Why Python?

Python is one of the **best languages for beginners** because:

- It reads almost like English.
- It is simple and clean -- no confusing symbols everywhere.
- It is used by real professionals at companies like Google, Netflix, Instagram, and NASA!
- You can build games, websites, robots, and even artificial intelligence with it.

For example, printing "Hello" in Python is just:
```python
print("Hello")
```

See? Python keeps things simple!

---

## Setting Up: Opening PyCharm and Creating a New Project

**PyCharm** is a special program (called an IDE -- Integrated Development Environment) that helps you write and run Python code. Think of it as a super-powered notebook designed just for coding.

### Step 1: Open PyCharm

- Find the **PyCharm** icon on your computer and double-click it.
- If this is your first time, you might see a "Welcome" screen.

### Step 2: Create a New Project

1. On the Welcome screen, click **"New Project"**.
2. You will see a window asking where to save your project.
   - **Location:** Choose a folder on your computer. For example: `learn-python`
   - Make sure **"Python"** is selected as the language.
3. Click **"Create"**.
4. PyCharm will set everything up for you. You will now see the main PyCharm window.

> **Tip:** A "project" is just a folder where all your Python files will live together.

---

## How to Create a New Python File in PyCharm

Now that your project is open, let's create a **file** (फाइल — डेटा साठवलेले एकक) to write code in.

1. Look at the left side of PyCharm -- you will see your project folder.
2. **Right-click** on the project folder name.
3. Go to **New** -> **Python File**.
4. Type a name for your file, like `hello` (PyCharm will automatically add `.py` at the end).
5. Press **Enter**.

A new empty file called `hello.py` will open. This is where you will write your code!

> **What does `.py` mean?** The `.py` at the end tells the computer "this is a Python file." Just like `.jpg` means a picture and `.mp3` means a song, `.py` means Python code.

---

## How to Run a Python File in PyCharm

After you write code, you need to **run** (चालवणे — कोड कार्यान्वित करणे) it to see what it does. There are two easy ways:

### Method 1: The Run Button (Green Triangle)

1. Write your code in the file.
2. Look at the **top-right corner** of PyCharm -- you will see a green **Play button** (a triangle pointing right).
3. Click it!
4. Your program will run, and you will see the **output** (आउटपुट — कार्यक्रमातून बाहेर येणारी माहिती) at the **bottom of the screen** in a panel called the **"Run" window**.

### Method 2: Right-Click and Run

1. **Right-click** anywhere inside your code file.
2. In the menu that appears, click **"Run 'hello'"** (it will show the name of your file).
3. The program runs, and output appears at the bottom.

### Method 3: Keyboard Shortcut

- On **Windows/Linux:** Press `Shift + F10`
- On **Mac:** Press `Control + R`

> **Tip:** The Run window at the bottom is where Python "talks back" to you. Anything your program prints will show up there!

---

## Your First Program: Hello, World!

It is a tradition in programming that the very first program you write should print the words "Hello, World!" on the screen. Programmers have been doing this since the 1970s!

Let's do it. Type this in your Python file:

```python
print("Hello, World!")
```

Now **run** the file (click the green Play button or right-click and select Run).

**Output:**
```
Hello, World!
```

**Congratulations!** You just wrote and ran your first Python program! You are officially a **programmer** (प्रोग्रामर — कोड लिहिणारी व्यक्ती)!

---

## How `print()` Works

The `print()` **function** (फंक्शन — नाव दिलेला, एक काम करणारा कोडाचा गट) is like a **loudspeaker** for your program. Whatever you put inside the parentheses `()`, Python will display it on the screen.

```python
print("I am learning Python!")
```

**Output:**
```
I am learning Python!
```

### The Rules:

1. Always write `print` in **lowercase letters** (not Print or PRINT).
2. Use **parentheses** `()` after `print`.
3. Put the text you want to display inside **quotes** (either `"double quotes"` or `'single quotes'`).

The text inside the quotes is called a **string** (स्ट्रिंग — अवतरण चिन्हांतील अक्षरांची मालिका). A string is just a fancy word for text.

```python
print("This is a string!")
```

**Output:**
```
This is a string!
```

---

## Printing Multiple Things

You can use `print()` as many times as you want. Each `print()` creates a **new line** on the screen.

```python
print("My name is Sachin.")
print("I love Python!")
print("Coding is fun!")
```

**Output:**
```
My name is Sachin.
I love Python!
Coding is fun!
```

### Printing Multiple Items in One print()

You can also print several things in a single `print()` by separating them with **commas**:

```python
print("Hello", "World", "Python")
```

**Output:**
```
Hello World Python
```

Notice how Python automatically puts a **space** between each item when you use commas.

You can even mix text and numbers:

```python
print("I am", 10, "years old.")
```

**Output:**
```
I am 10 years old.
```

---

## Printing on Multiple Lines

### Using Multiple print() Statements

The simplest way to print on multiple lines is to use multiple `print()` calls:

```python
print("Line 1")
print("Line 2")
print("Line 3")
```

**Output:**
```
Line 1
Line 2
Line 3
```

### Using an Empty print() for a Blank Line

Want to add a blank line? Just use `print()` with nothing inside:

```python
print("Hello!")
print()
print("Goodbye!")
```

**Output:**
```
Hello!

Goodbye!
```

### Using Triple Quotes for Multi-Line Text

If you want to print a big block of text, you can use **triple quotes** (`"""` or `'''`):

```python
print("""This is line 1.
This is line 2.
This is line 3.""")
```

**Output:**
```
This is line 1.
This is line 2.
This is line 3.
```

This is super handy when you want to print something like a poem or a picture!

---

## Using Single Quotes vs Double Quotes

In Python, you can use either **single quotes** `'...'` or **double quotes** `"..."` for strings. Both work exactly the same way!

```python
print("Hello, World!")
print('Hello, World!')
```

**Output (both lines produce the same result):**
```
Hello, World!
Hello, World!
```

### When to Use Which?

The choice becomes important when your text **contains a quote inside it**:

**Problem:** What if you want to print `It's a beautiful day`?

```python
# This will cause an ERROR:
# print('It's a beautiful day')

# Solution 1: Use double quotes on the outside
print("It's a beautiful day")

# Solution 2: Use a backslash to "escape" the single quote
print('It\'s a beautiful day')
```

**Output:**
```
It's a beautiful day
It's a beautiful day
```

Similarly, if your text contains double quotes:

```python
print('She said "Hello!" to me.')
```

**Output:**
```
She said "Hello!" to me.
```

> **Tip:** Most Python programmers prefer to use **double quotes** `"..."` as a habit, but either style is perfectly fine!

---

## Escape Characters: Special Codes Inside Strings

Sometimes you need to put special things inside your text that you cannot just type normally. Python uses the **backslash** `\` followed by a letter to create these special characters. They are called **escape characters**.

### `\n` -- New Line

The `\n` character tells Python to jump to a **new line**:

```python
print("Hello\nWorld")
```

**Output:**
```
Hello
World
```

Even though it is one `print()`, the `\n` forces the text to break into two lines!

More examples:

```python
print("Line 1\nLine 2\nLine 3")
```

**Output:**
```
Line 1
Line 2
Line 3
```

### `\t` -- Tab (Indent)

The `\t` character adds a **tab space** (a big indent):

```python
print("Name\tAge\tCity")
print("Sachin\t10\tMumbai")
print("Priya\t12\tDelhi")
```

**Output:**
```
Name    Age     City
Sachin  10      Mumbai
Priya   12      Delhi
```

This makes things line up neatly, almost like a table!

### `\\` -- Printing a Backslash

Since `\` is used for escape characters, what if you actually want to print a backslash? Use **two backslashes**:

```python
print("This is a backslash: \\")
```

**Output:**
```
This is a backslash: \
```

### `\"` and `\'` -- Printing Quotes

```python
print("She said, \"Python is awesome!\"")
print('It\'s a great day!')
```

**Output:**
```
She said, "Python is awesome!"
It's a great day!
```

### Quick Reference Table

| Escape Character | What It Does         |
|-------------------|----------------------|
| `\n`             | New line             |
| `\t`             | Tab (indent)         |
| `\\`             | Backslash            |
| `\"`             | Double quote         |
| `\'`             | Single quote         |

---

## Summary

Here is everything you learned today:

| Concept                    | Example                              |
|----------------------------|--------------------------------------|
| Print text                 | `print("Hello!")`                    |
| Print multiple items       | `print("Hi", "there")`               |
| Blank line                 | `print()`                            |
| Multi-line (triple quotes) | `print("""Line1\nLine2""")`          |
| Single quotes              | `print('Hello')`                     |
| Double quotes              | `print("Hello")`                     |
| New line character         | `\n`                                 |
| Tab character              | `\t`                                 |

---

## Exercises

Try these exercises on your own! Write each one in a new Python file in PyCharm. Remember: right-click your project folder, go to New -> Python File, give it a name, write your code, and click the green Run button.

---

### Exercise 1: Print Your Name

Write a program that prints your full name.

**Example Output:**
```
Sachin Fegade
```

---

### Exercise 2: Print Three Facts About Yourself

Print three interesting facts about yourself, each on a separate line.

**Example Output:**
```
I am 10 years old.
I love playing cricket.
My favorite color is blue.
```

---

### Exercise 3: Print a Greeting Card

Create a greeting card using `print()` statements and special characters. Make it look pretty!

**Example Output:**
```
*************************
*                       *
*   Happy Birthday!     *
*   Have a great day!   *
*                       *
*************************
```

---

### Exercise 4: Print a Poem

Print your favorite short poem (or make one up!) with proper line breaks.

**Example Output:**
```
Roses are red,
Violets are blue,
Python is awesome,
And so are you!
```

---

### Exercise 5: Use Tab Characters

Print a table that shows the names, ages, and favorite foods of three friends. Use `\t` to align the columns.

**Example Output:**
```
Name    Age     Food
Rahul   11      Pizza
Sneha   10      Ice Cream
Amit    12      Biryani
```

---

### Exercise 6: Print a Star Triangle

Print a triangle shape using stars (`*`).

**Expected Output:**
```
*
**
***
****
*****
```

---

### Exercise 7: Print a Diamond

Print a diamond shape using stars.

**Expected Output:**
```
  *
 ***
*****
 ***
  *
```

---

### Exercise 8: Mix Single and Double Quotes

Write a program that prints these two sentences (pay attention to the quotes inside!):

**Expected Output:**
```
She said, "Python is fun!"
It's the best language ever!
```

---

### Exercise 9: Print a House

Draw a simple house using characters like `*`, `/`, `\`, `|`, and `_`.

**Expected Output:**
```
   /\
  /  \
 /    \
/______\
|      |
|      |
|______|
```

---

### Exercise 10: Print Your School Schedule

Print your school schedule for one day using tabs for neat columns.

**Example Output:**
```
Time        Subject         Teacher
8:00 AM     Math            Mrs. Sharma
9:00 AM     English         Mr. Patel
10:00 AM    Science         Ms. Gupta
11:00 AM    History         Mr. Singh
```

---

## Solutions

---

### Solution 1: Print Your Name

```python
print("Sachin Fegade")
```

**Output:**
```
Sachin Fegade
```

---

### Solution 2: Print Three Facts About Yourself

```python
print("I am 10 years old.")
print("I love playing cricket.")
print("My favorite color is blue.")
```

**Output:**
```
I am 10 years old.
I love playing cricket.
My favorite color is blue.
```

---

### Solution 3: Print a Greeting Card

```python
print("*************************")
print("*                       *")
print("*   Happy Birthday!     *")
print("*   Have a great day!   *")
print("*                       *")
print("*************************")
```

**Output:**
```
*************************
*                       *
*   Happy Birthday!     *
*   Have a great day!   *
*                       *
*************************
```

---

### Solution 4: Print a Poem

```python
print("Roses are red,")
print("Violets are blue,")
print("Python is awesome,")
print("And so are you!")
```

**Output:**
```
Roses are red,
Violets are blue,
Python is awesome,
And so are you!
```

**Alternative using `\n`:**

```python
print("Roses are red,\nViolets are blue,\nPython is awesome,\nAnd so are you!")
```

**Output (same as above):**
```
Roses are red,
Violets are blue,
Python is awesome,
And so are you!
```

---

### Solution 5: Use Tab Characters

```python
print("Name\tAge\tFood")
print("Rahul\t11\tPizza")
print("Sneha\t10\tIce Cream")
print("Amit\t12\tBiryani")
```

**Output:**
```
Name    Age     Food
Rahul   11      Pizza
Sneha   10      Ice Cream
Amit    12      Biryani
```

---

### Solution 6: Print a Star Triangle

```python
print("*")
print("**")
print("***")
print("****")
print("*****")
```

**Output:**
```
*
**
***
****
*****
```

---

### Solution 7: Print a Diamond

```python
print("  *")
print(" ***")
print("*****")
print(" ***")
print("  *")
```

**Output:**
```
  *
 ***
*****
 ***
  *
```

---

### Solution 8: Mix Single and Double Quotes

```python
print('She said, "Python is fun!"')
print("It's the best language ever!")
```

**Output:**
```
She said, "Python is fun!"
It's the best language ever!
```

---

### Solution 9: Print a House

```python
print("   /\\")
print("  /  \\")
print(" /    \\")
print("/______\\")
print("|      |")
print("|      |")
print("|______|")
```

**Output:**
```
   /\
  /  \
 /    \
/______\
|      |
|      |
|______|
```

> **Note:** We use `\\` to print a single backslash because `\` is an escape character!

---

### Solution 10: Print Your School Schedule

```python
print("Time\t\tSubject\t\tTeacher")
print("8:00 AM\t\tMath\t\tMrs. Sharma")
print("9:00 AM\t\tEnglish\t\tMr. Patel")
print("10:00 AM\tScience\t\tMs. Gupta")
print("11:00 AM\tHistory\t\tMr. Singh")
```

**Output:**
```
Time        Subject         Teacher
8:00 AM     Math            Mrs. Sharma
9:00 AM     English         Mr. Patel
10:00 AM    Science         Ms. Gupta
11:00 AM    History         Mr. Singh
```

---

## What's Next?

Amazing work! You have learned how to talk to your computer using Python's `print()` function. In the next lesson, we will learn about **variables** -- special containers that can store information like your name, your age, and much more!

Keep practicing, and remember: every expert programmer started exactly where you are right now!

---
