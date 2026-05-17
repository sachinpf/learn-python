# Lesson 08: Tuples, Dictionaries, and Sets

Welcome back! In this lesson, you will learn three more ways to store data in Python -- **Tuples**, **Dictionaries**, and **Sets**. Each one has its own superpower. Let's explore them all!

---

## Part 1: Tuples

### What Is a Tuple?

A **tuple** is like a list, but with one big difference -- **you cannot change it** after you create it. Think of it like writing something in permanent marker instead of pencil. Once it is written, it stays that way!

**Analogy:** Imagine your **date of birth**. It is April 15, 2012. That never changes. It is fixed, permanent, and locked in. A tuple is perfect for storing data like this.

**Key facts about tuples:**
- Tuples use **parentheses** `()` instead of square brackets `[]`
- They are **ordered** (items have a position)
- They are **immutable** (cannot be changed after creation)
- They can hold **different data types**
- They are **faster** than lists (because Python knows they will not change)

### Creating Tuples

```python
# A tuple of colors
colors = ("red", "green", "blue")
print(colors)
print(type(colors))
```
**Output:**
```
('red', 'green', 'blue')
<class 'tuple'>
```

```python
# A tuple of numbers
coordinates = (10, 20)
print(coordinates)
```
**Output:**
```
(10, 20)
```

```python
# A tuple with mixed types
student = ("Alice", 14, "Grade 9", 95.5)
print(student)
```
**Output:**
```
('Alice', 14, 'Grade 9', 95.5)
```

```python
# A tuple with one item (note the comma!)
single = (42,)
print(single)
print(type(single))

# Without the comma, it is just a number in parentheses
not_a_tuple = (42)
print(type(not_a_tuple))
```
**Output:**
```
(42,)
<class 'tuple'>
<class 'int'>
```

```python
# Creating a tuple without parentheses (tuple packing)
fruits = "apple", "banana", "cherry"
print(fruits)
print(type(fruits))
```
**Output:**
```
('apple', 'banana', 'cherry')
<class 'tuple'>
```

### Accessing Items in a Tuple

This works exactly like lists -- use the index number.

```python
seasons = ("Spring", "Summer", "Autumn", "Winter")

print(seasons[0])    # First item
print(seasons[2])    # Third item
print(seasons[-1])   # Last item
```
**Output:**
```
Spring
Autumn
Winter
```

```python
# Slicing tuples works too
days = ("Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun")
weekdays = days[:5]
weekend = days[5:]
print(f"Weekdays: {weekdays}")
print(f"Weekend: {weekend}")
```
**Output:**
```
Weekdays: ('Mon', 'Tue', 'Wed', 'Thu', 'Fri')
Weekend: ('Sat', 'Sun')
```

### You Cannot Change a Tuple!

```python
colors = ("red", "green", "blue")

# This will cause an error:
# colors[0] = "yellow"   # TypeError: 'tuple' object does not support item assignment

# You also cannot append or remove
# colors.append("yellow")  # AttributeError!

print("Tuples are immutable -- they cannot be changed!")
```
**Output:**
```
Tuples are immutable -- they cannot be changed!
```

### Tuple vs List -- When to Use Which?

| Feature | List `[]` | Tuple `()` |
|---------|-----------|------------|
| Can you change it? | Yes (mutable) | No (immutable) |
| Speed | Slower | Faster |
| Use when... | Data needs to change | Data should stay fixed |
| Example | Shopping list, to-do list | Coordinates, days of week, RGB colors |
| Syntax | `[1, 2, 3]` | `(1, 2, 3)` |

**Use a LIST when:**
- You need to add, remove, or change items
- Example: a shopping list that keeps growing

**Use a TUPLE when:**
- The data should never change
- Example: the months of the year, GPS coordinates, a person's birthday

### Tuple Unpacking

**Tuple unpacking** is a super cool trick where you take the items out of a tuple and assign them to separate variables -- all in one line!

```python
# Unpacking a tuple
coordinates = (10, 20, 30)
x, y, z = coordinates

print(f"x = {x}")
print(f"y = {y}")
print(f"z = {z}")
```
**Output:**
```
x = 10
y = 20
z = 30
```

```python
# Unpacking student info
student = ("Alice", 14, "Grade 9")
name, age, grade = student

print(f"Name: {name}")
print(f"Age: {age}")
print(f"Grade: {grade}")
```
**Output:**
```
Name: Alice
Age: 14
Grade: Grade 9
```

