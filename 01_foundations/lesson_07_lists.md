# Lesson 07: Lists in Python

Welcome to one of the most exciting topics in Python -- **Lists**! Lists are one of the most useful tools you will ever learn. Once you understand lists, you can handle collections of data like a pro. Let's dive in!

---

## What Are Lists?

Imagine you are going to the grocery store. You write down everything you need on a **shopping list**:

```
1. Milk
2. Eggs
3. Bread
4. Butter
5. Apples
```

That is exactly what a **list** *(यादी)* is in Python -- a collection of items stored together in a specific order.

Or think about your **music playlist** on your phone. You have a bunch of songs stored in one playlist. You can add songs, remove songs, rearrange them, or skip to any song you want. A Python list works the same way!

**Key facts about lists:**
- A list can hold **multiple items** in one variable
- Items are stored in a **specific order** (first, second, third...)
- You can **change** the items (add, remove, modify)
- A list can hold **different types** of data (numbers, strings, even other lists!)
- Lists use **square brackets** `[]`

---

## Creating Lists

There are several ways to create a list in Python.

### Using Square Brackets

```python
# A list of fruits
fruits = ["apple", "banana", "cherry", "mango"]
print(fruits)
```
**Output:**
```
['apple', 'banana', 'cherry', 'mango']
```

### A List of Numbers

```python
# A list of test scores
scores = [95, 87, 92, 78, 100]
print(scores)
```
**Output:**
```
[95, 87, 92, 78, 100]
```

### A List with Mixed Data Types

```python
# A list with different types of data
mixed = ["Alice", 13, 95.5, True]
print(mixed)
```
**Output:**
```
['Alice', 13, 95.5, True]
```

### An Empty List

```python
# Creating an empty list (we can add items later)
my_list = []
print(my_list)
```
**Output:**
```
[]
```

### Using the list() Function

```python
# Converting a string to a list of characters
letters = list("hello")
print(letters)
```
**Output:**
```
['h', 'e', 'l', 'l', 'o']
```

### A List of Numbers Using range()

```python
# Creating a list of numbers from 1 to 5
numbers = list(range(1, 6))
print(numbers)
```
**Output:**
```
[1, 2, 3, 4, 5]
```

---

## Accessing Items by Index

Every item in a list has an **index** (a position number). Think of it like seats in a movie theater -- each seat has a number.

**Important:** In Python, counting starts at **0**, not 1!

```
Index:    0        1        2        3        4
List:  ["apple", "banana", "cherry", "mango", "grape"]
```

### Using Positive Indexes

```python
fruits = ["apple", "banana", "cherry", "mango", "grape"]

print(fruits[0])   # First item
print(fruits[1])   # Second item
print(fruits[2])   # Third item
print(fruits[4])   # Fifth (last) item
```
**Output:**
```
apple
banana
cherry
grape
```

### Using Negative Indexes

Negative indexes count from the **end** of the list. `-1` is the last item, `-2` is the second-to-last, and so on.

```python
fruits = ["apple", "banana", "cherry", "mango", "grape"]

print(fruits[-1])   # Last item
print(fruits[-2])   # Second to last
print(fruits[-3])   # Third to last
```
**Output:**
```
grape
mango
cherry
```

This is super handy when you want to quickly grab the last item without counting how many items are in the list!

---

## Modifying Items

Unlike some other data types, you can **change** items in a list. Lists are **mutable** *(बदलण्यायोग्य)* — meaning their contents can be modified after they're created. (Strings, for example, are *not* mutable — that's why every string method gives you a brand new string.)

Just use the index to pick which item to change.

```python
colors = ["red", "green", "blue", "yellow"]
print("Before:", colors)

# Change the second item (index 1)
colors[1] = "purple"
print("After:", colors)
```
**Output:**
```
Before: ['red', 'green', 'blue', 'yellow']
After: ['red', 'purple', 'blue', 'yellow']
```

