# Lesson 10: File Handling in Python

## Reading and Writing Files Like a Pro!

---

## What Are Files?

Think of **files** (फाइल — डेटा साठवलेले एकक) like notebooks or journals that your computer keeps. When you write something in a notebook, it stays there even after you close it. Files work the same way!

Without files, everything your program creates **disappears** when the program ends. It's like writing on a whiteboard that gets erased every night.

**Why do we need files?**

- **Save game scores** so players can continue later
- **Store a diary** that you can read tomorrow
- **Keep a to-do list** that doesn't vanish
- **Read data** like a list of students, a story, or quiz questions
- **Create logs** to track what happened in your program

There are many types of files, but we'll focus on **text files** (`.txt`) — files that contain readable text.

---

## Opening Files: The `open()` Function

Before you can read or write a file, you need to **open** it — just like opening a notebook before writing in it.

```python
# Basic syntax
file = open("filename.txt", "mode")
```

### File Modes — What Do You Want to Do?

> **⚠️ READ THIS FIRST — it could save your homework!**
> Mode `"w"` (write) is the most dangerous mode in this lesson. If the file already exists, **opening it in `"w"` mode instantly deletes everything inside it**, before you even start writing. There's no warning and no undo. If you want to *add* to a file without erasing it, use `"a"` (append) instead. Always double-check your mode!

| Mode | Meaning | What It Does |
|------|---------|-------------|
| `"r"` | Read | Opens file for reading (default). File must exist. |
| `"w"` | Write | Opens file for writing. **Creates new file** or **erases existing content!** |
| `"a"` | Append | Opens file for adding to the end. Creates file if it doesn't exist. |
| `"r+"` | Read + Write | Opens for both reading and writing. File must exist. |

Think of it like this:
- `"r"` = Reading a book (you can only look at it)
- `"w"` = Getting a brand new blank notebook (old stuff is gone!)
- `"a"` = Opening your notebook to the last page and continuing writing

```python
# Opening a file for reading
file = open("story.txt", "r")

# Opening a file for writing (WARNING: this erases old content!)
file = open("notes.txt", "w")

# Opening a file for appending (adds to the end)
file = open("diary.txt", "a")
```

**Important:** Always close the file when you're done!

```python
file = open("story.txt", "r")
# ... do stuff with the file ...
file.close()  # Don't forget this!
```

---

## Reading Files

Let's say we have a file called `greeting.txt` with this content:

```
Hello there!
Welcome to Python.
Have a great day!
```

> **Why are there three different methods to read a file?**
> Imagine a file with 1 million lines (real files can be huge!). If you `.read()` the whole thing at once, your computer has to load all million lines into memory — which can be slow or even crash on a small device. `.readline()` reads just one line at a time (lightweight), and `.readlines()` returns everything as a list (handy when you actually want a list). Use the smallest tool that fits the job.

### Method 1: `.read()` — Read Everything at Once

```python
# .read() grabs ALL the text from the file as one big string
file = open("greeting.txt", "r")
content = file.read()
print(content)
file.close()
```

**Output:**
```
Hello there!
Welcome to Python.
Have a great day!
```

You can also read a specific number of characters:

```python
file = open("greeting.txt", "r")
first_five = file.read(5)  # Read only 5 characters
print(first_five)           # Output: Hello
file.close()
```

### Method 2: `.readline()` — Read One Line at a Time

```python
# .readline() reads just ONE line each time you call it
file = open("greeting.txt", "r")

line1 = file.readline()
print(line1)  # Output: Hello there!\n

line2 = file.readline()
print(line2)  # Output: Welcome to Python.\n

line3 = file.readline()
print(line3)  # Output: Have a great day!\n

file.close()
```

Think of `.readline()` like a bookmark — each time you call it, it reads the next line and moves the bookmark forward.

**Tip:** `.readline()` includes the newline character `\n` at the end. To remove it:

```python
line = file.readline().strip()  # .strip() removes extra whitespace and \n
```

### Method 3: `.readlines()` — Read All Lines into a List