```python
# Swapping two variables using tuple unpacking!
a = 5
b = 10
print(f"Before: a = {a}, b = {b}")

a, b = b, a   # Swap!
print(f"After:  a = {a}, b = {b}")
```
**Output:**
```
Before: a = 5, b = 10
After:  a = 10, b = 5
```

```python
# Using * to catch extra items
first, *rest = (1, 2, 3, 4, 5)
print(f"First: {first}")
print(f"Rest: {rest}")

first, *middle, last = (1, 2, 3, 4, 5)
print(f"First: {first}")
print(f"Middle: {middle}")
print(f"Last: {last}")
```
**Output:**
```
First: 1
Rest: [2, 3, 4, 5]
First: 1
Middle: [2, 3, 4]
Last: 5
```

### Useful Tuple Operations

```python
# Counting and finding items
numbers = (1, 3, 5, 3, 7, 3, 9)
print(f"Count of 3: {numbers.count(3)}")
print(f"Index of 5: {numbers.index(5)}")

# Length
print(f"Length: {len(numbers)}")

# Checking membership
print(f"Is 5 in the tuple? {5 in numbers}")
print(f"Is 4 in the tuple? {4 in numbers}")
```
**Output:**
```
Count of 3: 3
Index of 5: 2
Length: 7
Is 5 in the tuple? True
Is 4 in the tuple? False
```

---

## Part 2: Dictionaries

### What Is a Dictionary?

A **dictionary** stores data in **key-value pairs**. Think of a real dictionary: you look up a **word** (the key) and find its **definition** (the value).

**Analogy 1 -- A Real Dictionary:**
- Word "Python" -> Definition: "A programming language"
- Word "Loop" -> Definition: "Repeating code"

**Analogy 2 -- A Phone Book:**
- Name "Alice" -> Phone: "555-0101"
- Name "Bob" -> Phone: "555-0202"

**Key facts about dictionaries:**
- Use **curly braces** `{}`
- Store data as **key: value** pairs
- Keys must be **unique** (no duplicates)
- Keys must be **immutable** (strings, numbers, or tuples)
- Values can be **anything**
- Dictionaries are **mutable** (you can change them)
- Dictionaries are **unordered** in concept, but since Python 3.7 they maintain **insertion order**

### Creating Dictionaries

```python
# A simple dictionary
student = {
    "name": "Alice",
    "age": 14,
    "grade": "9th",
    "school": "Python Academy"
}
print(student)
```
**Output:**
```
{'name': 'Alice', 'age': 14, 'grade': '9th', 'school': 'Python Academy'}
```

```python
# A phone book
phone_book = {
    "Alice": "555-0101",
    "Bob": "555-0202",
    "Charlie": "555-0303"
}
print(phone_book)
```
**Output:**
```
{'Alice': '555-0101', 'Bob': '555-0202', 'Charlie': '555-0303'}
```

```python
# An empty dictionary
empty_dict = {}
print(empty_dict)
print(type(empty_dict))
```
**Output:**
```
{}
<class 'dict'>
```

```python
# Using numbers as keys
square_roots = {
    1: 1.0,
    4: 2.0,
    9: 3.0,
    16: 4.0,
    25: 5.0
}
print(square_roots)
```
**Output:**
```
{1: 1.0, 4: 2.0, 9: 3.0, 16: 4.0, 25: 5.0}
```

### Accessing Values with Keys

Use the key inside square brackets `[]` to get the value.

```python
student = {
    "name": "Alice",
    "age": 14,
    "grade": "9th"
}

print(student["name"])
print(student["age"])
print(student["grade"])
```
**Output:**
```
Alice
14
9th
```

```python
# Using a phone book
phone_book = {
    "Alice": "555-0101",
    "Bob": "555-0202",
    "Charlie": "555-0303"
}

person = "Bob"
print(f"{person}'s number is {phone_book[person]}")
```
**Output:**
```
Bob's number is 555-0202
```

**Warning:** If you use a key that does not exist, you get a `KeyError`!

```python
# phone_book["Diana"]   # KeyError: 'Diana'
```

### Adding, Modifying, and Deleting Items