```python
# Fix a spelling mistake in a list
animals = ["cat", "dogg", "bird"]
print("Before:", animals)

animals[1] = "dog"  # Fix the typo!
print("After:", animals)
```
**Output:**
```
Before: ['cat', 'dogg', 'bird']
After: ['cat', 'dog', 'bird']
```

---

## List Methods

Lists come with many built-in **methods** (special actions you can perform). Think of methods as superpowers that every list has!

### .append() -- Add an Item to the End

The `.append()` method adds a single item to the **end** of the list. Like adding a new song to the bottom of your playlist.

```python
pets = ["cat", "dog"]
print("Before:", pets)

pets.append("hamster")
print("After:", pets)

pets.append("goldfish")
print("After again:", pets)
```
**Output:**
```
Before: ['cat', 'dog']
After: ['cat', 'dog', 'hamster']
After again: ['cat', 'dog', 'hamster', 'goldfish']
```

```python
# Building a list from scratch
numbers = []
numbers.append(10)
numbers.append(20)
numbers.append(30)
print(numbers)
```
**Output:**
```
[10, 20, 30]
```

### .insert() -- Add an Item at a Specific Position

The `.insert()` method lets you add an item at any position you want. You give it the index where you want the new item, and everything else shifts over.

```python
fruits = ["apple", "cherry", "mango"]
print("Before:", fruits)

# Insert "banana" at index 1 (second position)
fruits.insert(1, "banana")
print("After:", fruits)
```
**Output:**
```
Before: ['apple', 'cherry', 'mango']
After: ['apple', 'banana', 'cherry', 'mango']
```

```python
# Insert at the beginning (index 0)
colors = ["green", "blue"]
colors.insert(0, "red")
print(colors)
```
**Output:**
```
['red', 'green', 'blue']
```

```python
# Insert in the middle
subjects = ["Math", "Science", "English"]
subjects.insert(2, "History")
print(subjects)
```
**Output:**
```
['Math', 'Science', 'History', 'English']
```

### .remove() -- Remove an Item by Value

The `.remove()` method removes the **first** item that matches the value you give it.

```python
fruits = ["apple", "banana", "cherry", "banana"]
print("Before:", fruits)

fruits.remove("banana")  # Removes the FIRST "banana"
print("After:", fruits)
```
**Output:**
```
Before: ['apple', 'banana', 'cherry', 'banana']
After: ['apple', 'cherry', 'banana']
```

```python
# Removing a number from a list
scores = [90, 85, 70, 95]
scores.remove(70)
print(scores)
```
**Output:**
```
[90, 85, 95]
```

**Warning:** If the item is not in the list, you will get an error!

```python
colors = ["red", "blue"]
# colors.remove("green")  # This would cause a ValueError!
```

### .pop() -- Remove and Return an Item by Index

The `.pop()` method removes an item at a given index and **gives it back to you**. If you do not give it an index, it removes the **last** item. Think of it like popping a balloon -- once it is popped, it is gone from the list, but you caught what was inside!

```python
fruits = ["apple", "banana", "cherry", "mango"]

# Pop the last item
last_fruit = fruits.pop()
print("Popped:", last_fruit)
print("List now:", fruits)
```
**Output:**
```
Popped: mango
List now: ['apple', 'banana', 'cherry']
```

```python
# Pop an item at a specific index
colors = ["red", "green", "blue", "yellow"]
removed = colors.pop(1)  # Remove item at index 1
print("Removed:", removed)
print("List now:", colors)
```
**Output:**
```
Removed: green
List now: ['red', 'blue', 'yellow']
```

```python
# Using pop() to process items one by one
tasks = ["homework", "dishes", "clean room"]
while tasks:
    current_task = tasks.pop(0)
    print(f"Doing: {current_task}")
print("All done!")
```
**Output:**
```
Doing: homework
Doing: dishes
Doing: clean room
All done!
```

### .sort() -- Sort the List

The `.sort()` method arranges items in order. Numbers go from smallest to largest, and strings go in alphabetical order.

