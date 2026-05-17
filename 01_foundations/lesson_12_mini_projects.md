# Lesson 12: Mini Projects

## Putting It All Together — 10 Complete Projects!

---

Congratulations! You've learned so much Python — variables, strings, lists, dictionaries, loops, functions, file handling, and error handling. Now it's time to **build real things**!

Each project below is a complete program. Read through the code, understand how it works, type it out yourself, and then try the bonus challenges!

---

## Project 1: Mad Libs Game

### What We'll Build
A silly story generator where the player fills in words (nouns, verbs, adjectives) and the program creates a funny story with them!

### Concepts Used
- Strings and f-strings
- `input()` function
- String formatting

### Complete Code

```python
# ===================================================================
# PROJECT 1: MAD LIBS GAME
# ===================================================================
# Mad Libs is a word game where you fill in blanks to create
# a funny story. The player doesn't know the story in advance,
# so the results are always hilarious!
# ===================================================================

def play_mad_libs():
    """Play one round of Mad Libs."""

    # Display a welcome message
    print("=" * 50)
    print("       WELCOME TO MAD LIBS!")
    print("  Fill in the blanks for a silly story!")
    print("=" * 50)
    print()

    # Ask the player for different types of words
    # They don't know how these words will be used!
    adjective1 = input("Enter an adjective (describes something, like 'silly'): ")
    noun1 = input("Enter a noun (a thing, like 'pizza'): ")
    verb1 = input("Enter a verb (an action, like 'dance'): ")
    animal = input("Enter an animal: ")
    food = input("Enter a food: ")
    adjective2 = input("Enter another adjective: ")
    number = input("Enter a number: ")
    verb2 = input("Enter another verb (past tense, like 'jumped'): ")
    place = input("Enter a place (like 'the moon'): ")
    exclamation = input("Enter an exclamation (like 'Wow!' or 'Oh no!'): ")

    # Build the story using f-strings
    # Each blank is filled with the player's words
    story = f"""
    ╔══════════════════════════════════════════════╗
    ║           YOUR MAD LIBS STORY                ║
    ╚══════════════════════════════════════════════╝

    Once upon a time, there was a very {adjective1} {noun1}
    who loved to {verb1} every single day.

    One morning, a {adjective2} {animal} knocked on the door
    and said, "{exclamation} I need {number} plates of {food}
    right now!"

    The {noun1} {verb2} all the way to {place} to find
    the perfect {food}. When they returned, the {animal}
    was so happy that it started to {verb1} on the table!

    And they all lived {adjective1}ly ever after.

    THE END
    """

    # Display the completed story
    print(story)

def main():
    """Main function to run the Mad Libs game."""
    while True:
        # Play a round
        play_mad_libs()

        # Ask if they want to play again
        play_again = input("\nPlay again? (yes/no): ").lower().strip()
        if play_again != "yes":
            print("\nThanks for playing Mad Libs! Hope you had fun!")
            break
        print()  # Blank line before next round

# Run the game
main()
```

### Sample Output
```
==================================================
       WELCOME TO MAD LIBS!
  Fill in the blanks for a silly story!
==================================================

Enter an adjective (describes something, like 'silly'): sparkly
Enter a noun (a thing, like 'pizza'): toaster
Enter a verb (an action, like 'dance'): wiggle
Enter an animal: penguin
Enter a food: spaghetti
Enter another adjective: enormous
Enter a number: 47
Enter another verb (past tense, like 'jumped'): somersaulted
Enter a place (like 'the moon'): the North Pole
Enter an exclamation (like 'Wow!' or 'Oh no!'): Holy macaroni!

    Once upon a time, there was a very sparkly toaster
    who loved to wiggle every single day.

    One morning, a enormous penguin knocked on the door
    and said, "Holy macaroni! I need 47 plates of spaghetti
    right now!"

    The toaster somersaulted all the way to the North Pole to find
    the perfect spaghetti. When they returned, the penguin
    was so happy that it started to wiggle on the table!

    And they all lived sparklyly ever after.

    THE END
```

### Bonus Challenges
1. Add **3 different story templates** and let the player choose which one to play
2. Save the completed stories to a file so you can read them later
3. Add a "random word" option where the program picks a random word if the player presses Enter without typing anything
4. Create a **two-player mode** where one person enters words and the other reads the story

---

## Project 2: Number Guessing Game

### What We'll Build
A game where the computer picks a random number and the player tries to guess it. The computer gives hints ("too high" or "too low") after each guess.

### Concepts Used
- `random` module
- `while` loops
- `if/elif/else` conditions
- Input validation with `try-except`
- f-strings

### Complete Code

```python
# ===================================================================
# PROJECT 2: NUMBER GUESSING GAME
# ===================================================================
# The computer picks a secret number, and you try to guess it!
# After each guess, you get a hint: "too high" or "too low."
# Can you guess it in as few tries as possible?
# ===================================================================

import random

def get_difficulty():
    """Let the player choose a difficulty level."""
    print("\nChoose your difficulty:")
    print("  1. Easy   (1-50,   10 guesses)")
    print("  2. Medium (1-100,  7 guesses)")
    print("  3. Hard   (1-500,  9 guesses)")
    print("  4. Expert (1-1000, 10 guesses)")

    while True:
        choice = input("\nYour choice (1-4): ").strip()

        # Return (max_number, max_guesses) based on choice
        if choice == "1":
            return 50, 10
        elif choice == "2":
            return 100, 7
        elif choice == "3":
            return 500, 9
        elif choice == "4":
            return 1000, 10
        else:
            print("Please enter 1, 2, 3, or 4.")

def play_round():
    """Play one round of the guessing game."""

    # Get difficulty settings
    max_number, max_guesses = get_difficulty()

    # The computer picks a random secret number
    secret_number = random.randint(1, max_number)

    # Track the number of guesses
    guesses_taken = 0

    # Store all previous guesses to prevent repeats
    previous_guesses = []

    print(f"\nI'm thinking of a number between 1 and {max_number}.")
    print(f"You have {max_guesses} guesses. Let's go!\n")

    # Main game loop — keep going until they guess correctly or run out
    while guesses_taken < max_guesses:
        # Show remaining guesses
        remaining = max_guesses - guesses_taken
        print(f"Guesses remaining: {remaining}")

        # Get the player's guess with error handling
        try:
            guess = int(input("Your guess: "))
        except ValueError:
            # If they type something that's not a number
            print("That's not a valid number! Try again.\n")
            continue  # Don't count this as a guess

        # Check if the guess is in range
        if guess < 1 or guess > max_number:
            print(f"Please guess between 1 and {max_number}!\n")
            continue  # Don't count this as a guess

        # Check if they already guessed this number
        if guess in previous_guesses:
            print(f"You already guessed {guess}! Try a different number.\n")
            continue  # Don't count this as a guess

        # Count this as a valid guess
        guesses_taken += 1
        previous_guesses.append(guess)

        # Compare the guess to the secret number
        if guess == secret_number:
            # They got it! Celebrate!
            print(f"\n{'=' * 40}")
            print(f"  CORRECT! The number was {secret_number}!")
            print(f"  You got it in {guesses_taken} guess(es)!")

            # Rate their performance
            if guesses_taken == 1:
                print("  INCREDIBLE! First try! Are you psychic?!")
            elif guesses_taken <= 3:
                print("  AMAZING! You're a guessing genius!")
            elif guesses_taken <= max_guesses // 2:
                print("  GREAT JOB! Well done!")
            else:
                print("  NICE! You figured it out!")

            print(f"{'=' * 40}\n")
            return guesses_taken  # Return the score

        elif guess < secret_number:
            # Guess is too low
            print("  Too LOW! Guess higher.")

            # Give extra hint if they're very far off
            difference = secret_number - guess
            if difference > max_number // 2:
                print("  (WAY too low!)")
            print()

        else:
            # Guess is too high
            print("  Too HIGH! Guess lower.")

            # Give extra hint if they're very far off
            difference = guess - secret_number
            if difference > max_number // 2:
                print("  (WAY too high!)")
            print()

    # They ran out of guesses
    print(f"\n{'=' * 40}")
    print(f"  OUT OF GUESSES!")
    print(f"  The secret number was {secret_number}.")
    print(f"  Better luck next time!")
    print(f"{'=' * 40}\n")
    return None  # No score (they didn't guess it)

def main():
    """Main function with score tracking."""
    print("=" * 50)
    print("     NUMBER GUESSING GAME")
    print("=" * 50)

    # Track best scores
    scores = []

    while True:
        # Play a round
        score = play_round()

        # Record the score if they won
        if score is not None:
            scores.append(score)
            print(f"Your scores so far: {scores}")
            if len(scores) > 1:
                print(f"Best score: {min(scores)} guesses")
                print(f"Average: {sum(scores) / len(scores):.1f} guesses")

        # Ask to play again
        play_again = input("Play again? (yes/no): ").lower().strip()
        if play_again != "yes":
            print("\nThanks for playing!")
            if scores:
                print(f"Final best score: {min(scores)} guess(es)")
            break

# Run the game
main()
```