```python
# Start with a simple dictionary
pet = {"name": "Buddy", "type": "dog"}
print("Original:", pet)

# ADD a new key-value pair
pet["age"] = 5
print("After adding age:", pet)

# MODIFY an existing value
pet["age"] = 6
print("After birthday:", pet)

# DELETE an item
del pet["type"]
print("After deleting type:", pet)
```
**Output:**
```
Original: {'name': 'Buddy', 'type': 'dog'}
After adding age: {'name': 'Buddy', 'type': 'dog', 'age': 5}
After birthday: {'name': 'Buddy', 'type': 'dog', 'age': 6}
After deleting type: {'name': 'Buddy', 'age': 6}
```

```python
# Building a dictionary from scratch
scores = {}
scores["Alice"] = 95
scores["Bob"] = 87
scores["Charlie"] = 92
print(scores)
```
**Output:**
```
{'Alice': 95, 'Bob': 87, 'Charlie': 92}
```

### Dictionary Methods

#### .keys() -- Get All Keys

```python
student = {"name": "Alice", "age": 14, "grade": "9th"}

all_keys = student.keys()
print(all_keys)
print(list(all_keys))
```
**Output:**
```
dict_keys(['name', 'age', 'grade'])
['name', 'age', 'grade']
```

#### .values() -- Get All Values

```python
student = {"name": "Alice", "age": 14, "grade": "9th"}

all_values = student.values()
print(all_values)
print(list(all_values))
```
**Output:**
```
dict_values(['Alice', 14, '9th'])
['Alice', 14, '9th']
```

#### .items() -- Get All Key-Value Pairs

```python
student = {"name": "Alice", "age": 14, "grade": "9th"}

all_items = student.items()
print(all_items)

# Each item is a tuple of (key, value)
for key, value in student.items():
    print(f"  {key}: {value}")
```
**Output:**
```
dict_items([('name', 'Alice'), ('age', 14), ('grade', '9th')])
  name: Alice
  age: 14
  grade: 9th
```

#### .get() -- Safely Get a Value

The `.get()` method is safer than using `[]` because it does not crash if the key does not exist. Instead, it returns `None` (or a default value you choose).

```python
student = {"name": "Alice", "age": 14}

# Using .get() with an existing key
print(student.get("name"))

# Using .get() with a missing key (returns None)
print(student.get("grade"))

# Using .get() with a default value
print(student.get("grade", "Not assigned"))
```
**Output:**
```
Alice
None
Not assigned
```

```python
# Practical example: counting votes
votes = {"Alice": 5, "Bob": 3}

# Get Bob's votes (exists)
print(f"Bob has {votes.get('Bob', 0)} votes")

# Get Charlie's votes (does not exist, returns 0)
print(f"Charlie has {votes.get('Charlie', 0)} votes")
```
**Output:**
```
Bob has 3 votes
Charlie has 0 votes
```

#### .update() -- Merge Dictionaries

```python
student = {"name": "Alice", "age": 14}
print("Before:", student)

# Add multiple items at once
student.update({"grade": "9th", "school": "Python Academy"})
print("After update:", student)

# Update existing values
student.update({"age": 15})
print("After birthday:", student)
```
**Output:**
```
Before: {'name': 'Alice', 'age': 14}
After update: {'name': 'Alice', 'age': 14, 'grade': '9th', 'school': 'Python Academy'}
After birthday: {'name': 'Alice', 'age': 15, 'grade': '9th', 'school': 'Python Academy'}
```

#### .pop() -- Remove and Return a Value

```python
student = {"name": "Alice", "age": 14, "grade": "9th"}
print("Before:", student)

removed = student.pop("age")
print(f"Removed age: {removed}")
print("After:", student)

# Using a default to avoid errors
result = student.pop("phone", "Not found")
print(f"Phone: {result}")
```
**Output:**
```
Before: {'name': 'Alice', 'age': 14, 'grade': '9th'}
Removed age: 14
After: {'name': 'Alice', 'grade': '9th'}
Phone: Not found
```

### Looping Through Dictionaries

```python
# Loop through keys
scores = {"Alice": 95, "Bob": 87, "Charlie": 92}

print("--- Keys only ---")
for name in scores:
    print(name)

print("\n--- Keys and Values ---")
for name in scores:
    print(f"{name}: {scores[name]}")

print("\n--- Using .items() (best way!) ---")
for name, score in scores.items():
    print(f"{name} scored {score}")
```
**Output:**
```
--- Keys only ---
Alice
Bob
Charlie

--- Keys and Values ---
Alice: 95
Bob: 87
Charlie: 92

--- Using .items() (best way!) ---
Alice scored 95
Bob scored 87
Charlie scored 92
```

