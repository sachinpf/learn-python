# ROADMAP — Learn Python: The Complete Reference

A 5-part curriculum that takes anyone — especially absolute beginners in Grades 3–10 — from "what is a computer?" to building real AI applications.

| Part | Title | Status | What it does |
|---|---|---|---|
| 1 | Foundations | ✅ Built (needs beginner-gap patches) | 12 lessons. Syntax + first projects. |
| 2 | Practice & Curiosity | 🚧 Next | Exercises, themed packs, "did you know?", challenges. |
| 3 | Games | 📋 Planned | Terminal games that reinforce Parts 1–2. |
| 4 | Basics of AI | 📋 Planned | What AI actually is; tiny hand-coded examples. |
| 5 | AI Applications | 📋 Planned | Build chatbots, classifiers, recommenders. |

Every concept introduced shows the Marathi term in parentheses on first use, e.g. *variable (चल)*. See `.claude/STYLE.md` for the canonical glossary.

---

## Part 1 — Foundations (existing, in `01_foundations/`)

12 lessons, already written. Style: friendly, example-heavy, exercises at end of each lesson.

Coverage:
1. Hello, World
2. Variables & input
3. Numbers & math
4. Strings
5. Conditions (`if`/`elif`/`else`)
6. Loops (`for`/`while`)
7. Lists
8. Tuples, dictionaries, sets
9. Functions
10. File handling
11. Error handling
12. Mini projects (10 of them)

**Pending patches** (see `.claude/NOTES.md` for full list): clarify `=` direction in Lesson 02, add "when to use which" table for `if`/`elif`/`else` in Lesson 05, explain *why* `range(5)` stops at 4 in Lesson 06, reframe Lesson 11 to present errors as helpful information, etc.

---

## Part 2 — Practice & Curiosity (next to build)

Lives in `02_practice/`. Four parallel formats, each in its own subfolder.

### 2A. `02_practice/exercises/` — graded exercise sets per Part 1 topic

One file per Part 1 lesson: `exercises_02_variables.md`, `exercises_05_conditions.md`, etc.

Each file:
- 20–40 problems, sorted easy → medium → hard → "stretch"
- Each problem: prompt → expected output → collapsible solution (`<details>` block)
- Roughly: 10 easy (verbatim drill), 15 medium (slight twists), 8 hard (multi-step), 5 stretch (open-ended)
- Solutions include a one-line comment explaining the trick, not just the code

### 2B. `02_practice/packs/` — themed problem packs

Cross-topic packs that tell a story. Each pack has 8–12 problems progressing in difficulty.

Initial packs:
1. **Math Wizard Pack** — `pack_math_wizard.md` — prime checkers, Fibonacci, factorial, base conversions, simple cryptography
2. **Word Detective Pack** — `pack_word_detective.md` — palindromes, anagrams, word ladders, secret-code makers
3. **Data Explorer Pack** — `pack_data_explorer.md` — CSV crunching, finding patterns, simple statistics on lists/dicts
4. **Pattern Maker Pack** — `pack_pattern_maker.md` — ASCII art via loops, fractal-ish shapes, drawing letters with `*`
5. **Number Tricks Pack** — `pack_number_tricks.md` — guess my number, magic squares, math illusions

### 2C. `02_practice/did_you_know/` — short curiosity essays

1–2 page reads that explain *why* things are the way they are. No exercises — pure spark.

Initial topics:
- `dyk_why_indentation.md` — why Python uses whitespace where other languages use `{}`
- `dyk_what_is_a_byte.md` — bits, bytes, and what your computer really stores
- `dyk_how_print_works.md` — what happens between `print("hi")` and pixels on screen
- `dyk_why_zero_indexed.md` — why lists start at 0, not 1
- `dyk_how_python_runs.md` — interpreter vs compiler, the gentle version
- `dyk_what_is_unicode.md` — emojis, Marathi, English — all the same to Python
- `dyk_random_isnt_random.md` — pseudo-randomness in plain language
- `dyk_what_is_an_algorithm.md` — recipes, but for computers
- `dyk_why_bugs_are_called_bugs.md` — Grace Hopper, the original moth, history of debugging
- `dyk_how_files_actually_work.md` — what "saving" actually does to a disk