```python
# .readlines() gives you a LIST where each item is one line
file = open("greeting.txt", "r")
lines = file.readlines()
print(lines)
file.close()
```

**Output:**
```python
['Hello there!\n', 'Welcome to Python.\n', 'Have a great day!\n']
```

This is super handy when you want to work with each line separately:

```python
file = open("greeting.txt", "r")
lines = file.readlines()
file.close()

for i, line in enumerate(lines, 1):
    print(f"Line {i}: {line.strip()}")
```

**Output:**
```
Line 1: Hello there!
Line 2: Welcome to Python.
Line 3: Have a great day!
```

### Quick Comparison

| Method | Returns | Best For |
|--------|---------|----------|
| `.read()` | One big string | Small files, when you need all text at once |
| `.readline()` | One line (string) | Reading line by line, large files |
| `.readlines()` | List of strings | When you want all lines in a list |

---

## Writing Files

### `.write()` — Write a String to a File

```python
# "w" mode creates a new file or ERASES an existing one!
file = open("my_notes.txt", "w")
file.write("I love Python!\n")
file.write("It's so much fun!\n")
file.close()
```

**Contents of `my_notes.txt`:**
```
I love Python!
It's so much fun!
```

**Important:** `.write()` does NOT add a newline automatically. You must add `\n` yourself!

```python
# Without \n, everything sticks together
file = open("test.txt", "w")
file.write("Hello")
file.write("World")
file.close()

# Contents of test.txt: HelloWorld  (all on one line!)
```

### `.writelines()` — Write a List of Strings

```python
# .writelines() writes each item from a list to the file
lines = ["Apple\n", "Banana\n", "Cherry\n"]

file = open("fruits.txt", "w")
file.writelines(lines)
file.close()
```

**Contents of `fruits.txt`:**
```
Apple
Banana
Cherry
```

**Remember:** `.writelines()` also does NOT add newlines. You need `\n` in each string!

---

## Appending to Files

What if you want to **add** something to a file without erasing what's already there? Use `"a"` mode!

```python
# First, let's create a file
file = open("diary.txt", "w")
file.write("Day 1: Started learning Python!\n")
file.close()

# Now, let's ADD to it (not erase it!)
file = open("diary.txt", "a")
file.write("Day 2: Learned about loops!\n")
file.write("Day 3: Learned about files!\n")
file.close()

# Let's read it to see everything
file = open("diary.txt", "r")
print(file.read())
file.close()
```

**Output:**
```
Day 1: Started learning Python!
Day 2: Learned about loops!
Day 3: Learned about files!
```

The `"a"` mode is like opening your notebook to the last written page and continuing from there.

---

## The `with` Statement — The BETTER Way!

Remember how we always have to call `file.close()`? What if you forget? The file might get corrupted or locked!

The `with` statement is like having a **responsible friend** who always closes the file for you, no matter what happens.

```python
# The OLD way (you might forget to close!)
file = open("story.txt", "r")
content = file.read()
file.close()  # Easy to forget!

# The BETTER way — using "with"
with open("story.txt", "r") as file:
    content = file.read()
# File is automatically closed here! No need to call .close()
```

### Why is `with` better?

1. **You can't forget to close the file** — Python does it for you
2. **Even if an error happens**, the file still gets closed properly
3. **Less code** to write
4. **It's the professional way** — real Python developers use this

```python
# Writing with the "with" statement
with open("message.txt", "w") as file:
    file.write("This is so much cleaner!\n")
    file.write("No need to worry about closing.\n")
# File is already closed here!

# Reading with the "with" statement
with open("message.txt", "r") as file:
    content = file.read()
    print(content)
# File is already closed here!
```

**From now on, we'll always use the `with` statement!**

---

## Reading a File Line by Line

When a file is very large (imagine a book with millions of lines!), reading it all at once with `.read()` would use too much memory. Instead, read it line by line:

```python
# Method 1: Using a for loop (BEST way!)
with open("greeting.txt", "r") as file:
    for line in file:
        print(line.strip())  # .strip() removes the \n at the end
```

**Output:**
```
Hello there!
Welcome to Python.
Have a great day!
```

```python
# Method 2: Using readline() in a while loop
with open("greeting.txt", "r") as file:
    line = file.readline()
    while line:  # When there are no more lines, readline() returns ""
        print(line.strip())
        line = file.readline()
```

The `for line in file` approach is the most "Pythonic" (the most Python-like) way. Use it whenever you can!

---

## Working with CSV-Like Data

CSV stands for **Comma-Separated Values**. It's a simple way to store table-like data in a text file.

Imagine a file called `students.txt`:

```
Alice,15,A
Bob,14,B
Charlie,15,A
Diana,13,B+
```

Each line is a student, and commas separate the **name**, **age**, and **grade**.

### Reading CSV-Like Data

```python
# Reading and parsing comma-separated data
students = []

with open("students.txt", "r") as file:
    for line in file:
        line = line.strip()          # Remove the \n
        parts = line.split(",")      # Split by comma into a list

        name = parts[0]
        age = int(parts[1])
        grade = parts[2]

        students.append({
            "name": name,
            "age": age,
            "grade": grade
        })

# Now we have a list of dictionaries!
for student in students:
    print(f"{student['name']} is {student['age']} years old, Grade: {student['grade']}")
```

**Output:**
```
Alice is 15 years old, Grade: A
Bob is 14 years old, Grade: B
Charlie is 15 years old, Grade: A
Diana is 13 years old, Grade: B+
```

### Writing CSV-Like Data

```python
# Saving data in CSV format
scores = [
    ("Alice", 95),
    ("Bob", 87),
    ("Charlie", 92),
]

with open("scores.txt", "w") as file:
    # Write a header line
    file.write("Name,Score\n")

    # Write each score
    for name, score in scores:
        file.write(f"{name},{score}\n")
```

**Contents of `scores.txt`:**
```
Name,Score
Alice,95
Bob,87
Charlie,92
```

---

## Practical Example 1: A Simple Diary App

```python
# ===== MY DIGITAL DIARY =====
# This program lets you write diary entries and read them later!

def write_entry():
    """Add a new diary entry."""
    # Get today's date from the user
    date = input("Enter today's date (e.g., April 18, 2026): ")

    # Get the diary entry
    print("Write your diary entry (type 'DONE' on a new line when finished):")

    entry_lines = []
    while True:
        line = input()
        if line.upper() == "DONE":
            break
        entry_lines.append(line)

    # Join all lines into one entry
    entry = "\n".join(entry_lines)

    # Append to the diary file
    with open("my_diary.txt", "a") as file:
        file.write(f"--- {date} ---\n")
        file.write(entry + "\n")
        file.write("\n")  # Blank line between entries

    print("Your entry has been saved!\n")

def read_diary():
    """Read all diary entries."""
    try:
        with open("my_diary.txt", "r") as file:
            content = file.read()
            if content.strip() == "":
                print("Your diary is empty. Start writing!\n")
            else:
                print("\n===== MY DIARY =====")
                print(content)
                print("====================\n")
    except FileNotFoundError:
        print("No diary found yet. Write your first entry!\n")

# Main program loop
print("Welcome to My Digital Diary!")
while True:
    print("1. Write a new entry")
    print("2. Read my diary")
    print("3. Quit")

    choice = input("Choose (1/2/3): ")

    if choice == "1":
        write_entry()
    elif choice == "2":
        read_diary()
    elif choice == "3":
        print("Goodbye! Keep writing!")
        break
    else:
        print("Invalid choice. Try again.\n")
```

---

## Practical Example 2: Saving High Scores