```python
# Find the student with the highest score
scores = {"Alice": 95, "Bob": 87, "Charlie": 92, "Diana": 98}

best_student = ""
best_score = 0

for student, score in scores.items():
    if score > best_score:
        best_score = score
        best_student = student

print(f"Top student: {best_student} with a score of {best_score}")
```
**Output:**
```
Top student: Diana with a score of 98
```

### Checking if a Key Exists

```python
student = {"name": "Alice", "age": 14, "grade": "9th"}

print("name" in student)
print("phone" in student)

if "age" in student:
    print(f"Age is {student['age']}")
else:
    print("Age not found")
```
**Output:**
```
True
False
Age is 14
```

### Nested Dictionaries

Dictionaries can contain other dictionaries! This is great for organizing complex data.

```python
# A school database
school = {
    "Alice": {
        "age": 14,
        "grade": "9th",
        "subjects": ["Math", "Science", "English"]
    },
    "Bob": {
        "age": 13,
        "grade": "8th",
        "subjects": ["Math", "Art", "History"]
    },
    "Charlie": {
        "age": 15,
        "grade": "10th",
        "subjects": ["Physics", "Chemistry", "Math"]
    }
}

# Access nested data
print(f"Alice's age: {school['Alice']['age']}")
print(f"Bob's subjects: {school['Bob']['subjects']}")
print(f"Charlie's first subject: {school['Charlie']['subjects'][0]}")
```
**Output:**
```
Alice's age: 14
Bob's subjects: ['Math', 'Art', 'History']
Charlie's first subject: Physics
```

```python
# Loop through nested dictionaries
print("\n--- All Students ---")
for name, info in school.items():
    print(f"\n{name}:")
    print(f"  Age: {info['age']}")
    print(f"  Grade: {info['grade']}")
    print(f"  Subjects: {', '.join(info['subjects'])}")
```
**Output:**
```
--- All Students ---

Alice:
  Age: 14
  Grade: 9th
  Subjects: Math, Science, English

Bob:
  Age: 13
  Grade: 8th
  Subjects: Math, Art, History

Charlie:
  Age: 15
  Grade: 10th
  Subjects: Physics, Chemistry, Math
```

---

## Part 3: Sets (Brief Introduction)

### What Is a Set?

A **set** is a collection of **unique** items (no duplicates allowed!). Sets are great when you care about "what items do I have?" but not about their order.

**Analogy:** Think of a **bag of marbles**. Each marble is a different color. You cannot have two identical marbles, and they are all jumbled up in the bag (no specific order).

**Key facts about sets:**
- Use **curly braces** `{}` (like dictionaries, but without key-value pairs)
- **No duplicate** items
- **Unordered** (items have no index)
- **Mutable** (you can add and remove items)
- Great for **comparing** groups of data

### Creating Sets

```python
# A set of fruits
fruits = {"apple", "banana", "cherry"}
print(fruits)
print(type(fruits))
```
**Output:**
```
{'cherry', 'banana', 'apple'}
<class 'set'>
```
(Note: the order may vary because sets are unordered!)

```python
# Duplicates are automatically removed!
numbers = {1, 2, 3, 2, 4, 3, 5}
print(numbers)
```
**Output:**
```
{1, 2, 3, 4, 5}
```

```python
# Creating a set from a list (removes duplicates!)
my_list = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]
my_set = set(my_list)
print(f"List: {my_list}")
print(f"Set: {my_set}")
```
**Output:**
```
List: [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]
Set: {1, 2, 3, 4}
```

### .add() and .remove()

```python
colors = {"red", "green", "blue"}
print("Original:", colors)

# Add an item
colors.add("yellow")
print("After add:", colors)

# Adding a duplicate does nothing
colors.add("red")
print("After adding 'red' again:", colors)

# Remove an item
colors.remove("green")
print("After remove:", colors)
```
**Output:**
```
Original: {'red', 'green', 'blue'}
After add: {'red', 'green', 'blue', 'yellow'}
After adding 'red' again: {'red', 'green', 'blue', 'yellow'}
After remove: {'red', 'blue', 'yellow'}
```

### Set Operations: Union, Intersection, and Difference

These are like math operations with groups of things. This is where sets really shine!

#### Union -- Combine Everything

The union gives you **all** items from **both** sets (no duplicates).