### Sample Output
```
==================================================
     NUMBER GUESSING GAME
==================================================

Choose your difficulty:
  1. Easy   (1-50,   10 guesses)
  2. Medium (1-100,  7 guesses)
  3. Hard   (1-500,  9 guesses)
  4. Expert (1-1000, 10 guesses)

Your choice (1-4): 2

I'm thinking of a number between 1 and 100.
You have 7 guesses. Let's go!

Guesses remaining: 7
Your guess: 50
  Too HIGH! Guess lower.

Guesses remaining: 6
Your guess: 25
  Too LOW! Guess higher.

Guesses remaining: 5
Your guess: 37
  Too LOW! Guess higher.

Guesses remaining: 4
Your guess: 43
  CORRECT! The number was 43!
  You got it in 4 guess(es)!
  GREAT JOB! Well done!
```

### Bonus Challenges
1. Add a **hint system** where the player can type "hint" to get a range (costs one guess)
2. Save the **high score leaderboard** to a file
3. Add a **two-player mode** where one player picks the number and the other guesses
4. Make the computer guess YOUR number — implement **binary search**!

---

## Project 3: Rock Paper Scissors

### What We'll Build
The classic Rock, Paper, Scissors game against the computer! Play best of 3, 5, or unlimited rounds.

### Concepts Used
- `random.choice()`
- Conditions (`if/elif/else`)
- `while` loops
- Dictionaries (for score tracking)
- Functions

### Complete Code

```python
# ===================================================================
# PROJECT 3: ROCK PAPER SCISSORS
# ===================================================================
# The classic game! You vs the computer.
# Rock beats Scissors, Scissors beats Paper, Paper beats Rock.
# ===================================================================

import random

def display_welcome():
    """Show the welcome screen with ASCII art."""
    print("""
    ╔══════════════════════════════════════╗
    ║     ROCK  PAPER  SCISSORS            ║
    ║                                      ║
    ║     Rock     ✊  beats Scissors       ║
    ║     Scissors ✌  beats Paper          ║
    ║     Paper    ✋  beats Rock           ║
    ╚══════════════════════════════════════╝
    """)

def get_player_choice():
    """Get the player's choice with input validation."""
    # Map shortcuts to full names for convenience
    valid_choices = {
        "r": "rock",
        "p": "paper",
        "s": "scissors",
        "rock": "rock",
        "paper": "paper",
        "scissors": "scissors"
    }

    while True:
        choice = input("Choose [R]ock, [P]aper, or [S]cissors: ").lower().strip()

        if choice in valid_choices:
            return valid_choices[choice]
        else:
            print("Invalid choice! Enter R, P, or S.")

def get_computer_choice():
    """The computer randomly picks rock, paper, or scissors."""
    return random.choice(["rock", "paper", "scissors"])

def determine_winner(player, computer):
    """
    Determine who wins a round.

    Returns:
        "player"   if the player wins
        "computer" if the computer wins
        "tie"      if it's a tie
    """
    # If both chose the same thing, it's a tie
    if player == computer:
        return "tie"

    # Define winning combinations: key beats value
    # Rock beats Scissors, Scissors beats Paper, Paper beats Rock
    wins = {
        "rock": "scissors",      # Rock crushes Scissors
        "scissors": "paper",     # Scissors cuts Paper
        "paper": "rock"          # Paper covers Rock
    }

    # If the computer's choice is what the player's choice beats...
    if wins[player] == computer:
        return "player"
    else:
        return "computer"

def display_choices(player_choice, computer_choice):
    """Show both choices with some flair."""
    # Fun symbols for each choice
    symbols = {
        "rock":     "[ROCK]",
        "paper":    "[PAPER]",
        "scissors": "[SCISSORS]"
    }

    print(f"\n  You chose:      {symbols[player_choice]}")
    print(f"  Computer chose: {symbols[computer_choice]}")

def display_round_result(result, player, computer):
    """Show the result of a round with an explanation."""
    if result == "tie":
        print(f"  It's a TIE! You both chose {player}.\n")
    elif result == "player":
        explanations = {
            ("rock", "scissors"):     "Rock crushes Scissors!",
            ("scissors", "paper"):    "Scissors cuts Paper!",
            ("paper", "rock"):        "Paper covers Rock!"
        }
        explanation = explanations.get((player, computer), "")
        print(f"  YOU WIN this round! {explanation}\n")
    else:
        explanations = {
            ("rock", "scissors"):     "Rock crushes Scissors!",
            ("scissors", "paper"):    "Scissors cuts Paper!",
            ("paper", "rock"):        "Paper covers Rock!"
        }
        explanation = explanations.get((computer, player), "")
        print(f"  COMPUTER WINS this round! {explanation}\n")

def display_scoreboard(scores, round_num):
    """Show the current scores."""
    print(f"  --- Scoreboard (Round {round_num}) ---")
    print(f"  You:      {scores['player']}")
    print(f"  Computer: {scores['computer']}")
    print(f"  Ties:     {scores['ties']}")
    print()

def play_game():
    """Play a full game of Rock Paper Scissors."""
    display_welcome()

    # Ask how many rounds to play
    print("How many rounds do you want to play?")
    print("  1. Best of 3")
    print("  2. Best of 5")
    print("  3. Play until I quit")

    while True:
        mode = input("Choose (1/2/3): ").strip()
        if mode in ["1", "2", "3"]:
            break
        print("Please enter 1, 2, or 3.")

    # Set up the game based on mode
    if mode == "1":
        wins_needed = 2
    elif mode == "2":
        wins_needed = 3
    else:
        wins_needed = None  # Unlimited mode

    # Initialize scores
    scores = {"player": 0, "computer": 0, "ties": 0}
    round_num = 0

    # Main game loop
    while True:
        round_num += 1
        print(f"{'=' * 40}")
        print(f"  ROUND {round_num}")
        print(f"{'=' * 40}")

        # Get choices
        player_choice = get_player_choice()
        computer_choice = get_computer_choice()

        # Display choices
        display_choices(player_choice, computer_choice)

        # Determine and display the winner
        result = determine_winner(player_choice, computer_choice)
        display_round_result(result, player_choice, computer_choice)

        # Update scores
        if result == "player":
            scores["player"] += 1
        elif result == "computer":
            scores["computer"] += 1
        else:
            scores["ties"] += 1

        # Show the scoreboard
        display_scoreboard(scores, round_num)

        # Check if someone won the series (for best-of modes)
        if wins_needed:
            if scores["player"] >= wins_needed:
                print("*" * 40)
                print("  YOU WIN THE SERIES! Congratulations!")
                print("*" * 40)
                break
            elif scores["computer"] >= wins_needed:
                print("*" * 40)
                print("  COMPUTER WINS THE SERIES! Better luck next time!")
                print("*" * 40)
                break
        else:
            # Unlimited mode — ask to continue
            cont = input("Continue playing? (yes/no): ").lower().strip()
            if cont != "yes":
                # Show final results
                print("\n" + "=" * 40)
                print("  FINAL RESULTS")
                print("=" * 40)
                display_scoreboard(scores, round_num)

                if scores["player"] > scores["computer"]:
                    print("  Overall: YOU WIN!")
                elif scores["computer"] > scores["player"]:
                    print("  Overall: COMPUTER WINS!")
                else:
                    print("  Overall: IT'S A TIE!")
                break

# Run the game
play_game()
```

### Sample Output
```
Choose [R]ock, [P]aper, or [S]cissors: r

  You chose:      [ROCK]
  Computer chose: [SCISSORS]
  YOU WIN this round! Rock crushes Scissors!

  --- Scoreboard (Round 1) ---
  You:      1
  Computer: 0
  Ties:     0
```

### Bonus Challenges
1. Add **Rock, Paper, Scissors, Lizard, Spock** (the extended version from The Big Bang Theory)
2. Make the computer learn from your patterns (if you pick rock a lot, it starts picking paper more)
3. Add **win/loss statistics** saved to a file
4. Create a **tournament mode** with multiple players

---

## Project 4: Quiz Game

### What We'll Build
A multiple-choice quiz game with categories, score tracking, and a results summary!

### Concepts Used
- Lists of dictionaries
- Functions
- Loops
- Score tracking
- String formatting

### Complete Code