```python
# ===== HIGH SCORE TRACKER =====
# Save and load game high scores from a file!

def load_scores():
    """Load high scores from file. Returns a list of (name, score) tuples."""
    scores = []
    try:
        with open("high_scores.txt", "r") as file:
            for line in file:
                line = line.strip()
                if line:  # Skip empty lines
                    parts = line.split(",")
                    name = parts[0]
                    score = int(parts[1])
                    scores.append((name, score))
    except FileNotFoundError:
        # No scores file yet — that's okay!
        pass
    return scores

def save_scores(scores):
    """Save high scores to file."""
    # Sort scores from highest to lowest
    scores.sort(key=lambda x: x[1], reverse=True)

    # Keep only top 5
    scores = scores[:5]

    with open("high_scores.txt", "w") as file:
        for name, score in scores:
            file.write(f"{name},{score}\n")

    return scores

def display_scores(scores):
    """Display the high score table."""
    print("\n===== HIGH SCORES =====")
    if not scores:
        print("No scores yet! Be the first!")
    else:
        for i, (name, score) in enumerate(scores, 1):
            print(f"  {i}. {name} — {score} points")
    print("========================\n")

def add_score():
    """Add a new score."""
    name = input("Enter your name: ")
    score = int(input("Enter your score: "))

    scores = load_scores()
    scores.append((name, score))
    scores = save_scores(scores)

    print(f"Score saved! Let's see where you rank...")
    display_scores(scores)

# Main program
print("Welcome to the High Score Tracker!")
while True:
    print("1. Add a score")
    print("2. View high scores")
    print("3. Quit")

    choice = input("Choose (1/2/3): ")

    if choice == "1":
        add_score()
    elif choice == "2":
        scores = load_scores()
        display_scores(scores)
    elif choice == "3":
        print("See you next time!")
        break
```

---

## Practical Example 3: Reading a Story

```python
# ===== STORY READER =====
# Reads a story from a file and displays it page by page!

def create_sample_story():
    """Create a sample story file for demonstration."""
    story = """Once upon a time, in a land of ones and zeros, there lived a young programmer named Py.
Py loved to solve puzzles and build amazing things with code.
One day, Py discovered a magical function called open().
"With this," Py said, "I can save my adventures forever!"
And so Py began writing stories, saving them in files for everyone to read.
Py wrote about loops that danced in circles.
Py wrote about lists that held treasures.
Py wrote about dictionaries that remembered everything.
And every night, Py would save the day's adventures to a file.
"Tomorrow," Py whispered, "I'll write even more."
The End."""

    with open("story.txt", "w") as file:
        file.write(story)
    print("Sample story created!\n")

def read_story_page_by_page():
    """Read a story, showing 3 lines at a time."""
    try:
        with open("story.txt", "r") as file:
            lines = file.readlines()

        print("\n===== STORY TIME =====\n")

        page = 1
        for i in range(0, len(lines), 3):  # Show 3 lines at a time
            # Get the next 3 lines (or however many are left)
            page_lines = lines[i:i+3]

            print(f"--- Page {page} ---")
            for line in page_lines:
                print(line.strip())
            print()

            # Ask user to continue (unless it's the last page)
            if i + 3 < len(lines):
                input("Press Enter to continue reading... ")

            page += 1

        print("===== THE END =====\n")

    except FileNotFoundError:
        print("Story file not found! Creating a sample story...")
        create_sample_story()

# Run the story reader
read_story_page_by_page()
```

---

## Exercises

### Exercise 1: Create and Read a File

Write a program that:
1. Asks the user for 3 of their favorite movies
2. Saves them to a file called `movies.txt` (one movie per line)
3. Reads the file and displays the movies with numbers

**Expected Output:**
```
Enter movie 1: The Lion King
Enter movie 2: Finding Nemo
Enter movie 3: Toy Story

Your Favorite Movies:
1. The Lion King
2. Finding Nemo
3. Toy Story
```

<details>
<summary>Click to see the solution</summary>

```python
# Step 1: Get movies from the user
movies = []
for i in range(1, 4):
    movie = input(f"Enter movie {i}: ")
    movies.append(movie)

# Step 2: Save to file
with open("movies.txt", "w") as file:
    for movie in movies:
        file.write(movie + "\n")

print()  # Blank line

# Step 3: Read from file and display
print("Your Favorite Movies:")
with open("movies.txt", "r") as file:
    for i, line in enumerate(file, 1):
        print(f"{i}. {line.strip()}")
```
</details>