```python
numbers = [34, 12, 89, 5, 67]
print("Before:", numbers)

numbers.sort()
print("After:", numbers)
```
**Output:**
```
Before: [34, 12, 89, 5, 67]
After: [5, 12, 34, 67, 89]
```

```python
# Sort in reverse (largest to smallest)
numbers = [34, 12, 89, 5, 67]
numbers.sort(reverse=True)
print(numbers)
```
**Output:**
```
[89, 67, 34, 12, 5]
```

```python
# Sort strings alphabetically
names = ["Charlie", "Alice", "Bob", "Diana"]
names.sort()
print(names)
```
**Output:**
```
['Alice', 'Bob', 'Charlie', 'Diana']
```

### .reverse() -- Reverse the Order

The `.reverse()` method flips the list around. The first item becomes the last, and the last becomes the first.

```python
numbers = [1, 2, 3, 4, 5]
print("Before:", numbers)

numbers.reverse()
print("After:", numbers)
```
**Output:**
```
Before: [1, 2, 3, 4, 5]
After: [5, 4, 3, 2, 1]
```

```python
# Reverse a list of words
words = ["I", "love", "Python"]
words.reverse()
print(words)
print(" ".join(words))
```
**Output:**
```
['Python', 'love', 'I']
Python love I
```

### .index() -- Find the Position of an Item

The `.index()` method tells you **where** an item is in the list (its index number).

```python
fruits = ["apple", "banana", "cherry", "mango"]

position = fruits.index("cherry")
print(f"cherry is at index {position}")
```
**Output:**
```
cherry is at index 2
```

```python
# Finding a student's position in a line
students = ["Alice", "Bob", "Charlie", "Diana"]
pos = students.index("Bob")
print(f"Bob is number {pos + 1} in line")  # +1 because index starts at 0
```
**Output:**
```
Bob is number 2 in line
```

```python
# Checking scores
scores = [85, 92, 78, 95, 88]
best_index = scores.index(95)
print(f"The score 95 is at position {best_index}")
```
**Output:**
```
The score 95 is at position 3
```

### .count() -- Count How Many Times an Item Appears

```python
numbers = [1, 3, 5, 3, 7, 3, 9]
how_many_threes = numbers.count(3)
print(f"The number 3 appears {how_many_threes} times")
```
**Output:**
```
The number 3 appears 3 times
```

```python
grades = ["A", "B", "A", "C", "A", "B"]
a_count = grades.count("A")
b_count = grades.count("B")
print(f"A grades: {a_count}")
print(f"B grades: {b_count}")
```
**Output:**
```
A grades: 3
B grades: 2
```

```python
# Count letters in a word
letters = list("mississippi")
print(f"s appears {letters.count('s')} times")
print(f"p appears {letters.count('p')} times")
```
**Output:**
```
s appears 4 times
p appears 2 times
```

### .copy() -- Make a Copy of the List

**This is one of the most important — and most surprising — things about lists. Read this slowly.**

When you write `list2 = list1`, you might *think* you made a copy. But you didn't! Both names now refer to the **same** list. It's like two nicknames for one person — if one nickname does something, the other "sees" it too.

```
Before:  list1 ──► [1, 2, 3]
              ▲
              │
         list2 ──┘   (list2 points to the same list)

After list2.append(4):
         list1 ──► [1, 2, 3, 4]   ← list1 sees the new item too!
              ▲
              │
         list2 ──┘
```

The `.copy()` method creates a **new** list with the same items — a real, independent copy.

```python
# Without copy (both change together -- not what we want!)
original = [1, 2, 3]
not_a_copy = original
not_a_copy.append(4)
print("Original:", original)      # Original changed too!
print("Not a copy:", not_a_copy)
```
**Output:**
```
Original: [1, 2, 3, 4]
Not a copy: [1, 2, 3, 4]
```