```python
# ===================================================================
# PROJECT 4: QUIZ GAME
# ===================================================================
# A fun multiple-choice quiz with different categories!
# Test your knowledge and track your scores.
# ===================================================================

def create_quiz_data():
    """
    Create the quiz questions.
    Each question is a dictionary with:
      - "question": The question text
      - "options": A list of answer choices
      - "answer": The correct answer (letter: a, b, c, or d)
      - "category": The topic category
    """
    questions = [
        {
            "question": "What is the capital of France?",
            "options": ["a) London", "b) Berlin", "c) Paris", "d) Madrid"],
            "answer": "c",
            "category": "Geography"
        },
        {
            "question": "What does CPU stand for?",
            "options": [
                "a) Central Processing Unit",
                "b) Computer Personal Unit",
                "c) Central Program Utility",
                "d) Computer Processing Unit"
            ],
            "answer": "a",
            "category": "Technology"
        },
        {
            "question": "Which planet is known as the Red Planet?",
            "options": ["a) Venus", "b) Mars", "c) Jupiter", "d) Saturn"],
            "answer": "b",
            "category": "Science"
        },
        {
            "question": "What is the result of 15 * 3?",
            "options": ["a) 30", "b) 35", "c) 45", "d) 50"],
            "answer": "c",
            "category": "Math"
        },
        {
            "question": "In Python, which keyword is used to define a function?",
            "options": ["a) function", "b) func", "c) define", "d) def"],
            "answer": "d",
            "category": "Python"
        },
        {
            "question": "What is the largest ocean on Earth?",
            "options": [
                "a) Atlantic Ocean",
                "b) Indian Ocean",
                "c) Pacific Ocean",
                "d) Arctic Ocean"
            ],
            "answer": "c",
            "category": "Geography"
        },
        {
            "question": "Which data type is used for True/False values in Python?",
            "options": ["a) str", "b) int", "c) bool", "d) float"],
            "answer": "c",
            "category": "Python"
        },
        {
            "question": "How many legs does a spider have?",
            "options": ["a) 6", "b) 8", "c) 10", "d) 12"],
            "answer": "b",
            "category": "Science"
        },
        {
            "question": "What is the square root of 144?",
            "options": ["a) 10", "b) 11", "c) 12", "d) 14"],
            "answer": "c",
            "category": "Math"
        },
        {
            "question": "Which symbol is used for comments in Python?",
            "options": ["a) //", "b) /*", "c) #", "d) --"],
            "answer": "c",
            "category": "Python"
        }
    ]

    return questions

def ask_question(question_data, question_number, total):
    """
    Display a question and get the player's answer.

    Returns:
        True if the answer is correct, False otherwise.
    """
    print(f"\n--- Question {question_number} of {total} ---")
    print(f"Category: {question_data['category']}")
    print(f"\n  {question_data['question']}\n")

    # Display the answer options
    for option in question_data["options"]:
        print(f"    {option}")

    # Get the player's answer
    while True:
        answer = input("\nYour answer (a/b/c/d): ").lower().strip()

        if answer in ["a", "b", "c", "d"]:
            break
        else:
            print("Please enter a, b, c, or d.")

    # Check if the answer is correct
    correct_answer = question_data["answer"]

    if answer == correct_answer:
        print("  CORRECT! Great job!")
        return True
    else:
        # Find the full text of the correct answer
        correct_text = question_data["options"]["abcd".index(correct_answer)]
        print(f"  WRONG! The correct answer was: {correct_text}")
        return False

def display_results(score, total, results_by_category):
    """Display the final results with detailed statistics."""
    percentage = (score / total) * 100

    print("\n" + "=" * 50)
    print("             QUIZ RESULTS")
    print("=" * 50)
    print(f"\n  Score: {score} out of {total} ({percentage:.0f}%)")

    # Progress bar
    bar_length = 20
    filled = int(bar_length * score / total)
    bar = "#" * filled + "-" * (bar_length - filled)
    print(f"  [{bar}]")

    # Rating based on percentage
    if percentage == 100:
        print("\n  PERFECT SCORE! You're a genius!")
    elif percentage >= 80:
        print("\n  EXCELLENT! You really know your stuff!")
    elif percentage >= 60:
        print("\n  GOOD JOB! You passed!")
    elif percentage >= 40:
        print("\n  NOT BAD, but there's room to improve.")
    else:
        print("\n  KEEP STUDYING! You'll do better next time!")

    # Show results by category
    print(f"\n  Results by Category:")
    for category, (correct, total_cat) in results_by_category.items():
        cat_pct = (correct / total_cat) * 100 if total_cat > 0 else 0
        print(f"    {category}: {correct}/{total_cat} ({cat_pct:.0f}%)")

    print("\n" + "=" * 50)

def play_quiz():
    """Run the quiz game."""
    print("=" * 50)
    print("         WELCOME TO THE QUIZ GAME!")
    print("=" * 50)
    print("\nAnswer multiple-choice questions to test your knowledge!")
    print("Each correct answer earns you 1 point.")

    # Get the quiz questions
    questions = create_quiz_data()

    # Shuffle the questions for variety
    import random
    random.shuffle(questions)

    # Track scores
    score = 0
    total = len(questions)

    # Track results by category
    results_by_category = {}

    # Ask each question
    for i, question_data in enumerate(questions, 1):
        category = question_data["category"]

        # Initialize category tracking if new
        if category not in results_by_category:
            results_by_category[category] = [0, 0]  # [correct, total]

        # Ask the question and check the answer
        is_correct = ask_question(question_data, i, total)

        # Update scores
        if is_correct:
            score += 1
            results_by_category[category][0] += 1

        results_by_category[category][1] += 1

        # Show running score
        print(f"  Running score: {score}/{i}")

    # Display final results
    display_results(score, total, results_by_category)

    return score, total

# Main program
while True:
    score, total = play_quiz()

    play_again = input("\nPlay again? (yes/no): ").lower().strip()
    if play_again != "yes":
        print("\nThanks for playing the Quiz Game! Keep learning!")
        break
```

### Sample Output
```
--- Question 1 of 10 ---
Category: Science

  Which planet is known as the Red Planet?

    a) Venus
    b) Mars
    c) Jupiter
    d) Saturn

Your answer (a/b/c/d): b
  CORRECT! Great job!
  Running score: 1/1
```

### Bonus Challenges
1. Add **more categories** and let the player choose which category to quiz on
2. Add a **timer** — give only 15 seconds per question
3. Save the **high scores** to a file with the player's name and date
4. Add **difficulty levels** (easy, medium, hard) with different point values
5. Add an option for **players to create their own quiz questions**

---

## Project 5: Simple Contact Book

### What We'll Build
A contact book that lets you add, search, update, delete, and save contacts to a file!

### Concepts Used
- Dictionaries
- Functions
- File handling (read/write)
- Error handling
- String methods

### Complete Code

```python
# ===================================================================
# PROJECT 5: SIMPLE CONTACT BOOK
# ===================================================================
# Store your contacts and find them easily!
# All contacts are saved to a file so they persist between sessions.
# ===================================================================

# The filename where contacts are stored
CONTACTS_FILE = "contacts.txt"

def load_contacts():
    """
    Load contacts from the file.
    Each line in the file: name|phone|email
    Returns a dictionary: {name: {"phone": ..., "email": ...}}
    """
    contacts = {}

    try:
        with open(CONTACTS_FILE, "r") as file:
            for line in file:
                line = line.strip()
                if line:  # Skip empty lines
                    parts = line.split("|")
                    # Make sure we have all 3 parts
                    if len(parts) == 3:
                        name = parts[0]
                        phone = parts[1]
                        email = parts[2]
                        contacts[name] = {
                            "phone": phone,
                            "email": email
                        }
    except FileNotFoundError:
        # File doesn't exist yet — that's fine, start fresh
        pass

    return contacts

def save_contacts(contacts):
    """Save all contacts to the file."""
    with open(CONTACTS_FILE, "w") as file:
        for name, info in contacts.items():
            file.write(f"{name}|{info['phone']}|{info['email']}\n")

def add_contact(contacts):
    """Add a new contact to the book."""
    print("\n--- Add New Contact ---")
    name = input("Name: ").strip()

    if not name:
        print("Name cannot be empty!")
        return

    # Check if contact already exists
    if name in contacts:
        print(f"A contact named '{name}' already exists!")
        overwrite = input("Overwrite? (yes/no): ").lower()
        if overwrite != "yes":
            print("Contact not added.")
            return

    phone = input("Phone: ").strip()
    email = input("Email: ").strip()

    # Add to the dictionary
    contacts[name] = {"phone": phone, "email": email}

    # Save to file immediately
    save_contacts(contacts)

    print(f"\nContact '{name}' has been saved!")

def view_all_contacts(contacts):
    """Display all contacts in a neat table."""
    if not contacts:
        print("\nNo contacts yet! Add some first.")
        return

    print(f"\n{'=' * 60}")
    print(f"  {'Name':<20} {'Phone':<18} {'Email'}")
    print(f"{'=' * 60}")

    # Sort contacts alphabetically by name
    for name in sorted(contacts.keys()):
        info = contacts[name]
        print(f"  {name:<20} {info['phone']:<18} {info['email']}")

    print(f"{'=' * 60}")
    print(f"  Total contacts: {len(contacts)}\n")

def search_contact(contacts):
    """Search for a contact by name (supports partial matching)."""
    if not contacts:
        print("\nNo contacts to search!")
        return

    search_term = input("\nSearch for: ").strip().lower()

    # Find all contacts whose name contains the search term
    results = {}
    for name, info in contacts.items():
        if search_term in name.lower():
            results[name] = info

    if results:
        print(f"\nFound {len(results)} contact(s):")
        for name, info in results.items():
            print(f"\n  Name:  {name}")
            print(f"  Phone: {info['phone']}")
            print(f"  Email: {info['email']}")
    else:
        print(f"No contacts found matching '{search_term}'.")

def update_contact(contacts):
    """Update an existing contact's information."""
    if not contacts:
        print("\nNo contacts to update!")
        return

    name = input("\nEnter the name of the contact to update: ").strip()

    if name not in contacts:
        print(f"Contact '{name}' not found!")
        return

    print(f"\nCurrent info for '{name}':")
    print(f"  Phone: {contacts[name]['phone']}")
    print(f"  Email: {contacts[name]['email']}")

    print("\n(Press Enter to keep the current value)")

    # Get new values — keep old value if user presses Enter
    new_phone = input(f"New phone [{contacts[name]['phone']}]: ").strip()
    new_email = input(f"New email [{contacts[name]['email']}]: ").strip()

    # Update only if new values were provided
    if new_phone:
        contacts[name]["phone"] = new_phone
    if new_email:
        contacts[name]["email"] = new_email

    save_contacts(contacts)
    print(f"\nContact '{name}' updated!")

def delete_contact(contacts):
    """Delete a contact from the book."""
    if not contacts:
        print("\nNo contacts to delete!")
        return

    name = input("\nEnter the name of the contact to delete: ").strip()

    if name not in contacts:
        print(f"Contact '{name}' not found!")
        return

    # Confirm deletion
    confirm = input(f"Are you sure you want to delete '{name}'? (yes/no): ").lower()
    if confirm == "yes":
        del contacts[name]
        save_contacts(contacts)
        print(f"Contact '{name}' deleted!")
    else:
        print("Deletion cancelled.")

def main():
    """Main program loop."""
    print("=" * 40)
    print("     CONTACT BOOK")
    print("=" * 40)

    # Load existing contacts from file
    contacts = load_contacts()
    print(f"Loaded {len(contacts)} contact(s).\n")

    while True:
        # Show the menu
        print("What would you like to do?")
        print("  1. Add a contact")
        print("  2. View all contacts")
        print("  3. Search for a contact")
        print("  4. Update a contact")
        print("  5. Delete a contact")
        print("  6. Quit")

        choice = input("\nChoose (1-6): ").strip()

        if choice == "1":
            add_contact(contacts)
        elif choice == "2":
            view_all_contacts(contacts)
        elif choice == "3":
            search_contact(contacts)
        elif choice == "4":
            update_contact(contacts)
        elif choice == "5":
            delete_contact(contacts)
        elif choice == "6":
            save_contacts(contacts)
            print("\nContacts saved. Goodbye!")
            break
        else:
            print("Invalid choice. Please enter 1-6.\n")

# Run the contact book
main()
```