---

### Exercise 2: Word Counter from a File

Write a program that reads a text file and counts:
- The total number of **words**
- The total number of **lines**
- The total number of **characters** (including spaces)

**Test with a file containing:**
```
Python is awesome
I love coding
Files are useful
```

**Expected Output:**
```
Word count: 9
Line count: 3
Character count: 47
```

<details>
<summary>Click to see the solution</summary>

```python
# First, let's create a test file
with open("sample_text.txt", "w") as file:
    file.write("Python is awesome\n")
    file.write("I love coding\n")
    file.write("Files are useful\n")

# Now, let's count words, lines, and characters
word_count = 0
line_count = 0
char_count = 0

with open("sample_text.txt", "r") as file:
    for line in file:
        line_count += 1                          # Count this line
        char_count += len(line.strip())          # Count characters (without \n)
        words = line.strip().split()             # Split line into words
        word_count += len(words)                 # Count the words

print(f"Word count: {word_count}")
print(f"Line count: {line_count}")
print(f"Character count: {char_count}")
```
</details>

---

### Exercise 3: To-Do List Saver

Create a to-do list program where the user can:
1. **Add** a task
2. **View** all tasks
3. **Mark a task as done** (remove it from the list)
4. **Quit** (tasks are saved to `todo.txt`)

Tasks should be loaded from `todo.txt` when the program starts.

<details>
<summary>Click to see the solution</summary>

```python
# ===== TO-DO LIST PROGRAM =====

def load_tasks():
    """Load tasks from the file."""
    tasks = []
    try:
        with open("todo.txt", "r") as file:
            for line in file:
                task = line.strip()
                if task:  # Skip empty lines
                    tasks.append(task)
    except FileNotFoundError:
        # No file yet, start with an empty list
        pass
    return tasks

def save_tasks(tasks):
    """Save all tasks to the file."""
    with open("todo.txt", "w") as file:
        for task in tasks:
            file.write(task + "\n")

def view_tasks(tasks):
    """Display all tasks."""
    if not tasks:
        print("\nYour to-do list is empty! Add some tasks.\n")
    else:
        print("\n===== TO-DO LIST =====")
        for i, task in enumerate(tasks, 1):
            print(f"  {i}. {task}")
        print("======================\n")

def add_task(tasks):
    """Add a new task."""
    task = input("Enter a new task: ")
    tasks.append(task)
    save_tasks(tasks)
    print(f"Added: '{task}'\n")

def complete_task(tasks):
    """Mark a task as done (remove it)."""
    view_tasks(tasks)
    if tasks:
        try:
            num = int(input("Enter the task number to mark as done: "))
            if 1 <= num <= len(tasks):
                removed = tasks.pop(num - 1)
                save_tasks(tasks)
                print(f"Completed: '{removed}'\n")
            else:
                print("Invalid task number.\n")
        except ValueError:
            print("Please enter a valid number.\n")

# Main program
print("Welcome to the To-Do List App!")
tasks = load_tasks()

while True:
    print("1. Add a task")
    print("2. View tasks")
    print("3. Complete a task")
    print("4. Quit")

    choice = input("Choose (1/2/3/4): ")

    if choice == "1":
        add_task(tasks)
    elif choice == "2":
        view_tasks(tasks)
    elif choice == "3":
        complete_task(tasks)
    elif choice == "4":
        save_tasks(tasks)
        print("Goodbye! Your tasks are saved.")
        break
    else:
        print("Invalid choice. Try again.\n")
```
</details>

---

### Exercise 4: Simple Log File

Write a program that works like a simple log system:
- Each time the program runs, it adds a log entry with a timestamp (just use a counter)
- The log entry includes a message from the user
- Display all previous log entries when requested

<details>
<summary>Click to see the solution</summary>