```python
# With copy (each list is independent)
original = [1, 2, 3]
real_copy = original.copy()
real_copy.append(4)
print("Original:", original)      # Original stays the same!
print("Copy:", real_copy)
```
**Output:**
```
Original: [1, 2, 3]
Copy: [1, 2, 3, 4]
```

### .clear() -- Remove All Items

The `.clear()` method empties the entire list.

```python
shopping = ["milk", "eggs", "bread", "butter"]
print("Before:", shopping)

shopping.clear()
print("After:", shopping)
```
**Output:**
```
Before: ['milk', 'eggs', 'bread', 'butter']
After: []
```

```python
# Clear and start fresh
tasks = ["homework", "chores", "reading"]
print("Tasks:", tasks)
print("All done! Clearing the list...")
tasks.clear()
print("Tasks:", tasks)
print(f"Number of tasks left: {len(tasks)}")
```
**Output:**
```
Tasks: ['homework', 'chores', 'reading']
All done! Clearing the list...
Tasks: []
Number of tasks left: 0
```

---

## List Slicing

Slicing lets you grab a **portion** of a list. Think of it like cutting a slice of pizza -- you pick the starting point and the ending point.

The syntax is: `list[start:end]`

- `start` -- where to begin (included)
- `end` -- where to stop (NOT included)

```python
numbers = [10, 20, 30, 40, 50, 60, 70]

# Get items from index 1 to 4 (not including 4)
print(numbers[1:4])

# Get the first 3 items
print(numbers[0:3])
# Or simply:
print(numbers[:3])

# Get items from index 3 to the end
print(numbers[3:])

# Get the last 3 items
print(numbers[-3:])
```
**Output:**
```
[20, 30, 40]
[10, 20, 30]
[10, 20, 30]
[40, 50, 60, 70]
[50, 60, 70]
```

### Slicing with a Step

You can also add a **step** value: `list[start:end:step]`

```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Every second item
print(numbers[::2])

# Every third item
print(numbers[::3])

# Reverse the list using slicing
print(numbers[::-1])
```
**Output:**
```
[0, 2, 4, 6, 8]
[0, 3, 6, 9]
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
```

```python
# Get even-indexed items from a portion of the list
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']
print(letters[1:7:2])  # Start at 1, end before 7, step by 2
```
**Output:**
```
['b', 'd', 'f']
```

---

## Useful Functions with Lists: len(), min(), max(), sum()

Python has some built-in functions that work great with lists.

### len() -- How Many Items?

```python
fruits = ["apple", "banana", "cherry", "mango"]
print(f"Number of fruits: {len(fruits)}")
```
**Output:**
```
Number of fruits: 4
```

### min() and max() -- Smallest and Largest

```python
scores = [78, 92, 85, 100, 67]
print(f"Highest score: {max(scores)}")
print(f"Lowest score: {min(scores)}")
```
**Output:**
```
Highest score: 100
Lowest score: 67
```

```python
# Works with strings too (alphabetical order)
names = ["Charlie", "Alice", "Bob"]
print(f"First alphabetically: {min(names)}")
print(f"Last alphabetically: {max(names)}")
```
**Output:**
```
First alphabetically: Alice
Last alphabetically: Charlie
```

### sum() -- Add All Numbers Together

```python
prices = [4.99, 2.50, 8.75, 1.25]
total = sum(prices)
print(f"Total: ${total}")
```
**Output:**
```
Total: $17.49
```

```python
# Calculate the average
scores = [85, 92, 78, 95, 88]
average = sum(scores) / len(scores)
print(f"Average score: {average}")
```
**Output:**
```
Average score: 87.6
```

---

## Looping Through Lists

Looping means going through every item in the list, one by one. This is incredibly useful!

### Using a for Loop

The simplest and most common way.

```python
fruits = ["apple", "banana", "cherry", "mango"]

for fruit in fruits:
    print(f"I like {fruit}!")
```
**Output:**
```
I like apple!
I like banana!
I like cherry!
I like mango!
```