```python
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

# All items from both sets
result = set_a | set_b           # Using the | operator
result2 = set_a.union(set_b)    # Using the .union() method

print(f"Set A: {set_a}")
print(f"Set B: {set_b}")
print(f"Union: {result}")
```
**Output:**
```
Set A: {1, 2, 3, 4}
Set B: {3, 4, 5, 6}
Union: {1, 2, 3, 4, 5, 6}
```

#### Intersection -- Only Common Items

The intersection gives you items that appear in **both** sets.

```python
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

result = set_a & set_b                  # Using the & operator
result2 = set_a.intersection(set_b)     # Using the method

print(f"Set A: {set_a}")
print(f"Set B: {set_b}")
print(f"Intersection: {result}")
```
**Output:**
```
Set A: {1, 2, 3, 4}
Set B: {3, 4, 5, 6}
Intersection: {3, 4}
```

#### Difference -- Items in One but Not the Other

```python
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

# Items in A but NOT in B
diff = set_a - set_b
print(f"A - B: {diff}")

# Items in B but NOT in A
diff2 = set_b - set_a
print(f"B - A: {diff2}")
```
**Output:**
```
A - B: {1, 2}
B - A: {5, 6}
```

#### Practical Example: Students in Classes

```python
math_class = {"Alice", "Bob", "Charlie", "Diana", "Eve"}
science_class = {"Bob", "Diana", "Frank", "Grace"}

# Students in BOTH classes
both = math_class & science_class
print(f"In both Math and Science: {both}")

# Students in Math but NOT Science
math_only = math_class - science_class
print(f"Only in Math: {math_only}")

# ALL students across both classes
all_students = math_class | science_class
print(f"All students: {all_students}")
print(f"Total unique students: {len(all_students)}")
```
**Output:**
```
In both Math and Science: {'Bob', 'Diana'}
Only in Math: {'Alice', 'Charlie', 'Eve'}
All students: {'Alice', 'Bob', 'Charlie', 'Diana', 'Eve', 'Frank', 'Grace'}
Total unique students: 7
```

---

## Exercises

Try these exercises on your own, then check the solutions below!

### Exercise 1: Phone Book
Create a phone book dictionary where users can:
- Add a contact
- Look up a number
- Delete a contact
- View all contacts

### Exercise 2: Word Counter
Write a program that counts how many times each word appears in a sentence using a dictionary.

### Exercise 3: Student Grades
Create a dictionary of students and their grades (list of scores). Calculate and display the average for each student.

### Exercise 4: Inventory System
Create a simple store inventory system using a dictionary. Items have names, prices, and quantities. Allow adding, updating, and displaying items.

### Exercise 5: Tuple Unpacking Practice
Given a list of tuples containing (name, age, city), unpack and print each person's info.

### Exercise 6: Merge Two Dictionaries
Write a program that merges two dictionaries. If a key exists in both, add the values together.

### Exercise 7: Character Frequency
Count the frequency of each character in a string (ignoring spaces) using a dictionary.

### Exercise 8: Nested Dictionary -- School Report
Create a nested dictionary for 3 students with their name, age, and dictionary of subject scores. Print a report card for each.

### Exercise 9: Set Operations -- Friend Groups
Two people have different friend groups. Find mutual friends, unique friends of each person, and all friends combined.

### Exercise 10: Dictionary Comprehension (Bonus Challenge)
Create a dictionary of numbers 1-10 and their squares using a dictionary comprehension.

### Exercise 11: Translation Dictionary
Create a simple English-to-Spanish translator using a dictionary. Let the user type English words and see the Spanish translation.

### Exercise 12: Vote Counter
Write a program that counts votes from a list and displays the winner.

---

## Solutions

### Solution 1: Phone Book

```python
phone_book = {}

while True:
    print("\n--- Phone Book ---")
    print("1. Add contact")
    print("2. Look up number")
    print("3. Delete contact")
    print("4. View all contacts")
    print("5. Quit")

    choice = input("Choose (1-5): ")

    if choice == "1":
        name = input("Enter name: ")
        number = input("Enter number: ")
        phone_book[name] = number
        print(f"Added {name}: {number}")

    elif choice == "2":
        name = input("Enter name to look up: ")
        if name in phone_book:
            print(f"{name}'s number: {phone_book[name]}")
        else:
            print(f"{name} not found!")

    elif choice == "3":
        name = input("Enter name to delete: ")
        if name in phone_book:
            del phone_book[name]
            print(f"{name} deleted!")
        else:
            print(f"{name} not found!")

    elif choice == "4":
        if phone_book:
            print("\nAll Contacts:")
            for name, number in phone_book.items():
                print(f"  {name}: {number}")
        else:
            print("Phone book is empty.")

    elif choice == "5":
        print("Goodbye!")
        break
```