### Sample Output
```
========================================
     CONTACT BOOK
========================================
Loaded 0 contact(s).

What would you like to do?
  1. Add a contact
  2. View all contacts
  3. Search for a contact
  4. Update a contact
  5. Delete a contact
  6. Quit

Choose (1-6): 1

--- Add New Contact ---
Name: Alice Smith
Phone: 555-1234
Email: alice@example.com

Contact 'Alice Smith' has been saved!
```

### Bonus Challenges
1. Add a **category/group** field (family, friends, work) and let users filter by group
2. Add an **export to CSV** option that creates a proper CSV file
3. Add **input validation** for phone numbers and email addresses
4. Add a **favorites** feature to mark certain contacts as favorites
5. Implement **sorting** options (by name, by date added)

---

## Project 6: Hangman Game

### What We'll Build
The classic word-guessing game! One player thinks of a word (in this case, the computer picks one), and the other player guesses letters one at a time.

### Concepts Used
- Strings and string methods
- Lists
- `while` loops
- `random.choice()`
- Conditions

### Complete Code

```python
# ===================================================================
# PROJECT 6: HANGMAN GAME
# ===================================================================
# Guess the word one letter at a time!
# But be careful — too many wrong guesses and it's game over!
# ===================================================================

import random

def get_word():
    """Choose a random word from a list of words, grouped by category."""
    # Word list organized by category
    word_categories = {
        "Animals": ["elephant", "giraffe", "penguin", "dolphin", "butterfly",
                     "crocodile", "kangaroo", "squirrel", "cheetah", "octopus"],
        "Foods": ["chocolate", "spaghetti", "strawberry", "hamburger", "pineapple",
                   "pancake", "sandwich", "broccoli", "watermelon", "cinnamon"],
        "Countries": ["australia", "brazil", "canada", "germany", "japan",
                       "mexico", "france", "iceland", "portugal", "thailand"],
        "Python": ["variable", "function", "dictionary", "boolean", "integer",
                    "string", "loop", "exception", "module", "parameter"]
    }

    # Pick a random category
    category = random.choice(list(word_categories.keys()))

    # Pick a random word from that category
    word = random.choice(word_categories[category])

    return word, category

def display_hangman(wrong_guesses):
    """
    Display the hangman figure based on the number of wrong guesses.
    The figure builds up with each wrong guess.
    """
    stages = [
        # 0 wrong guesses — empty gallows
        """
           --------
           |      |
           |
           |
           |
           |
        --------
        """,
        # 1 wrong guess — head
        """
           --------
           |      |
           |      O
           |
           |
           |
        --------
        """,
        # 2 wrong guesses — head + body
        """
           --------
           |      |
           |      O
           |      |
           |
           |
        --------
        """,
        # 3 wrong guesses — head + body + left arm
        """
           --------
           |      |
           |      O
           |     /|
           |
           |
        --------
        """,
        # 4 wrong guesses — head + body + both arms
        """
           --------
           |      |
           |      O
           |     /|\\
           |
           |
        --------
        """,
        # 5 wrong guesses — head + body + both arms + left leg
        """
           --------
           |      |
           |      O
           |     /|\\
           |     /
           |
        --------
        """,
        # 6 wrong guesses — complete figure (GAME OVER)
        """
           --------
           |      |
           |      O
           |     /|\\
           |     / \\
           |
        --------
        """
    ]

    # Show the appropriate stage
    print(stages[wrong_guesses])

def display_word(word, guessed_letters):
    """
    Display the word with guessed letters revealed and unguessed letters as underscores.
    Example: if word is "python" and guessed is ['p', 't'], show "p _ t _ _ _"
    """
    display = ""
    for letter in word:
        if letter in guessed_letters:
            display += letter + " "  # Show the letter
        else:
            display += "_ "          # Hide the letter

    return display.strip()

def play_hangman():
    """Play one round of Hangman."""
    # Get a random word and its category
    word, category = get_word()

    # Track the game state
    guessed_letters = []     # All letters the player has guessed
    wrong_guesses = 0        # Number of incorrect guesses
    max_wrong = 6            # Maximum wrong guesses allowed

    print("\n" + "=" * 40)
    print("        H A N G M A N")
    print("=" * 40)
    print(f"\nHint: The category is '{category}'")
    print(f"The word has {len(word)} letters.")
    print(f"You can make {max_wrong} wrong guesses.\n")

    # Main game loop
    while wrong_guesses < max_wrong:
        # Display the hangman figure
        display_hangman(wrong_guesses)

        # Display the current state of the word
        current_display = display_word(word, guessed_letters)
        print(f"  Word: {current_display}")
        print(f"  Guessed letters: {', '.join(sorted(guessed_letters)) if guessed_letters else 'None'}")
        print(f"  Wrong guesses remaining: {max_wrong - wrong_guesses}")

        # Get the player's guess
        guess = input("\n  Guess a letter: ").lower().strip()

        # Validate the input
        if len(guess) != 1:
            print("  Please enter exactly one letter!")
            continue

        if not guess.isalpha():
            print("  Please enter a letter (a-z)!")
            continue

        if guess in guessed_letters:
            print(f"  You already guessed '{guess}'! Try another letter.")
            continue

        # Record the guess
        guessed_letters.append(guess)

        # Check if the guess is in the word
        if guess in word:
            print(f"\n  YES! '{guess}' is in the word!")

            # Check if the player has guessed all the letters
            all_guessed = all(letter in guessed_letters for letter in word)

            if all_guessed:
                print(f"\n  {'*' * 40}")
                print(f"  *  CONGRATULATIONS! YOU WON!        *")
                print(f"  *  The word was: {word.upper():<19}*")
                print(f"  *  Wrong guesses: {wrong_guesses:<18}*")
                print(f"  {'*' * 40}\n")
                return True  # Player won
        else:
            wrong_guesses += 1
            print(f"\n  NOPE! '{guess}' is NOT in the word.")

    # If we get here, the player ran out of guesses
    display_hangman(wrong_guesses)  # Show the final hangman
    print(f"\n  {'=' * 40}")
    print(f"  GAME OVER! The word was: {word.upper()}")
    print(f"  Better luck next time!")
    print(f"  {'=' * 40}\n")
    return False  # Player lost

def main():
    """Main program with win/loss tracking."""
    wins = 0
    losses = 0

    print("""
    Welcome to HANGMAN!
    Try to guess the word one letter at a time.
    But be careful — 6 wrong guesses and it's game over!
    """)

    while True:
        # Play a round
        won = play_hangman()

        # Update stats
        if won:
            wins += 1
        else:
            losses += 1

        # Show stats
        print(f"  Record: {wins} win(s), {losses} loss(es)")

        # Ask to play again
        play_again = input("\nPlay again? (yes/no): ").lower().strip()
        if play_again != "yes":
            print(f"\nFinal record: {wins} win(s), {losses} loss(es)")
            print("Thanks for playing Hangman! Goodbye!")
            break

# Run the game
main()
```