```python
# Add up all the numbers
numbers = [10, 20, 30, 40]
total = 0
for num in numbers:
    total += num
print(f"Total: {total}")
```
**Output:**
```
Total: 100
```

### Using a while Loop

```python
colors = ["red", "green", "blue", "yellow"]
i = 0
while i < len(colors):
    print(f"Color {i + 1}: {colors[i]}")
    i += 1
```
**Output:**
```
Color 1: red
Color 2: green
Color 3: blue
Color 4: yellow
```

### Using enumerate() -- Get Index AND Value

The `enumerate()` function gives you both the **index number** and the **item** at the same time. Super useful!

```python
students = ["Alice", "Bob", "Charlie", "Diana"]

for index, name in enumerate(students):
    print(f"Student {index + 1}: {name}")
```
**Output:**
```
Student 1: Alice
Student 2: Bob
Student 3: Charlie
Student 4: Diana
```

```python
# Find the position of the highest score
scores = [85, 92, 78, 100, 88]
for i, score in enumerate(scores):
    if score == max(scores):
        print(f"Highest score {score} is at position {i + 1}")
```
**Output:**
```
Highest score 100 is at position 4
```

```python
# Number a to-do list
tasks = ["Wake up", "Brush teeth", "Eat breakfast", "Go to school"]
for number, task in enumerate(tasks, start=1):   # start counting from 1
    print(f"{number}. {task}")
```
**Output:**
```
1. Wake up
2. Brush teeth
3. Eat breakfast
4. Go to school
```

---

## List Comprehensions

List comprehensions are a **shortcut** for creating new lists. They let you write what would normally take 3-4 lines in just **one line**! They are like a mini factory that processes items.

### Basic List Comprehension

```python
# The long way
squares = []
for x in range(1, 6):
    squares.append(x ** 2)
print(squares)

# The short way (list comprehension)
squares = [x ** 2 for x in range(1, 6)]
print(squares)
```
**Output:**
```
[1, 4, 9, 16, 25]
[1, 4, 9, 16, 25]
```

### With a Condition (Filter)

```python
# Get only even numbers from 1 to 20
evens = [n for n in range(1, 21) if n % 2 == 0]
print(evens)
```
**Output:**
```
[2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```

```python
# Get words that are longer than 4 letters
words = ["hi", "hello", "hey", "wonderful", "ok", "amazing"]
long_words = [w for w in words if len(w) > 4]
print(long_words)
```
**Output:**
```
['hello', 'wonderful', 'amazing']
```

```python
# Convert all names to uppercase
names = ["alice", "bob", "charlie"]
upper_names = [name.upper() for name in names]
print(upper_names)
```
**Output:**
```
['ALICE', 'BOB', 'CHARLIE']
```

---

## Checking Membership with "in"

The `in` keyword lets you check if an item exists in a list. It returns `True` or `False`.

```python
fruits = ["apple", "banana", "cherry", "mango"]

print("banana" in fruits)
print("grape" in fruits)
```
**Output:**
```
True
False
```

```python
# Using "in" with if statements
favorite_foods = ["pizza", "ice cream", "pasta", "tacos"]

food = "pizza"
if food in favorite_foods:
    print(f"Yes! {food} is one of my favorites!")
else:
    print(f"No, {food} is not in my favorites list.")
```
**Output:**
```
Yes! pizza is one of my favorites!
```

```python
# Using "not in"
banned_words = ["hate", "stupid", "ugly"]
message = "you are amazing"

words_in_message = message.split()
is_clean = True
for word in words_in_message:
    if word in banned_words:
        is_clean = False

if is_clean:
    print("Message is clean!")
else:
    print("Message contains a banned word!")
```
**Output:**
```
Message is clean!
```

---

## Nested Lists (2D Lists / Grids)

A **nested list** is a list inside another list. Think of it like a **grid**, a **table**, or a **tic-tac-toe board**.