```python
# ===== SIMPLE LOG SYSTEM =====

import datetime

def get_timestamp():
    """Get the current date and time as a string."""
    # We'll use a simple approach
    now = datetime.datetime.now()
    return now.strftime("%Y-%m-%d %H:%M:%S")

def add_log_entry():
    """Add a new log entry."""
    message = input("Enter log message: ")
    timestamp = get_timestamp()

    with open("app_log.txt", "a") as file:
        file.write(f"[{timestamp}] {message}\n")

    print(f"Log entry added at {timestamp}\n")

def view_logs():
    """View all log entries."""
    try:
        with open("app_log.txt", "r") as file:
            content = file.read()
            if content.strip():
                print("\n===== LOG FILE =====")
                print(content)
                print("====================\n")
            else:
                print("Log file is empty.\n")
    except FileNotFoundError:
        print("No log file found yet.\n")

def clear_logs():
    """Clear all log entries."""
    confirm = input("Are you sure you want to clear all logs? (yes/no): ")
    if confirm.lower() == "yes":
        with open("app_log.txt", "w") as file:
            pass  # Writing nothing clears the file
        print("Logs cleared!\n")
    else:
        print("Logs not cleared.\n")

# Main program
print("===== Simple Logger =====")
while True:
    print("1. Add log entry")
    print("2. View all logs")
    print("3. Clear logs")
    print("4. Quit")

    choice = input("Choose: ")

    if choice == "1":
        add_log_entry()
    elif choice == "2":
        view_logs()
    elif choice == "3":
        clear_logs()
    elif choice == "4":
        print("Logger closed.")
        break
```
</details>

---

### Exercise 5: File Copy Tool

Write a program that copies the contents of one file to another file. Ask the user for both file names.

<details>
<summary>Click to see the solution</summary>

```python
# ===== FILE COPY TOOL =====

# First, let's create a sample file to copy
with open("original.txt", "w") as file:
    file.write("This is the original file.\n")
    file.write("It has multiple lines.\n")
    file.write("Let's copy it!\n")

# Get file names from the user
source_file = input("Enter the source file name: ")
destination_file = input("Enter the destination file name: ")

try:
    # Read the source file
    with open(source_file, "r") as source:
        content = source.read()

    # Write to the destination file
    with open(destination_file, "w") as destination:
        destination.write(content)

    print(f"\nSuccessfully copied '{source_file}' to '{destination_file}'!")

    # Verify by reading the destination
    print(f"\nContents of '{destination_file}':")
    with open(destination_file, "r") as file:
        print(file.read())

except FileNotFoundError:
    print(f"Error: '{source_file}' not found!")
```
</details>

---

### Exercise 6: Student Grade Tracker (CSV-Style)

Create a program that:
1. Lets the user enter student names and scores
2. Saves them in CSV format: `name,score`
3. Reads the file and displays the class average

<details>
<summary>Click to see the solution</summary>

```python
# ===== STUDENT GRADE TRACKER =====

def add_students():
    """Add student scores to the file."""
    print("Enter student scores (type 'done' to finish):")

    with open("grades.txt", "a") as file:
        while True:
            name = input("Student name (or 'done'): ")
            if name.lower() == "done":
                break
            score = input(f"Score for {name}: ")
            file.write(f"{name},{score}\n")

    print("Students saved!\n")

def view_grades():
    """Read and display all grades with statistics."""
    try:
        students = []

        with open("grades.txt", "r") as file:
            for line in file:
                line = line.strip()
                if line:
                    parts = line.split(",")
                    name = parts[0]
                    score = int(parts[1])
                    students.append((name, score))

        if not students:
            print("No student data found.\n")
            return

        # Display all students
        print("\n===== STUDENT GRADES =====")
        for name, score in students:
            print(f"  {name}: {score}")

        # Calculate statistics
        scores = [s for _, s in students]
        average = sum(scores) / len(scores)
        highest = max(scores)
        lowest = min(scores)

        print(f"\n  Class Average: {average:.1f}")
        print(f"  Highest Score: {highest}")
        print(f"  Lowest Score:  {lowest}")
        print(f"  Total Students: {len(students)}")
        print("==========================\n")

    except FileNotFoundError:
        print("No grades file found. Add some students first!\n")

# Main program
print("Student Grade Tracker")
while True:
    print("1. Add students")
    print("2. View grades & stats")
    print("3. Quit")

    choice = input("Choose: ")

    if choice == "1":
        add_students()
    elif choice == "2":
        view_grades()
    elif choice == "3":
        print("Goodbye!")
        break
```
</details>

