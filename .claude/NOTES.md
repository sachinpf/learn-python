# NOTES — Design Decisions & Open Questions

This file captures *why* the curriculum is shaped the way it is, and what we still need to decide. Edit freely; it's not user-facing.

---

## Audience

- **Grades 3–10 throughout all 5 parts** (decided 2026-05-17). Even Parts 4–5 (AI basics, AI applications) must remain accessible to a curious 10-year-old. That means *concept-first* AI, not heavy math. A 12-year-old should be able to build a chatbot in Part 5.
- The owner (Sachin) is a Marathi-speaking parent/teacher. The curriculum is being built so anyone — not just his own kids — can become an expert.

## Marathi integration: inline bilingual key terms only

- On **first use** in a lesson, technical terms get Marathi in parentheses: `variable (चल)`, `function (फंक्शन)`.
- We do **not** translate full sentences or write parallel Marathi lessons. Keeps the file size and maintenance reasonable.
- The canonical translation list lives in `.claude/STYLE.md` — always check there before inventing a new translation. Consistency matters more than perfect translation.

## Beginner-gap audit (2026-05-17)

A sweep of Part 1 turned up ~35 spots where an absolute beginner could get stuck. Highlights — full list below. We will **not** rewrite Part 1 immediately; instead, we'll address these via:
1. Small targeted patches to Part 1 lessons (clarifying paragraphs, "common mistake" callouts).
2. Part 2 exercise sets that drill each gap explicitly.

### Critical gaps to patch in Part 1

| Lesson | Gap | Fix approach |
|---|---|---|
| 02 | `=` direction (value flows right-to-left), reassignment doesn't conflict | Add "the arrow analogy" callout + 3-line example |
| 02 | `input()` always returns a string — *why* | One paragraph: "Python can't read your mind" |
| 04 | Indexing starts at 0 — *why* | Brief note: "0 is the offset from the start" |
| 05 | `if` vs `elif` vs nested `if` — *when to use which* | New "Choosing the right shape" table |
| 05 | Indentation has meaning (not just style) | Sidebar: "Python uses spacing where other languages use `{}`" |
| 06 | `range(5)` stops at 4 — *why* | "Half-open range" note + visual |
| 06 | `for` vs `while` — when each fits | Decision table |
| 07 | Lists are mutable; assignment shares the list | "Two names, one list" diagram |
| 09 | `return` vs `print()` — when each | "The function gives you something vs. shows you something" |
| 10 | `"w"` mode deletes existing content | Bold warning at top of file-modes section |
| 11 | Errors are information, not failures | Reframe lesson intro |

### Lower-priority gaps (handle via Part 2 exercises, not Part 1 edits)

- escape sequences (`\n`, `\t`) — exercise set in Part 2
- `enumerate()`, `zip()` motivation — themed pack in Part 2
- tuple unpacking — exercise set
- dictionary `.get()` vs `[]` — exercise set
- raising vs catching exceptions — exercise set
- `random` module — introduced naturally in Part 3 (games)

## Part 2 philosophy

Four exercise types, each serving a different muscle:

1. **Graded sets** — `exercises_05_conditions.md` etc. 20–40 problems per lesson, easy → hard, with full solutions. Pure drill. Builds fluency.
2. **Themed packs** — `pack_math_wizard.md`, `pack_word_detective.md`. Cross-topic. Tell a story. Builds *transfer*: applying what you know in a new context.
3. **Did-you-know deep-dives** — `dyk_why_indentation.md`, `dyk_what_is_a_byte.md`. 1–2 page essays. Builds curiosity and explains the *why* behind syntax.
4. **Mini-challenges with hints** — `challenge_001.md`. One puzzle per file, with progressive hint reveal, then solution. Builds problem-solving muscle (the hardest skill to teach).

## Part 3 philosophy (games)

Games motivate retention. Each game in Part 3 should:
- Be playable in a terminal (no GUI library needed for Part 3 — keep dependency surface tiny)
- Reinforce 2–3 concepts from Parts 1–2
- Have a "Now you try" extension at the end (e.g., "Add a difficulty setting")

Order matters: simpler games first (Number Guessing, Rock Paper Scissors) before state-heavy ones (Tic-Tac-Toe, Hangman). Saving graphical games (Pygame) for **Part 3b** or a sub-section so kids who don't want to install extra libraries can still finish Part 3.

## Part 4 philosophy (AI basics)

"AI basics" for a 10-year-old does **not** mean linear algebra or backprop math. It means:
- What is a pattern? How do computers spot one?
- What is "training data"? Why does it matter what's in it?
- What's the difference between rules-based code and learning-from-examples code?
- A tiny hand-coded "AI" (e.g., classify fruits by weight & color using `if` statements) → show how this breaks → motivate why you'd want a machine to learn rules itself.
- One simple library example (e.g., `scikit-learn` for classifying flowers) — but treated as a magical box first, then peeled open in late Part 4.

We do NOT use TensorFlow/PyTorch in Part 4. Save that for Part 5 if at all.

## Part 5 philosophy (AI applications)

Project-driven, like Part 1 Lesson 12 but bigger. Build things that feel real:
- A chatbot (using the Claude API or similar)
- An image classifier (cats vs dogs with a pre-trained model)
- A recommender (your favorite songs → suggest more)
- A sentiment analyzer (good review or bad review?)
- A simple voice assistant (uses speech-to-text)

Each project: **what it does** → **why it's useful** → **the code** → **how to extend it**.

## Open questions

- **Marathi script in code comments?** Currently no — comments stay English so any reader can run the code. Marathi only in prose. Confirm if this is wrong.
- **Exercise solutions: inline or separate file?** Leaning inline (under a `<details>` collapsible) so a learner has to *choose* to peek. Decide before writing Part 2.
- **Numbering scheme for Part 2 files**: `exercises_NN_topic.md` matches Part 1's pattern. But themed packs and did-you-knows don't map 1-to-1 to lessons. Probably: `exercises_NN_*` for graded, `pack_*` for themed, `dyk_*` for deep-dives, `challenge_NNN_*` for puzzles.
- **PyCharm assumption**: Part 1 assumes PyCharm. Parts 2-5 should be IDE-agnostic so people on VS Code / Thonny / online editors aren't excluded. The setup steps belong in Part 1 only.
- **License?** Not set. If this is going public eventually, add a LICENSE file. CC-BY-SA likely fits an educational resource.