```python
# A 3x3 grid (like a tic-tac-toe board)
grid = [
    ["X", "O", "X"],
    ["O", "X", "O"],
    ["X", "X", "O"]
]

# Print the grid nicely
for row in grid:
    print(row)
```
**Output:**
```
['X', 'O', 'X']
['O', 'X', 'O']
['X', 'X', 'O']
```

### Accessing Items in Nested Lists

Use two indexes: `list[row][column]`

```python
grid = [
    ["X", "O", "X"],
    ["O", "X", "O"],
    ["X", "X", "O"]
]

print(grid[0][0])   # Row 0, Column 0 -> "X"
print(grid[1][2])   # Row 1, Column 2 -> "O"
print(grid[2][1])   # Row 2, Column 1 -> "X"
```
**Output:**
```
X
O
X
```

### A Classroom Seating Chart

```python
# Each inner list is a row of desks
classroom = [
    ["Alice", "Bob", "Charlie"],
    ["Diana", "Eve", "Frank"],
    ["Grace", "Henry", "Ivy"]
]

# Print the seating chart
for row_num, row in enumerate(classroom, start=1):
    print(f"Row {row_num}: {', '.join(row)}")

# Find where a student sits
print(f"\nEve sits in Row 2, Seat 2")
print(f"Checking: {classroom[1][1]}")
```
**Output:**
```
Row 1: Alice, Bob, Charlie
Row 2: Diana, Eve, Frank
Row 3: Grace, Henry, Ivy

Eve sits in Row 2, Seat 2
Checking: Eve
```

### A Multiplication Table Using Nested Lists

```python
# Create a 5x5 multiplication table
table = []
for i in range(1, 6):
    row = []
    for j in range(1, 6):
        row.append(i * j)
    table.append(row)

# Print it nicely
print("Multiplication Table:")
for row in table:
    for num in row:
        print(f"{num:4}", end="")
    print()
```
**Output:**
```
Multiplication Table:
   1   2   3   4   5
   2   4   6   8  10
   3   6   9  12  15
   4   8  12  16  20
   5  10  15  20  25
```

---

## Exercises

Try these exercises on your own first, then check the solutions below!

### Exercise 1: Find the Largest Number
Write a program that finds the largest number in a list **without using max()**.

### Exercise 2: Remove Duplicates
Write a program that removes duplicate items from a list.

### Exercise 3: Shopping List Program
Create an interactive shopping list program where the user can:
- Add items
- Remove items
- View the list
- Quit

### Exercise 4: Average Calculator
Write a program that takes a list of numbers and calculates the average.

### Exercise 5: Reverse a List Without .reverse()
Write a program that reverses a list without using the `.reverse()` method or slicing.

### Exercise 6: Count Even and Odd Numbers
Given a list of numbers, count how many are even and how many are odd.

### Exercise 7: Merge and Sort Two Lists
Take two lists of numbers, merge them into one list, and sort the result.

### Exercise 8: Find Common Items
Given two lists, find the items that appear in **both** lists.

### Exercise 9: Flatten a Nested List
Convert a nested list (2D list) into a single flat list.

### Exercise 10: Second Largest Number
Find the second largest number in a list.

### Exercise 11: Rotate a List
Write a program that rotates a list by n positions (move items from the beginning to the end).

### Exercise 12: Word Frequency Counter
Given a sentence, count how many times each word appears using a list.

---

## Solutions

### Solution 1: Find the Largest Number

```python
numbers = [34, 67, 12, 89, 45, 23, 78]

largest = numbers[0]  # Start by assuming the first number is largest
for num in numbers:
    if num > largest:
        largest = num

print(f"The largest number is: {largest}")
```
**Output:**
```
The largest number is: 89
```

### Solution 2: Remove Duplicates