### Sample Output
```
        H A N G M A N

Hint: The category is 'Animals'
The word has 7 letters.
You can make 6 wrong guesses.

           --------
           |      |
           |
           |
           |
           |
        --------

  Word: _ _ _ _ _ _ _
  Guessed letters: None
  Wrong guesses remaining: 6

  Guess a letter: e

  YES! 'e' is in the word!

  Word: _ _ _ _ _ _ e
  Guessed letters: e
  Wrong guesses remaining: 6

  Guess a letter: a

  NOPE! 'a' is NOT in the word.
```

### Bonus Challenges
1. Add a **two-player mode** where one player enters the word and the other guesses
2. Load words from a **text file** instead of a hardcoded list
3. Add a **scoring system** based on word length and wrong guesses
4. Add **difficulty levels** that change the number of allowed wrong guesses
5. Display a hint (the word's definition) if the player asks for one

---

## Project 7: Tic-Tac-Toe

### What We'll Build
The classic Tic-Tac-Toe game for two players on the same computer!

### Concepts Used
- 2D lists (list of lists)
- Functions
- `while` loops
- Input validation
- Conditions for checking winner

### Complete Code

```python
# ===================================================================
# PROJECT 7: TIC-TAC-TOE
# ===================================================================
# The classic game of X's and O's!
# Two players take turns placing their marks on a 3x3 grid.
# First to get 3 in a row (horizontal, vertical, or diagonal) wins!
# ===================================================================

def create_board():
    """
    Create a fresh 3x3 game board.
    Each cell starts with a space " " (empty).
    We use a list of 3 lists, each containing 3 spaces.
    """
    return [
        [" ", " ", " "],  # Row 0 (top)
        [" ", " ", " "],  # Row 1 (middle)
        [" ", " ", " "]   # Row 2 (bottom)
    ]

def display_board(board):
    """
    Display the game board in a nice format.
    Also shows position numbers for easy reference.
    """
    print()
    print("     Current Board          Position Guide")
    print()

    # Display each row of the board alongside position numbers
    for i in range(3):
        # Current board
        row = f"      {board[i][0]} | {board[i][1]} | {board[i][2]}"

        # Position guide (shows which number corresponds to which cell)
        pos_row = f"       {i*3 + 1} | {i*3 + 2} | {i*3 + 3}"

        print(f"{row}          {pos_row}")

        # Print the horizontal divider (except after the last row)
        if i < 2:
            print("     ---+---+---          ---+---+---")

    print()

def get_move(board, player):
    """
    Get a valid move from the current player.
    Players enter a number 1-9 corresponding to a position:
      1 | 2 | 3
      4 | 5 | 6
      7 | 8 | 9
    """
    while True:
        try:
            move = int(input(f"  Player {player}, enter position (1-9): "))

            # Check if the move is in valid range
            if move < 1 or move > 9:
                print("  Please enter a number between 1 and 9!")
                continue

            # Convert position number to row and column
            # Position 1 → row 0, col 0
            # Position 5 → row 1, col 1
            # Position 9 → row 2, col 2
            row = (move - 1) // 3    # Integer division gives the row
            col = (move - 1) % 3     # Remainder gives the column

            # Check if the cell is already taken
            if board[row][col] != " ":
                print("  That position is already taken! Choose another.")
                continue

            return row, col

        except ValueError:
            print("  Please enter a valid number!")

def make_move(board, row, col, player):
    """Place the player's mark (X or O) on the board."""
    board[row][col] = player

def check_winner(board, player):
    """
    Check if the given player has won.
    A player wins by getting 3 in a row:
      - Horizontally (any row)
      - Vertically (any column)
      - Diagonally (either diagonal)

    Returns True if the player has won, False otherwise.
    """
    # Check all 3 rows (horizontal)
    for row in range(3):
        if board[row][0] == board[row][1] == board[row][2] == player:
            return True

    # Check all 3 columns (vertical)
    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] == player:
            return True

    # Check diagonal (top-left to bottom-right)
    if board[0][0] == board[1][1] == board[2][2] == player:
        return True

    # Check diagonal (top-right to bottom-left)
    if board[0][2] == board[1][1] == board[2][0] == player:
        return True

    # No win found
    return False

def is_board_full(board):
    """Check if the board is completely filled (tie condition)."""
    for row in board:
        for cell in row:
            if cell == " ":
                return False  # Found an empty cell
    return True  # No empty cells found

def play_game():
    """Play one complete game of Tic-Tac-Toe."""
    # Create a fresh board
    board = create_board()

    # Player X always goes first
    current_player = "X"

    # Track the number of moves
    moves = 0

    print("\n" + "=" * 45)
    print("          TIC - TAC - TOE")
    print("=" * 45)
    print("  Player 1 is X, Player 2 is O")
    print("  Enter a number 1-9 to place your mark!")

    # Main game loop
    while True:
        # Display the current board
        display_board(board)

        # Get the current player's move
        row, col = get_move(board, current_player)

        # Place the mark on the board
        make_move(board, row, col, current_player)
        moves += 1

        # Check if the current player won
        if check_winner(board, current_player):
            display_board(board)
            print(f"  {'*' * 35}")
            print(f"  *  PLAYER {current_player} WINS! Congratulations!  *")
            print(f"  *  Game finished in {moves} moves.         *")
            print(f"  {'*' * 35}")
            return current_player

        # Check if the board is full (tie)
        if is_board_full(board):
            display_board(board)
            print("  " + "=" * 35)
            print("  IT'S A TIE! Great game by both players!")
            print("  " + "=" * 35)
            return "tie"

        # Switch to the other player
        # If current is "X", switch to "O"; if "O", switch to "X"
        if current_player == "X":
            current_player = "O"
        else:
            current_player = "X"

def main():
    """Main program with match tracking."""
    # Track wins for each player
    scores = {"X": 0, "O": 0, "tie": 0}

    print("""
    Welcome to TIC-TAC-TOE!

    Two players take turns placing X and O on the board.
    Get 3 in a row to win!
    """)

    while True:
        # Play a game
        result = play_game()

        # Update scores
        if result in scores:
            scores[result] += 1

        # Show overall scores
        print(f"\n  --- Overall Scores ---")
        print(f"  Player X: {scores['X']} win(s)")
        print(f"  Player O: {scores['O']} win(s)")
        print(f"  Ties:     {scores['tie']}")

        # Ask to play again
        play_again = input("\n  Play again? (yes/no): ").lower().strip()
        if play_again != "yes":
            print("\n  Thanks for playing Tic-Tac-Toe! See you next time!")
            break

# Run the game
main()
```

### Sample Output
```
          TIC - TAC - TOE

     Current Board          Position Guide

      X | O |               1 | 2 | 3
     ---+---+---          ---+---+---
        | X |               4 | 5 | 6
     ---+---+---          ---+---+---
        |   | O             7 | 8 | 9

  Player X, enter position (1-9): 9

  *************************************
  *  PLAYER X WINS! Congratulations!  *
  *  Game finished in 5 moves.        *
  *************************************
```

### Bonus Challenges
1. Add a **single-player mode** against the computer (start with random moves, then try to make it smarter)
2. Add a **4x4 board** variant where you need 4 in a row
3. **Color the output** using ANSI escape codes (X in red, O in blue)
4. Track **game history** and save it to a file
5. Add an **undo move** feature

---

## Project 8: Simple Password Generator

### What We'll Build
A tool that generates secure random passwords with customizable options!

### Concepts Used
- `random` module
- `string` module
- Functions with parameters
- String operations
- User input and validation

### Complete Code

```python
# ===================================================================
# PROJECT 8: SIMPLE PASSWORD GENERATOR
# ===================================================================
# Generate strong, random passwords with customizable options!
# Choose the length and what types of characters to include.
# ===================================================================

import random
import string

def generate_password(length=12, use_uppercase=True, use_lowercase=True,
                      use_digits=True, use_symbols=True):
    """
    Generate a random password with the specified options.

    Parameters:
        length:        How many characters long (default: 12)
        use_uppercase: Include A-Z (default: True)
        use_lowercase: Include a-z (default: True)
        use_digits:    Include 0-9 (default: True)
        use_symbols:   Include special characters (default: True)

    Returns:
        A random password string
    """
    # Build the character pool based on options
    characters = ""

    if use_lowercase:
        characters += string.ascii_lowercase   # abcdefghijklmnopqrstuvwxyz
    if use_uppercase:
        characters += string.ascii_uppercase   # ABCDEFGHIJKLMNOPQRSTUVWXYZ
    if use_digits:
        characters += string.digits            # 0123456789
    if use_symbols:
        characters += "!@#$%^&*()_+-=[]{}|;:,.<>?"

    # Make sure we have at least some characters to use
    if not characters:
        raise ValueError("At least one character type must be selected!")

    # Generate the password
    # We'll ensure at least one character from each selected type
    password_chars = []

    # Add at least one of each selected type
    if use_lowercase:
        password_chars.append(random.choice(string.ascii_lowercase))
    if use_uppercase:
        password_chars.append(random.choice(string.ascii_uppercase))
    if use_digits:
        password_chars.append(random.choice(string.digits))
    if use_symbols:
        password_chars.append(random.choice("!@#$%^&*()_+-=[]{}|;:,.<>?"))

    # Fill the rest with random characters from the full pool
    remaining_length = length - len(password_chars)
    for _ in range(remaining_length):
        password_chars.append(random.choice(characters))

    # Shuffle the characters so the guaranteed ones aren't always at the start
    random.shuffle(password_chars)

    # Join the list of characters into a string
    password = "".join(password_chars)

    return password

def check_password_strength(password):
    """
    Analyze a password's strength and return a rating.

    Checks:
        - Length
        - Has uppercase letters
        - Has lowercase letters
        - Has numbers
        - Has special characters
    """
    score = 0
    feedback = []

    # Check length
    if len(password) >= 16:
        score += 3
        feedback.append("Great length (16+)")
    elif len(password) >= 12:
        score += 2
        feedback.append("Good length (12+)")
    elif len(password) >= 8:
        score += 1
        feedback.append("Acceptable length (8+)")
    else:
        feedback.append("Too short (less than 8) - WEAK!")

    # Check character variety
    has_upper = any(c.isupper() for c in password)
    has_lower = any(c.islower() for c in password)
    has_digit = any(c.isdigit() for c in password)
    has_symbol = any(c in "!@#$%^&*()_+-=[]{}|;:,.<>?" for c in password)

    if has_upper:
        score += 1
        feedback.append("Has uppercase letters")
    else:
        feedback.append("Missing uppercase letters")

    if has_lower:
        score += 1
        feedback.append("Has lowercase letters")
    else:
        feedback.append("Missing lowercase letters")

    if has_digit:
        score += 1
        feedback.append("Has numbers")
    else:
        feedback.append("Missing numbers")

    if has_symbol:
        score += 2
        feedback.append("Has special characters")
    else:
        feedback.append("Missing special characters")

    # Determine overall rating
    if score >= 8:
        rating = "VERY STRONG"
    elif score >= 6:
        rating = "STRONG"
    elif score >= 4:
        rating = "MODERATE"
    elif score >= 2:
        rating = "WEAK"
    else:
        rating = "VERY WEAK"

    return rating, score, feedback

def display_password(password):
    """Display the generated password with a strength analysis."""
    print(f"\n  {'=' * 50}")
    print(f"  Generated Password: {password}")
    print(f"  Length: {len(password)} characters")
    print(f"  {'=' * 50}")

    # Check and display password strength
    rating, score, feedback = check_password_strength(password)

    # Create a visual strength bar
    bar_length = 10
    filled = min(score, bar_length)
    bar = "#" * filled + "-" * (bar_length - filled)

    print(f"\n  Strength: [{bar}] {rating}")
    print(f"\n  Analysis:")
    for item in feedback:
        print(f"    - {item}")
    print()

def get_yes_no(prompt):
    """Get a yes/no answer from the user."""
    while True:
        answer = input(prompt).lower().strip()
        if answer in ["y", "yes"]:
            return True
        elif answer in ["n", "no"]:
            return False
        print("  Please enter 'yes' or 'no'.")

def main():
    """Main program — interactive password generator."""
    print("=" * 50)
    print("     PASSWORD GENERATOR")
    print("=" * 50)
    print("\nGenerate strong, random passwords instantly!")

    while True:
        print("\nOptions:")
        print("  1. Quick generate (12 characters, all types)")
        print("  2. Custom generate (choose your options)")
        print("  3. Generate multiple passwords")
        print("  4. Check a password's strength")
        print("  5. Quit")

        choice = input("\nChoose (1-5): ").strip()

        if choice == "1":
            # Quick generation with default settings
            password = generate_password()
            display_password(password)

        elif choice == "2":
            # Custom generation
            print("\n--- Custom Password Options ---")

            # Get desired length
            while True:
                try:
                    length = int(input("  Password length (4-100): "))
                    if 4 <= length <= 100:
                        break
                    print("  Please enter a number between 4 and 100.")
                except ValueError:
                    print("  Please enter a valid number.")

            # Ask about character types
            use_lower = get_yes_no("  Include lowercase letters (a-z)? (yes/no): ")
            use_upper = get_yes_no("  Include uppercase letters (A-Z)? (yes/no): ")
            use_digits = get_yes_no("  Include numbers (0-9)? (yes/no): ")
            use_symbols = get_yes_no("  Include symbols (!@#$...)? (yes/no): ")

            # Make sure at least one type is selected
            if not any([use_lower, use_upper, use_digits, use_symbols]):
                print("  You must select at least one character type!")
                print("  Using all types as default.")
                use_lower = use_upper = use_digits = use_symbols = True

            try:
                password = generate_password(
                    length=length,
                    use_uppercase=use_upper,
                    use_lowercase=use_lower,
                    use_digits=use_digits,
                    use_symbols=use_symbols
                )
                display_password(password)
            except ValueError as e:
                print(f"  Error: {e}")

        elif choice == "3":
            # Generate multiple passwords
            try:
                count = int(input("  How many passwords? (1-20): "))
                if count < 1 or count > 20:
                    print("  Please enter between 1 and 20.")
                    continue

                length = int(input("  Password length: "))

                print(f"\n  --- {count} Generated Passwords ---")
                for i in range(count):
                    pwd = generate_password(length=length)
                    rating, _, _ = check_password_strength(pwd)
                    print(f"  {i+1}. {pwd}  [{rating}]")
                print()

            except ValueError:
                print("  Please enter valid numbers.")

        elif choice == "4":
            # Check an existing password
            password = input("  Enter a password to check: ")
            display_password(password)

        elif choice == "5":
            print("\nStay safe with strong passwords! Goodbye!")
            break

        else:
            print("  Invalid choice. Please enter 1-5.")

# Run the generator
main()
```

### Sample Output
```
==================================================
     PASSWORD GENERATOR
==================================================

Options:
  1. Quick generate (12 characters, all types)
  2. Custom generate (choose your options)
  3. Generate multiple passwords
  4. Check a password's strength
  5. Quit

Choose (1-5): 1

  ==================================================
  Generated Password: kR7#mP2xL&9n
  Length: 12 characters
  ==================================================

  Strength: [########--] VERY STRONG

  Analysis:
    - Good length (12+)
    - Has uppercase letters
    - Has lowercase letters
    - Has numbers
    - Has special characters
```

### Bonus Challenges
1. Add a **"memorable password"** mode that generates passwords like "Correct-Horse-Battery-Staple" (random words)
2. Add a **"pronounceable password"** mode that creates passwords you can actually say
3. **Save generated passwords** to an encrypted file
4. Add a **clipboard copy** feature (using the `pyperclip` module)
5. Generate **passphrases** using random words from a word list

---

## Project 9: Word Counter Tool

### What We'll Build
A tool that reads a text file and gives you detailed word statistics: word count, most common words, average word length, and more!

### Concepts Used
- File handling
- Dictionaries (for counting words)
- String methods
- Sorting
- Functions
- Error handling

### Complete Code

```python
# ===================================================================
# PROJECT 9: WORD COUNTER TOOL
# ===================================================================
# Analyze any text file and get detailed word statistics!
# Find the most common words, longest words, and more.
# ===================================================================

def create_sample_file():
    """Create a sample text file for testing the word counter."""
    sample_text = """Python is an amazing programming language. Python is used by
millions of developers around the world. Learning Python is fun and rewarding.

Python can be used for web development, data science, artificial intelligence,
and many other exciting fields. The Python community is one of the most
welcoming and helpful communities in the world.

If you are learning to code, Python is a great place to start. Python code
is easy to read and write. Many people say that Python feels like writing
in plain English. That is one of the reasons why Python is so popular.

Keep coding, keep learning, and keep building amazing things with Python!
Every line of code you write makes you a better programmer."""

    with open("sample_article.txt", "w") as file:
        file.write(sample_text)

    print("Sample file 'sample_article.txt' created!")

def read_file(filename):
    """
    Read a text file and return its content.
    Handles errors gracefully.
    """
    try:
        with open(filename, "r") as file:
            content = file.read()
        return content
    except FileNotFoundError:
        print(f"Error: File '{filename}' not found!")
        return None
    except PermissionError:
        print(f"Error: No permission to read '{filename}'!")
        return None

def count_words(text):
    """
    Count the frequency of each word in the text.
    Returns a dictionary: {word: count}
    """
    # Convert to lowercase so "Python" and "python" count as the same word
    text = text.lower()

    # Remove common punctuation marks
    for char in ".,;:!?\"'()-[]{}":
        text = text.replace(char, "")

    # Split the text into individual words
    words = text.split()

    # Count each word using a dictionary
    word_counts = {}
    for word in words:
        word = word.strip()  # Remove any extra whitespace
        if word:  # Skip empty strings
            if word in word_counts:
                word_counts[word] += 1
            else:
                word_counts[word] = 1

    return word_counts

def get_basic_stats(text):
    """Calculate basic statistics about the text."""
    # Count lines (including empty ones)
    lines = text.split("\n")
    total_lines = len(lines)
    non_empty_lines = len([line for line in lines if line.strip()])

    # Count words
    words = text.split()
    total_words = len(words)

    # Count characters
    total_chars = len(text)
    chars_no_spaces = len(text.replace(" ", "").replace("\n", ""))

    # Count sentences (rough estimate based on period, !, ?)
    sentences = 0
    for char in text:
        if char in ".!?":
            sentences += 1

    # Average word length
    if total_words > 0:
        total_word_length = sum(len(word.strip(".,;:!?\"'()-")) for word in words)
        avg_word_length = total_word_length / total_words
    else:
        avg_word_length = 0

    return {
        "total_lines": total_lines,
        "non_empty_lines": non_empty_lines,
        "total_words": total_words,
        "total_chars": total_chars,
        "chars_no_spaces": chars_no_spaces,
        "sentences": sentences,
        "avg_word_length": avg_word_length
    }

def get_top_words(word_counts, n=10):
    """Get the top N most frequent words."""
    # Sort the dictionary by count (highest first)
    sorted_words = sorted(word_counts.items(), key=lambda x: x[1], reverse=True)
    return sorted_words[:n]

def get_word_lengths(word_counts):
    """Find the shortest and longest words."""
    if not word_counts:
        return [], []

    words = list(word_counts.keys())

    # Sort by length
    words_by_length = sorted(words, key=lambda w: len(w))

    shortest = words_by_length[:5]   # 5 shortest words
    longest = words_by_length[-5:]   # 5 longest words
    longest.reverse()                # Put longest first

    return shortest, longest

def display_results(filename, stats, word_counts):
    """Display all analysis results in a beautiful format."""
    print(f"\n{'=' * 55}")
    print(f"  WORD COUNTER ANALYSIS")
    print(f"  File: {filename}")
    print(f"{'=' * 55}")

    # Basic statistics
    print(f"\n  --- Basic Statistics ---")
    print(f"  Total lines:           {stats['total_lines']}")
    print(f"  Non-empty lines:       {stats['non_empty_lines']}")
    print(f"  Total words:           {stats['total_words']}")
    print(f"  Total characters:      {stats['total_chars']}")
    print(f"  Characters (no space): {stats['chars_no_spaces']}")
    print(f"  Sentences (approx):    {stats['sentences']}")
    print(f"  Average word length:   {stats['avg_word_length']:.1f} characters")
    print(f"  Unique words:          {len(word_counts)}")

    # Top 10 most common words
    top_words = get_top_words(word_counts, 10)
    print(f"\n  --- Top 10 Most Common Words ---")
    for i, (word, count) in enumerate(top_words, 1):
        # Create a simple bar chart
        bar = "#" * count
        print(f"  {i:2d}. {word:<15} {count:3d} times  {bar}")

    # Longest and shortest words
    shortest, longest = get_word_lengths(word_counts)

    print(f"\n  --- Longest Words ---")
    for word in longest:
        print(f"    '{word}' ({len(word)} letters)")

    print(f"\n  --- Shortest Words ---")
    for word in shortest:
        print(f"    '{word}' ({len(word)} letters)")

    print(f"\n{'=' * 55}\n")

def save_report(filename, stats, word_counts):
    """Save the analysis report to a file."""
    report_filename = filename.replace(".", "_report.")
    if "." not in filename:
        report_filename = filename + "_report.txt"

    with open(report_filename, "w") as file:
        file.write(f"Word Counter Report for: {filename}\n")
        file.write(f"{'=' * 50}\n\n")

        file.write(f"Total words: {stats['total_words']}\n")
        file.write(f"Unique words: {len(word_counts)}\n")
        file.write(f"Total lines: {stats['total_lines']}\n")
        file.write(f"Average word length: {stats['avg_word_length']:.1f}\n\n")

        file.write(f"Top 20 Most Common Words:\n")
        file.write(f"{'-' * 30}\n")
        for i, (word, count) in enumerate(get_top_words(word_counts, 20), 1):
            file.write(f"{i:2d}. {word:<20} {count} times\n")

    print(f"Report saved to '{report_filename}'!")

def main():
    """Main program — interactive word counter."""
    print("=" * 50)
    print("     WORD COUNTER TOOL")
    print("=" * 50)
    print("\nAnalyze any text file for word statistics!")

    while True:
        print("\nOptions:")
        print("  1. Analyze a file")
        print("  2. Create a sample file to analyze")
        print("  3. Analyze text you type in")
        print("  4. Quit")

        choice = input("\nChoose (1-4): ").strip()

        if choice == "1":
            filename = input("Enter the filename: ").strip()
            content = read_file(filename)

            if content:
                stats = get_basic_stats(content)
                word_counts = count_words(content)
                display_results(filename, stats, word_counts)

                # Offer to save the report
                save = input("Save report to file? (yes/no): ").lower()
                if save == "yes":
                    save_report(filename, stats, word_counts)

        elif choice == "2":
            create_sample_file()

        elif choice == "3":
            print("Type or paste your text (enter a blank line to finish):")
            lines = []
            while True:
                line = input()
                if line == "":
                    break
                lines.append(line)

            if lines:
                content = "\n".join(lines)
                stats = get_basic_stats(content)
                word_counts = count_words(content)
                display_results("(typed text)", stats, word_counts)

        elif choice == "4":
            print("\nHappy analyzing! Goodbye!")
            break

        else:
            print("Invalid choice.")

# Run the word counter
main()
```

### Sample Output
```
  --- Top 10 Most Common Words ---
   1. python             9 times  #########
   2. is                 7 times  #######
   3. the                4 times  ####
   4. and                4 times  ####
   5. of                 3 times  ###
   6. to                 3 times  ###
   7. code               3 times  ###
   8. learning           2 times  ##
   9. world              2 times  ##
  10. amazing            2 times  ##
```

### Bonus Challenges
1. Add a **"stop words" filter** that removes common words (the, is, a, an, etc.) from the analysis
2. Create a **word cloud** using ASCII art (bigger text for more common words)
3. Compare **two files** and show which words are unique to each
4. Add **reading time estimate** (average reading speed is about 200-250 words per minute)
5. Analyze **sentence length** and flag very long sentences

---

## Project 10: Mini Gradebook

### What We'll Build
A complete gradebook system for teachers! Add students, record grades, calculate averages, find the top student, and save everything to a file.

### Concepts Used
- Dictionaries (nested)
- Functions
- File handling
- Error handling
- Sorting
- Statistics (average, min, max)

### Complete Code

```python
# ===================================================================
# PROJECT 10: MINI GRADEBOOK
# ===================================================================
# A complete gradebook for managing student grades!
# Add students, record scores, calculate averages, and more.
# All data is saved to a file so nothing is lost.
# ===================================================================

# The file where all gradebook data is stored
GRADEBOOK_FILE = "gradebook.txt"

def load_gradebook():
    """
    Load the gradebook from a file.

    File format: Each line is "student_name:subject1=score1,subject2=score2,..."
    Example: "Alice:Math=95,Science=88,English=92"

    Returns a dictionary:
    {
        "Alice": {"Math": 95, "Science": 88, "English": 92},
        "Bob": {"Math": 78, "Science": 85}
    }
    """
    gradebook = {}

    try:
        with open(GRADEBOOK_FILE, "r") as file:
            for line in file:
                line = line.strip()
                if not line:
                    continue  # Skip empty lines

                # Split into name and grades
                parts = line.split(":")
                if len(parts) != 2:
                    continue  # Skip malformed lines

                name = parts[0]
                grades_str = parts[1]

                # Parse the grades
                grades = {}
                if grades_str:  # If there are any grades
                    for grade_pair in grades_str.split(","):
                        if "=" in grade_pair:
                            subject, score = grade_pair.split("=")
                            try:
                                grades[subject] = float(score)
                            except ValueError:
                                pass  # Skip invalid scores

                gradebook[name] = grades

    except FileNotFoundError:
        pass  # No file yet, start fresh

    return gradebook

def save_gradebook(gradebook):
    """Save the gradebook to a file."""
    with open(GRADEBOOK_FILE, "w") as file:
        for name, grades in gradebook.items():
            # Build the grades string: "Math=95,Science=88"
            grades_str = ",".join(f"{subject}={score}" for subject, score in grades.items())
            file.write(f"{name}:{grades_str}\n")

def add_student(gradebook):
    """Add a new student to the gradebook."""
    print("\n--- Add New Student ---")
    name = input("Student name: ").strip()

    if not name:
        print("Name cannot be empty!")
        return

    if name in gradebook:
        print(f"'{name}' already exists in the gradebook!")
        return

    # Initialize the student with an empty grades dictionary
    gradebook[name] = {}
    save_gradebook(gradebook)
    print(f"Student '{name}' added successfully!")

    # Ask if they want to add grades right away
    add_now = input("Add grades now? (yes/no): ").lower().strip()
    if add_now == "yes":
        add_grades(gradebook, name)

def add_grades(gradebook, student_name=None):
    """Add or update grades for a student."""
    if not gradebook:
        print("\nNo students in the gradebook! Add a student first.")
        return

    # If no student name was provided, ask for one
    if student_name is None:
        print("\n--- Add Grades ---")
        student_name = input("Student name: ").strip()

    if student_name not in gradebook:
        print(f"Student '{student_name}' not found!")
        return

    print(f"\nAdding grades for {student_name}")
    print("(Type 'done' when finished)\n")

    while True:
        subject = input("  Subject: ").strip()
        if subject.lower() == "done":
            break

        if not subject:
            print("  Subject cannot be empty!")
            continue

        # Get the score with validation
        try:
            score = float(input(f"  Score for {subject}: "))
            if score < 0 or score > 100:
                print("  Score must be between 0 and 100!")
                continue
        except ValueError:
            print("  Please enter a valid number!")
            continue

        # Record the grade
        gradebook[student_name][subject] = score
        print(f"  Recorded: {subject} = {score}")

    save_gradebook(gradebook)
    print(f"\nGrades saved for {student_name}!")

def view_student(gradebook):
    """View detailed information for one student."""
    if not gradebook:
        print("\nNo students in the gradebook!")
        return

    name = input("\nEnter student name: ").strip()

    if name not in gradebook:
        print(f"Student '{name}' not found!")
        return

    grades = gradebook[name]

    print(f"\n{'=' * 45}")
    print(f"  Student Report: {name}")
    print(f"{'=' * 45}")

    if not grades:
        print("  No grades recorded yet.")
    else:
        # Display each subject and grade
        print(f"\n  {'Subject':<20} {'Score':>8}  {'Grade':>6}")
        print(f"  {'-' * 36}")

        for subject, score in sorted(grades.items()):
            letter = score_to_letter(score)
            # Add a visual bar
            bar_length = int(score / 5)  # Scale to 20 characters max
            bar = "#" * bar_length
            print(f"  {subject:<20} {score:>8.1f}  {letter:>6}  {bar}")

        # Calculate and display statistics
        scores = list(grades.values())
        avg = sum(scores) / len(scores)
        highest = max(scores)
        lowest = min(scores)

        print(f"\n  {'-' * 36}")
        print(f"  {'Average':<20} {avg:>8.1f}  {score_to_letter(avg):>6}")
        print(f"  {'Highest':<20} {highest:>8.1f}")
        print(f"  {'Lowest':<20} {lowest:>8.1f}")
        print(f"  {'Total Subjects':<20} {len(grades):>8}")

    print(f"\n{'=' * 45}")

def score_to_letter(score):
    """Convert a numeric score to a letter grade."""
    if score >= 90:
        return "A"
    elif score >= 80:
        return "B"
    elif score >= 70:
        return "C"
    elif score >= 60:
        return "D"
    else:
        return "F"

def view_all_students(gradebook):
    """View a summary of all students."""
    if not gradebook:
        print("\nNo students in the gradebook!")
        return

    print(f"\n{'=' * 60}")
    print(f"  GRADEBOOK SUMMARY")
    print(f"{'=' * 60}")
    print(f"\n  {'Student':<20} {'Subjects':>10} {'Average':>10} {'Grade':>8}")
    print(f"  {'-' * 50}")

    # Calculate and display each student's summary
    student_averages = []

    for name in sorted(gradebook.keys()):
        grades = gradebook[name]
        num_subjects = len(grades)

        if grades:
            avg = sum(grades.values()) / len(grades)
            letter = score_to_letter(avg)
            student_averages.append((name, avg))
        else:
            avg = 0
            letter = "N/A"

        print(f"  {name:<20} {num_subjects:>10} {avg:>10.1f} {letter:>8}")

    print(f"  {'-' * 50}")
    print(f"  Total students: {len(gradebook)}")

    # Show class average
    if student_averages:
        class_avg = sum(avg for _, avg in student_averages) / len(student_averages)
        print(f"  Class average:  {class_avg:.1f} ({score_to_letter(class_avg)})")

    print(f"\n{'=' * 60}")

def find_top_students(gradebook):
    """Find and display the top students by average score."""
    if not gradebook:
        print("\nNo students in the gradebook!")
        return

    # Calculate averages for students who have grades
    student_averages = []
    for name, grades in gradebook.items():
        if grades:
            avg = sum(grades.values()) / len(grades)
            student_averages.append((name, avg))

    if not student_averages:
        print("\nNo grades recorded yet!")
        return

    # Sort by average (highest first)
    student_averages.sort(key=lambda x: x[1], reverse=True)

    print(f"\n{'=' * 45}")
    print(f"  TOP STUDENTS")
    print(f"{'=' * 45}")

    # Show ranking with medals for top 3
    medals = ["1st", "2nd", "3rd"]

    for i, (name, avg) in enumerate(student_averages):
        if i < 3:
            rank = medals[i]
        else:
            rank = f"{i+1}th"

        letter = score_to_letter(avg)
        bar = "#" * int(avg / 5)
        print(f"  {rank:>4}  {name:<20} {avg:.1f} ({letter})  {bar}")

    print(f"\n{'=' * 45}")

def subject_report(gradebook):
    """Show a report organized by subject instead of by student."""
    if not gradebook:
        print("\nNo students in the gradebook!")
        return

    # Collect all grades by subject
    subject_data = {}

    for name, grades in gradebook.items():
        for subject, score in grades.items():
            if subject not in subject_data:
                subject_data[subject] = []
            subject_data[subject].append((name, score))

    if not subject_data:
        print("\nNo grades recorded yet!")
        return

    print(f"\n{'=' * 55}")
    print(f"  SUBJECT REPORT")
    print(f"{'=' * 55}")

    for subject in sorted(subject_data.keys()):
        scores_list = subject_data[subject]

        # Sort students by score (highest first)
        scores_list.sort(key=lambda x: x[1], reverse=True)

        # Calculate subject statistics
        scores_only = [s for _, s in scores_list]
        avg = sum(scores_only) / len(scores_only)
        highest = max(scores_only)
        lowest = min(scores_only)

        print(f"\n  --- {subject} ---")
        print(f"  Average: {avg:.1f} | Highest: {highest:.1f} | Lowest: {lowest:.1f}")
        print(f"  Students:")

        for name, score in scores_list:
            letter = score_to_letter(score)
            print(f"    {name:<20} {score:.1f} ({letter})")

    print(f"\n{'=' * 55}")

def delete_student(gradebook):
    """Remove a student from the gradebook."""
    if not gradebook:
        print("\nNo students in the gradebook!")
        return

    name = input("\nEnter the name of the student to remove: ").strip()

    if name not in gradebook:
        print(f"Student '{name}' not found!")
        return

    confirm = input(f"Are you sure you want to delete '{name}' and all their grades? (yes/no): ")
    if confirm.lower() == "yes":
        del gradebook[name]
        save_gradebook(gradebook)
        print(f"Student '{name}' has been removed.")
    else:
        print("Deletion cancelled.")

def main():
    """Main program loop for the gradebook."""
    print("=" * 50)
    print("         MINI GRADEBOOK")
    print("=" * 50)

    # Load existing data
    gradebook = load_gradebook()
    print(f"\nLoaded {len(gradebook)} student(s) from file.\n")

    while True:
        # Display the menu
        print("What would you like to do?")
        print("  1.  Add a student")
        print("  2.  Add/update grades")
        print("  3.  View a student's report")
        print("  4.  View all students")
        print("  5.  Top students ranking")
        print("  6.  Subject report")
        print("  7.  Delete a student")
        print("  8.  Quit")

        choice = input("\nChoose (1-8): ").strip()

        if choice == "1":
            add_student(gradebook)
        elif choice == "2":
            add_grades(gradebook)
        elif choice == "3":
            view_student(gradebook)
        elif choice == "4":
            view_all_students(gradebook)
        elif choice == "5":
            find_top_students(gradebook)
        elif choice == "6":
            subject_report(gradebook)
        elif choice == "7":
            delete_student(gradebook)
        elif choice == "8":
            save_gradebook(gradebook)
            print("\nAll data saved. Goodbye!")
            break
        else:
            print("Invalid choice. Please enter 1-8.\n")

# Run the gradebook
main()
```

### Sample Output
```
=============================================
  Student Report: Alice
=============================================

  Subject               Score    Grade
  ------------------------------------
  English                92.0       A  ##################
  Math                   95.0       A  ###################
  Science                88.0       B  #################

  ------------------------------------
  Average                91.7       A
  Highest                95.0
  Lowest                 88.0
  Total Subjects            3

=============================================
```

### Bonus Challenges
1. Add a **weighted grades** feature (e.g., final exam counts more than homework)
2. Generate a **report card** as a text file for each student
3. Add **assignment tracking** (not just subjects, but individual assignments within each subject)
4. Add a **graph feature** that shows a student's progress over time using ASCII art
5. Import/export the gradebook as a **CSV file** that can be opened in Excel

---

## What's Next?

You've just built 10 complete Python projects! Here's what you can do next:

1. **Combine projects** — Add a quiz game to the gradebook, or add file saving to the hangman game
2. **Add GUIs** — Learn `tkinter` to add graphical interfaces to your projects
3. **Learn about modules** — Explore the Python standard library (`os`, `json`, `datetime`, `math`)
4. **Try web development** — Learn Flask or Django to build websites with Python
5. **Explore data science** — Learn pandas and matplotlib to work with data
6. **Build bigger projects** — A chat bot, a web scraper, a simple game engine

**Remember:** The best way to learn programming is to BUILD THINGS. Take these projects, modify them, break them, fix them, and make them your own. Every bug you fix makes you a better programmer!

**You're a Python programmer now. Go build something amazing!**