### 2D. `02_practice/challenges/` — mini-challenges with progressive hints

One puzzle per file. Format:
- **The puzzle** — short, clear
- **Hint 1** (collapsible) — gentle nudge
- **Hint 2** (collapsible) — more specific
- **Hint 3** (collapsible) — almost the answer
- **Solution** (collapsible) — full code with comments
- **Why this matters** — one paragraph on what the puzzle teaches

Aim for 50 challenges in total, numbered `challenge_001_..md` upward. Roughly grouped:
- 001–015: pure Part 1 skill drills
- 016–030: classic CS puzzles (FizzBuzz, palindrome check, Caesar cipher)
- 031–045: real-world micro-problems (password strength, simple grading, etc.)
- 046–050: stretch puzzles that hint at Parts 3/4 (e.g., a tiny rule-based AI)

---

## Part 3 — Games (planned)

Terminal-first games in `03_games/`. Each game = one folder with the code, a `README.md`, and a "Now you try" extension list.

Planned games (rough difficulty order):
1. Number Guessing (variables, loops, `random`)
2. Rock Paper Scissors (functions, conditions)
3. Mad Libs Deluxe (extended from Part 1 mini-project)
4. Hangman (lists, strings, state)
5. Tic-Tac-Toe (2D lists, win-checking logic)
6. Wordle Clone (string comparison, color codes in terminal)
7. Snake (terminal graphics with `curses`)
8. Minesweeper (recursion + 2D grids)
9. Quiz Master (file I/O for question banks)
10. Text Adventure ("you are in a dark room…")

Optional **Part 3b** (`03_games/with_pygame/`) — graphical games for kids who want to install `pygame`. Pong, Brick Breaker, Asteroids. Kept separate so the core Part 3 needs zero extra installs.

---

## Part 4 — Basics of AI (planned)

`04_ai_basics/`. Concept-first. No frameworks until the last lesson. Every example runs on a regular laptop in <1 second.

Outline:
1. **What is intelligence anyway?** — humans vs animals vs computers
2. **Patterns are everywhere** — let kids find them in numbers, words, pictures
3. **Rules-based "AI"** — build a fruit classifier with `if` statements; watch it break on new fruits
4. **Data is the new code** — what "training data" means, why bad data = bad AI
5. **The simplest learner: nearest neighbor** — by hand, then in 10 lines of Python
6. **A first real model: decision trees** — using `scikit-learn`, treated as a black box
7. **Why does it work?** — peek under the hood (one diagram, no math)
8. **What can go wrong?** — bias, overfitting, "garbage in, garbage out" (kid-level examples)
9. **Mini-project: classify your own data** — kid collects their own data (favorite foods, weather, anything), trains a classifier
10. **What's next?** — preview of Part 5

---

## Part 5 — AI Applications (planned)

`05_ai_apps/`. Project-driven, like a bigger Part 1 Lesson 12. 5–7 projects.

Planned projects:
1. **Smart Chatbot** — uses the Claude API; kid can give it a personality
2. **Image Classifier** — cats vs dogs (or rocks vs leaves — kid's choice) using a pre-trained model
3. **Song Recommender** — given your favorites, suggest more (collaborative filtering, kid-friendly version)
4. **Sentiment Detector** — read a movie review, guess thumbs-up or thumbs-down
5. **Speech-to-Text Notebook** — speak, get text, save it
6. **Generative Art** — text-to-image API; explore prompts
7. **Build Your Own** — capstone: kid picks the problem, we walk through how to scope it

Each project: what it does → why it's cool → setup → code → "make it yours" challenges.

---

## Cross-cutting conventions

- **Filename pattern**: `lowercase_with_underscores.md`. Numbers padded to 2 digits where they form a sequence.
- **Lesson length**: aim for 15–35 KB per markdown file. Anything bigger gets split.
- **Code in examples**: always include the expected output below the code block.
- **Marathi terms**: parenthetical on first use only per lesson. Glossary in `.claude/STYLE.md`.
- **No external dependencies in Part 1–3 core**: anything beyond the Python standard library is opt-in.
- **Each lesson/file ends with**: "What's next" pointer to the next file.