```python
original = [1, 2, 3, 2, 4, 3, 5, 1, 6]
print(f"Original: {original}")

no_duplicates = []
for item in original:
    if item not in no_duplicates:
        no_duplicates.append(item)

print(f"Without duplicates: {no_duplicates}")
```
**Output:**
```
Original: [1, 2, 3, 2, 4, 3, 5, 1, 6]
Without duplicates: [1, 2, 3, 4, 5, 6]
```

### Solution 3: Shopping List Program

```python
shopping_list = []

while True:
    print("\n--- Shopping List Menu ---")
    print("1. Add item")
    print("2. Remove item")
    print("3. View list")
    print("4. Quit")

    choice = input("Choose an option (1-4): ")

    if choice == "1":
        item = input("Enter item to add: ")
        shopping_list.append(item)
        print(f"'{item}' added!")

    elif choice == "2":
        if len(shopping_list) == 0:
            print("The list is empty!")
        else:
            item = input("Enter item to remove: ")
            if item in shopping_list:
                shopping_list.remove(item)
                print(f"'{item}' removed!")
            else:
                print(f"'{item}' is not in the list.")

    elif choice == "3":
        if len(shopping_list) == 0:
            print("Your shopping list is empty.")
        else:
            print("\nYour Shopping List:")
            for i, item in enumerate(shopping_list, start=1):
                print(f"  {i}. {item}")

    elif choice == "4":
        print("Goodbye! Happy shopping!")
        break

    else:
        print("Invalid choice. Please try again.")
```

### Solution 4: Average Calculator

```python
numbers = [85, 92, 78, 95, 88, 76, 90]

total = sum(numbers)
count = len(numbers)
average = total / count

print(f"Numbers: {numbers}")
print(f"Sum: {total}")
print(f"Count: {count}")
print(f"Average: {average:.2f}")
```
**Output:**
```
Numbers: [85, 92, 78, 95, 88, 76, 90]
Sum: 604
Count: 7
Average: 86.29
```

### Solution 5: Reverse a List Without .reverse()

```python
original = [1, 2, 3, 4, 5]
print(f"Original: {original}")

reversed_list = []
for i in range(len(original) - 1, -1, -1):
    reversed_list.append(original[i])

print(f"Reversed: {reversed_list}")
```
**Output:**
```
Original: [1, 2, 3, 4, 5]
Reversed: [5, 4, 3, 2, 1]
```

### Solution 6: Count Even and Odd Numbers

```python
numbers = [12, 7, 3, 18, 25, 6, 14, 9, 21, 8]

even_count = 0
odd_count = 0

for num in numbers:
    if num % 2 == 0:
        even_count += 1
    else:
        odd_count += 1

print(f"Numbers: {numbers}")
print(f"Even numbers: {even_count}")
print(f"Odd numbers: {odd_count}")
```
**Output:**
```
Numbers: [12, 7, 3, 18, 25, 6, 14, 9, 21, 8]
Even numbers: 5
Odd numbers: 5
```

### Solution 7: Merge and Sort Two Lists

```python
list1 = [5, 3, 8, 1]
list2 = [9, 2, 7, 4]

merged = list1 + list2  # Combine the lists using +
print(f"List 1: {list1}")
print(f"List 2: {list2}")
print(f"Merged: {merged}")

merged.sort()
print(f"Sorted: {merged}")
```
**Output:**
```
List 1: [5, 3, 8, 1]
List 2: [9, 2, 7, 4]
Merged: [5, 3, 8, 1, 9, 2, 7, 4]
Sorted: [1, 2, 3, 4, 5, 7, 8, 9]
```

### Solution 8: Find Common Items

```python
list1 = ["apple", "banana", "cherry", "mango", "grape"]
list2 = ["banana", "kiwi", "mango", "orange", "grape"]

common = []
for item in list1:
    if item in list2:
        common.append(item)

print(f"List 1: {list1}")
print(f"List 2: {list2}")
print(f"Common items: {common}")
```
**Output:**
```
List 1: ['apple', 'banana', 'cherry', 'mango', 'grape']
List 2: ['banana', 'kiwi', 'mango', 'orange', 'grape']
Common items: ['banana', 'mango', 'grape']
```