### Solution 2: Word Counter

```python
sentence = "the cat sat on the mat and the cat played with the ball"
words = sentence.lower().split()

word_count = {}
for word in words:
    if word in word_count:
        word_count[word] += 1
    else:
        word_count[word] = 1

print(f"Sentence: {sentence}")
print("\nWord Counts:")
for word, count in word_count.items():
    print(f"  '{word}': {count}")

# Find the most common word
most_common = max(word_count, key=word_count.get)
print(f"\nMost common word: '{most_common}' ({word_count[most_common]} times)")
```
**Output:**
```
Sentence: the cat sat on the mat and the cat played with the ball

Word Counts:
  'the': 4
  'cat': 2
  'sat': 1
  'on': 1
  'mat': 1
  'and': 1
  'played': 1
  'with': 1
  'ball': 1

Most common word: 'the' (4 times)
```

### Solution 3: Student Grades

```python
students = {
    "Alice": [95, 87, 92, 88],
    "Bob": [78, 82, 85, 90],
    "Charlie": [92, 95, 98, 96],
    "Diana": [70, 75, 68, 72]
}

print("=== Student Report ===\n")
for name, grades in students.items():
    average = sum(grades) / len(grades)
    highest = max(grades)
    lowest = min(grades)
    print(f"{name}:")
    print(f"  Grades: {grades}")
    print(f"  Average: {average:.1f}")
    print(f"  Highest: {highest}")
    print(f"  Lowest: {lowest}")
    print()
```
**Output:**
```
=== Student Report ===

Alice:
  Grades: [95, 87, 92, 88]
  Average: 90.5
  Highest: 95
  Lowest: 87

Bob:
  Grades: [78, 82, 85, 90]
  Average: 83.8
  Highest: 90
  Lowest: 78

Charlie:
  Grades: [92, 95, 98, 96]
  Average: 95.2
  Highest: 98
  Lowest: 92

Diana:
  Grades: [70, 75, 68, 72]
  Average: 71.2
  Highest: 75
  Lowest: 68
```

### Solution 4: Inventory System

```python
inventory = {
    "apple": {"price": 0.50, "quantity": 100},
    "bread": {"price": 2.99, "quantity": 50},
    "milk": {"price": 3.49, "quantity": 30}
}

while True:
    print("\n--- Inventory System ---")
    print("1. View inventory")
    print("2. Add item")
    print("3. Update quantity")
    print("4. Calculate total value")
    print("5. Quit")

    choice = input("Choose (1-5): ")

    if choice == "1":
        print(f"\n{'Item':<15} {'Price':>8} {'Quantity':>10}")
        print("-" * 35)
        for item, details in inventory.items():
            print(f"{item:<15} ${details['price']:>7.2f} {details['quantity']:>10}")

    elif choice == "2":
        item = input("Item name: ").lower()
        price = float(input("Price: $"))
        qty = int(input("Quantity: "))
        inventory[item] = {"price": price, "quantity": qty}
        print(f"Added {item}!")

    elif choice == "3":
        item = input("Item name: ").lower()
        if item in inventory:
            qty = int(input("New quantity: "))
            inventory[item]["quantity"] = qty
            print(f"Updated {item} quantity to {qty}")
        else:
            print("Item not found!")

    elif choice == "4":
        total = 0
        for item, details in inventory.items():
            item_value = details["price"] * details["quantity"]
            total += item_value
        print(f"\nTotal inventory value: ${total:.2f}")

    elif choice == "5":
        print("Goodbye!")
        break
```

### Solution 5: Tuple Unpacking Practice

```python
people = [
    ("Alice", 14, "New York"),
    ("Bob", 13, "London"),
    ("Charlie", 15, "Tokyo"),
    ("Diana", 12, "Paris")
]

print("=== People Directory ===\n")
for name, age, city in people:
    print(f"Name: {name}")
    print(f"  Age: {age} years old")
    print(f"  City: {city}")
    print()
```
**Output:**
```
=== People Directory ===

Name: Alice
  Age: 14 years old
  City: New York

Name: Bob
  Age: 13 years old
  City: London

Name: Charlie
  Age: 15 years old
  City: Tokyo

Name: Diana
  Age: 12 years old
  City: Paris
```