---

### Exercise 7: Search in a File

Write a program that asks the user for a word, then searches a text file and shows:
- Which lines contain the word
- How many times the word appears total

<details>
<summary>Click to see the solution</summary>

```python
# ===== FILE SEARCH TOOL =====

# Create a sample file to search
with open("poem.txt", "w") as file:
    file.write("Roses are red\n")
    file.write("Violets are blue\n")
    file.write("Python is fun\n")
    file.write("And so are you\n")
    file.write("Roses bloom in spring\n")
    file.write("Birds sing a tune so blue\n")

# Ask the user for a search word
search_word = input("Enter a word to search for: ").lower()

# Search the file
found_lines = []
total_count = 0

with open("poem.txt", "r") as file:
    for line_number, line in enumerate(file, 1):
        # Count occurrences in this line (case-insensitive)
        line_lower = line.lower()
        count = line_lower.count(search_word)

        if count > 0:
            found_lines.append((line_number, line.strip()))
            total_count += count

# Display results
if found_lines:
    print(f"\nFound '{search_word}' {total_count} time(s) in {len(found_lines)} line(s):\n")
    for line_num, line_text in found_lines:
        print(f"  Line {line_num}: {line_text}")
else:
    print(f"\n'{search_word}' was not found in the file.")
```
</details>

---

### Exercise 8: Number Statistics from File

Create a file with 10 random numbers (one per line). Then write a program that reads the file and calculates: sum, average, minimum, maximum.

<details>
<summary>Click to see the solution</summary>

```python
# ===== NUMBER STATISTICS FROM FILE =====

import random

# Step 1: Create a file with random numbers
with open("numbers.txt", "w") as file:
    for _ in range(10):
        num = random.randint(1, 100)
        file.write(str(num) + "\n")
print("Created numbers.txt with 10 random numbers.\n")

# Step 2: Read the numbers and calculate statistics
numbers = []

with open("numbers.txt", "r") as file:
    for line in file:
        num = int(line.strip())
        numbers.append(num)

# Display the numbers
print("Numbers in file:", numbers)
print()

# Calculate statistics
total = sum(numbers)
average = total / len(numbers)
minimum = min(numbers)
maximum = max(numbers)

print("===== STATISTICS =====")
print(f"  Count:   {len(numbers)}")
print(f"  Sum:     {total}")
print(f"  Average: {average:.2f}")
print(f"  Minimum: {minimum}")
print(f"  Maximum: {maximum}")
print("======================")
```
</details>

---

### Exercise 9: Replace Words in a File

Write a program that reads a file, replaces all occurrences of a word with another word, and saves the result.

<details>
<summary>Click to see the solution</summary>

```python
# ===== FIND AND REPLACE IN FILE =====

# Create a sample file
with open("replace_demo.txt", "w") as file:
    file.write("I like cats. Cats are cute.\n")
    file.write("My cat is fluffy.\n")
    file.write("Cats make great pets.\n")

# Show original content
print("Original file contents:")
with open("replace_demo.txt", "r") as file:
    print(file.read())

# Get the words to find and replace
find_word = input("Word to find: ")
replace_word = input("Replace with: ")

# Read the file, replace the word, and save
with open("replace_demo.txt", "r") as file:
    content = file.read()

# Count how many replacements will be made
count = content.lower().count(find_word.lower())

# Do the replacement (case-insensitive approach)
# For simplicity, we'll do a case-sensitive replace
new_content = content.replace(find_word, replace_word)

# Save the modified content
with open("replace_demo.txt", "w") as file:
    file.write(new_content)

print(f"\nReplaced {count} occurrence(s) of '{find_word}' with '{replace_word}'.")
print("\nNew file contents:")
with open("replace_demo.txt", "r") as file:
    print(file.read())
```
</details>