### Solution 9: Flatten a Nested List

```python
nested = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(f"Nested: {nested}")

flat = []
for inner_list in nested:
    for item in inner_list:
        flat.append(item)

print(f"Flat: {flat}")

# Bonus: using list comprehension
flat2 = [item for inner in nested for item in inner]
print(f"Flat (comprehension): {flat2}")
```
**Output:**
```
Nested: [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
Flat: [1, 2, 3, 4, 5, 6, 7, 8, 9]
Flat (comprehension): [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### Solution 10: Second Largest Number

```python
numbers = [34, 67, 12, 89, 45, 23, 78]
print(f"Numbers: {numbers}")

# Remove duplicates and sort
unique = []
for num in numbers:
    if num not in unique:
        unique.append(num)

unique.sort(reverse=True)
print(f"Sorted unique: {unique}")
print(f"Second largest: {unique[1]}")
```
**Output:**
```
Numbers: [34, 67, 12, 89, 45, 23, 78]
Sorted unique: [89, 78, 67, 45, 34, 23, 12]
Second largest: 78
```

### Solution 11: Rotate a List

```python
def rotate_list(lst, n):
    """Rotate a list by n positions to the left."""
    n = n % len(lst)  # Handle cases where n > length
    return lst[n:] + lst[:n]

original = [1, 2, 3, 4, 5]

print(f"Original: {original}")
print(f"Rotated by 1: {rotate_list(original, 1)}")
print(f"Rotated by 2: {rotate_list(original, 2)}")
print(f"Rotated by 3: {rotate_list(original, 3)}")
```
**Output:**
```
Original: [1, 2, 3, 4, 5]
Rotated by 1: [2, 3, 4, 5, 1]
Rotated by 2: [3, 4, 5, 1, 2]
Rotated by 3: [4, 5, 1, 2, 3]
```

### Solution 12: Word Frequency Counter

```python
sentence = "the cat sat on the mat and the cat played with the ball"
words = sentence.split()

counted_words = []
counts = []

for word in words:
    if word in counted_words:
        index = counted_words.index(word)
        counts[index] += 1
    else:
        counted_words.append(word)
        counts.append(1)

print(f"Sentence: {sentence}")
print("\nWord Frequencies:")
for i in range(len(counted_words)):
    print(f"  '{counted_words[i]}' appears {counts[i]} time(s)")
```
**Output:**
```
Sentence: the cat sat on the mat and the cat played with the ball
Word Frequencies:
  'the' appears 4 time(s)
  'cat' appears 2 time(s)
  'sat' appears 1 time(s)
  'on' appears 1 time(s)
  'mat' appears 1 time(s)
  'and' appears 1 time(s)
  'played' appears 1 time(s)
  'with' appears 1 time(s)
  'ball' appears 1 time(s)
```

---

## Summary

Congratulations! You have learned one of the most powerful tools in Python! Here is what you covered:

| Topic | What You Learned |
|-------|-----------------|
| Creating lists | `[]`, `list()`, `list(range())` |
| Accessing items | `list[0]`, `list[-1]` |
| Modifying items | `list[0] = new_value` |
| Adding items | `.append()`, `.insert()` |
| Removing items | `.remove()`, `.pop()`, `.clear()` |
| Searching | `.index()`, `.count()`, `in` |
| Ordering | `.sort()`, `.reverse()` |
| Copying | `.copy()` |
| Slicing | `list[start:end:step]` |
| Functions | `len()`, `min()`, `max()`, `sum()` |
| Looping | `for`, `while`, `enumerate()` |
| Comprehensions | `[x for x in list if condition]` |
| Nested lists | 2D grids, tables |

Lists are everywhere in programming. Keep practicing and you will become a list master! In the next lesson, you will learn about **Tuples and Dictionaries** -- more ways to store and organize data!

Happy coding! Keep going, you are doing amazing!