### Solution 6: Merge Two Dictionaries

```python
dict1 = {"math": 90, "science": 85, "english": 88}
dict2 = {"science": 92, "history": 78, "math": 95}

print(f"Dict 1: {dict1}")
print(f"Dict 2: {dict2}")

merged = {}
# Add all from dict1
for key, value in dict1.items():
    merged[key] = value

# Add from dict2, combining values if key exists
for key, value in dict2.items():
    if key in merged:
        merged[key] = merged[key] + value  # Add the values together
    else:
        merged[key] = value

print(f"Merged (values added): {merged}")
```
**Output:**
```
Dict 1: {'math': 90, 'science': 85, 'english': 88}
Dict 2: {'science': 92, 'history': 78, 'math': 95}
Merged (values added): {'math': 185, 'science': 177, 'english': 88, 'history': 78}
```

### Solution 7: Character Frequency

```python
text = "hello world"
print(f"Text: '{text}'")

char_count = {}
for char in text:
    if char != " ":   # Skip spaces
        if char in char_count:
            char_count[char] += 1
        else:
            char_count[char] = 1

print("\nCharacter Frequencies:")
for char, count in char_count.items():
    print(f"  '{char}': {count}")
```
**Output:**
```
Text: 'hello world'

Character Frequencies:
  'h': 1
  'e': 1
  'l': 3
  'o': 2
  'w': 1
  'r': 1
  'd': 1
```

### Solution 8: Nested Dictionary -- School Report

```python
students = {
    "Alice": {
        "age": 14,
        "scores": {
            "Math": 95,
            "Science": 88,
            "English": 92
        }
    },
    "Bob": {
        "age": 13,
        "scores": {
            "Math": 78,
            "Science": 85,
            "English": 80
        }
    },
    "Charlie": {
        "age": 15,
        "scores": {
            "Math": 92,
            "Science": 96,
            "English": 89
        }
    }
}

print("=" * 40)
print("       SCHOOL REPORT CARDS")
print("=" * 40)

for name, info in students.items():
    print(f"\nStudent: {name} (Age: {info['age']})")
    print("-" * 30)

    total = 0
    for subject, score in info["scores"].items():
        print(f"  {subject:<10}: {score}")
        total += score

    avg = total / len(info["scores"])
    print(f"  {'Average':<10}: {avg:.1f}")

    if avg >= 90:
        print(f"  Grade: A -- Excellent!")
    elif avg >= 80:
        print(f"  Grade: B -- Good job!")
    elif avg >= 70:
        print(f"  Grade: C -- Keep trying!")
    else:
        print(f"  Grade: D -- Needs improvement")
```
**Output:**
```
========================================
       SCHOOL REPORT CARDS
========================================

Student: Alice (Age: 14)
------------------------------
  Math      : 95
  Science   : 88
  English   : 92
  Average   : 91.7
  Grade: A -- Excellent!

Student: Bob (Age: 13)
------------------------------
  Math      : 78
  Science   : 85
  English   : 80
  Average   : 81.0
  Grade: B -- Good job!

Student: Charlie (Age: 15)
------------------------------
  Math      : 92
  Science   : 96
  English   : 89
  Average   : 92.3
  Grade: A -- Excellent!
```

### Solution 9: Set Operations -- Friend Groups

```python
alice_friends = {"Bob", "Charlie", "Diana", "Eve", "Frank"}
bob_friends = {"Charlie", "Eve", "Grace", "Henry", "Diana"}

print(f"Alice's friends: {alice_friends}")
print(f"Bob's friends: {bob_friends}")

# Mutual friends
mutual = alice_friends & bob_friends
print(f"\nMutual friends: {mutual}")

# Friends only Alice has
alice_only = alice_friends - bob_friends
print(f"Only Alice's friends: {alice_only}")

# Friends only Bob has
bob_only = bob_friends - alice_friends
print(f"Only Bob's friends: {bob_only}")

# All friends combined
all_friends = alice_friends | bob_friends
print(f"All friends: {all_friends}")
print(f"Total unique friends: {len(all_friends)}")
```
**Output:**
```
Alice's friends: {'Bob', 'Charlie', 'Diana', 'Eve', 'Frank'}
Bob's friends: {'Charlie', 'Eve', 'Grace', 'Henry', 'Diana'}

Mutual friends: {'Charlie', 'Diana', 'Eve'}
Only Alice's friends: {'Bob', 'Frank'}
Only Bob's friends: {'Grace', 'Henry'}
All friends: {'Bob', 'Charlie', 'Diana', 'Eve', 'Frank', 'Grace', 'Henry'}
Total unique friends: 7
```