---

### Exercise 10: Personal Address Book

Create an address book program that saves contacts to a file. Each contact has: name, phone, email. The user can add contacts, search by name, and list all contacts.

<details>
<summary>Click to see the solution</summary>

```python
# ===== PERSONAL ADDRESS BOOK =====

def load_contacts():
    """Load contacts from file. Returns a list of dictionaries."""
    contacts = []
    try:
        with open("address_book.txt", "r") as file:
            for line in file:
                line = line.strip()
                if line:
                    parts = line.split("|")  # Using | as separator
                    contacts.append({
                        "name": parts[0],
                        "phone": parts[1],
                        "email": parts[2]
                    })
    except FileNotFoundError:
        pass
    return contacts

def save_contacts(contacts):
    """Save all contacts to file."""
    with open("address_book.txt", "w") as file:
        for contact in contacts:
            file.write(f"{contact['name']}|{contact['phone']}|{contact['email']}\n")

def add_contact(contacts):
    """Add a new contact."""
    name = input("Name: ")
    phone = input("Phone: ")
    email = input("Email: ")

    contacts.append({"name": name, "phone": phone, "email": email})
    save_contacts(contacts)
    print(f"Contact '{name}' added!\n")

def search_contact(contacts):
    """Search for a contact by name."""
    search = input("Search for name: ").lower()

    found = [c for c in contacts if search in c["name"].lower()]

    if found:
        print(f"\nFound {len(found)} contact(s):")
        for c in found:
            print(f"  Name:  {c['name']}")
            print(f"  Phone: {c['phone']}")
            print(f"  Email: {c['email']}")
            print()
    else:
        print("No contacts found.\n")

def list_contacts(contacts):
    """Display all contacts."""
    if not contacts:
        print("Address book is empty.\n")
        return

    print("\n===== ADDRESS BOOK =====")
    for i, c in enumerate(contacts, 1):
        print(f"  {i}. {c['name']} | {c['phone']} | {c['email']}")
    print(f"\nTotal contacts: {len(contacts)}")
    print("========================\n")

# Main program
print("Personal Address Book")
contacts = load_contacts()

while True:
    print("1. Add contact")
    print("2. Search contacts")
    print("3. List all contacts")
    print("4. Quit")

    choice = input("Choose: ")

    if choice == "1":
        add_contact(contacts)
    elif choice == "2":
        search_contact(contacts)
    elif choice == "3":
        list_contacts(contacts)
    elif choice == "4":
        print("Goodbye!")
        break
    else:
        print("Invalid choice.\n")
```
</details>

---

## Summary

| Concept | What It Does |
|---------|-------------|
| `open("file", "r")` | Open a file for reading |
| `open("file", "w")` | Open a file for writing (erases old content!) |
| `open("file", "a")` | Open a file for appending (adds to end) |
| `.read()` | Read entire file as one string |
| `.readline()` | Read one line at a time |
| `.readlines()` | Read all lines into a list |
| `.write(text)` | Write text to a file |
| `.writelines(list)` | Write a list of strings to a file |
| `.close()` | Close the file (important!) |
| `with open(...) as f:` | Automatically close the file (BEST way!) |
| `.strip()` | Remove whitespace/newlines from ends of a string |
| `.split(",")` | Split a string into a list by a separator |

**Key Rules:**
1. Always use the `with` statement when working with files
2. Remember to add `\n` when writing lines
3. Use `.strip()` when reading lines to remove the `\n`
4. `"w"` mode **erases** existing content — use `"a"` to add to a file
5. Always handle `FileNotFoundError` when reading files

**You're now a File Handling Hero! You can make your programs remember things forever!**