### Solution 10: Dictionary Comprehension

```python
# Dictionary of numbers and their squares
squares = {n: n**2 for n in range(1, 11)}
print("Squares:", squares)

# Dictionary of numbers and whether they are even
even_odd = {n: "even" if n % 2 == 0 else "odd" for n in range(1, 11)}
print("Even/Odd:", even_odd)

# Nicely formatted
print("\nNumber | Square | Even/Odd")
print("-" * 30)
for n in range(1, 11):
    print(f"  {n:>4} | {squares[n]:>6} | {even_odd[n]}")
```
**Output:**
```
Squares: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25, 6: 36, 7: 49, 8: 64, 9: 81, 10: 100}
Even/Odd: {1: 'odd', 2: 'even', 3: 'odd', 4: 'even', 5: 'odd', 6: 'even', 7: 'odd', 8: 'even', 9: 'odd', 10: 'even'}

Number | Square | Even/Odd
------------------------------
     1 |      1 | odd
     2 |      4 | even
     3 |      9 | odd
     4 |     16 | even
     5 |     25 | odd
     6 |     36 | even
     7 |     49 | odd
     8 |     64 | even
     9 |     81 | odd
    10 |    100 | even
```

### Solution 11: Translation Dictionary

```python
english_to_spanish = {
    "hello": "hola",
    "goodbye": "adios",
    "please": "por favor",
    "thank you": "gracias",
    "yes": "si",
    "no": "no",
    "friend": "amigo",
    "water": "agua",
    "food": "comida",
    "house": "casa"
}

print("=== English to Spanish Translator ===")
print("Type 'quit' to exit.\n")

while True:
    word = input("Enter an English word: ").lower()

    if word == "quit":
        print("Adios!")
        break

    translation = english_to_spanish.get(word, None)
    if translation:
        print(f"  '{word}' in Spanish is '{translation}'")
    else:
        print(f"  Sorry, I don't know the word '{word}'")
        print(f"  I know these words: {', '.join(english_to_spanish.keys())}")
```

### Solution 12: Vote Counter

```python
votes = ["Alice", "Bob", "Alice", "Charlie", "Bob", "Alice",
         "Diana", "Bob", "Alice", "Charlie", "Alice", "Bob"]

print(f"Total votes cast: {len(votes)}\n")

# Count votes using a dictionary
vote_count = {}
for name in votes:
    vote_count[name] = vote_count.get(name, 0) + 1

# Display results
print("--- Election Results ---")
for candidate, count in vote_count.items():
    bar = "#" * count  # Visual bar
    print(f"  {candidate:<10}: {count} votes  {bar}")

# Find the winner
winner = max(vote_count, key=vote_count.get)
print(f"\nThe winner is {winner} with {vote_count[winner]} votes!")
```
**Output:**
```
Total votes cast: 12

--- Election Results ---
  Alice     : 5 votes  #####
  Bob       : 4 votes  ####
  Charlie   : 2 votes  ##
  Diana     : 1 votes  #

The winner is Alice with 5 votes!
```

---

## Summary

You learned three powerful data structures today!

### Tuples
| Feature | Details |
|---------|---------|
| Create | `my_tuple = (1, 2, 3)` |
| Access | `my_tuple[0]` |
| Unpack | `a, b, c = my_tuple` |
| Key fact | Immutable (cannot change) |

### Dictionaries
| Feature | Details |
|---------|---------|
| Create | `my_dict = {"key": "value"}` |
| Access | `my_dict["key"]` or `my_dict.get("key")` |
| Add/Modify | `my_dict["new_key"] = value` |
| Delete | `del my_dict["key"]` or `.pop("key")` |
| Loop | `for key, value in my_dict.items()` |
| Key fact | Key-value pairs, keys must be unique |

### Sets
| Feature | Details |
|---------|---------|
| Create | `my_set = {1, 2, 3}` |
| Add | `my_set.add(4)` |
| Remove | `my_set.remove(2)` |
| Union | `set_a \| set_b` |
| Intersection | `set_a & set_b` |
| Key fact | No duplicates, unordered |

You are doing fantastic! In the next lesson, you will learn about **Functions** -- how to create reusable blocks of code that make your programs cleaner and more powerful!

Keep coding and keep learning!
