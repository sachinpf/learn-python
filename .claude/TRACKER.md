# TRACKER — Where We Are, What's Next

**Last updated:** 2026-05-17 (Session 2)

This is the "start here" file for any new session on this curriculum. It captures **current state** and **next actions**. The master plan lives in `ROADMAP.md`; style rules in `STYLE.md`; design rationale in `NOTES.md`.

---

## TL;DR — pick up here next time

> **Two tracks open. Pick one:**
>
> **Track 1 (preferred — unblocks the most work):** Sachin reviews `01_foundations/GLOSSARY.md`. ~85 Marathi definitions drafted by Claude; many need correcting. Once corrected, Phases 3 + 4 (Part 1 + Part 2 retrofits, 18 files total) can start.
>
> **Track 2 (independent — can run in parallel):** Continue scaling exercises with **`exercises_03_numbers_and_math.md`** (operators, `%`, `//`, `**`, order of operations, `math` module). Use the new full-form gloss format from the start.
>
> Reference templates: `exercises_02_variables.md` (mid-weight, 30 problems) and `exercises_05_conditions.md` (canonical, 30 problems).

---

## 📊 Session 2 digest

What was built in this session (2026-05-17):

| Artifact | Lines / size | Purpose |
|---|---|---|
| `02_practice/packs/pack_word_detective.md` | ~430 lines | First themed-pack sample (11 cases) |
| `02_practice/did_you_know/dyk_why_indentation.md` | ~180 lines | First did-you-know essay (5-min read) |
| `02_practice/challenges/challenge_001_fizzbuzz.md` | ~290 lines | First mini-challenge sample |
| `02_practice/exercises/exercises_01_hello_world.md` | ~530 lines | Graded exercises, 22 problems |
| `02_practice/exercises/exercises_02_variables.md` | ~720 lines | Graded exercises, 30 problems |
| `01_foundations/GLOSSARY.md` | ~170 lines | Single source of truth for Marathi terms + definitions |
| `.claude/STYLE.md` (edit) | small | Marathi gloss format rule updated |
| `.claude/TRACKER.md` (this file) | ~175 lines | State tracker, kept current |

Roughly **2,300 lines** of new curriculum content, plus the GLOSSARY infrastructure that will guide every future lesson edit.

---

## ✅ Completed

### Structure & planning (Session 1)
- [x] Renamed `part_1/` → `01_foundations/`
- [x] Reserved naming scheme: `01_foundations/`, `02_practice/`, `03_games/`, `04_ai_basics/`, `05_ai_apps/`
- [x] Top-level `README.md` rewritten with 5-part roadmap
- [x] `.claude/ROADMAP.md` — master plan, all 5 parts, detailed Part 2 outline
- [x] `.claude/STYLE.md` — voice rules + canonical Marathi glossary (~80 terms)
- [x] `.claude/NOTES.md` — design decisions + full beginner-gap audit (~35 gaps)

### Part 1 patches (Session 1)
- [x] Lesson 02 (Variables): `=` arrow diagram, reassignment doesn't conflict, `x = x + 5` trick, why `input()` returns string, Marathi terms
- [x] Lesson 05 (Conditions): **"Which Shape Do I Use?"** decision table, indentation-why sidebar, `elif`-vs-multiple-`if` trap, Marathi terms
- [x] Lesson 06 (Loops): expanded "why `range(5)` stops at 4", Golden Rule of `while`, Marathi terms
- [x] Lesson 07 (Lists): mutability framing, "two names, one list" diagram, Marathi terms
- [x] Lesson 09 (Functions): print-vs-return shouting-vs-paper analogy, parameter-vs-argument mnemonic, Marathi terms
- [x] Lesson 10 (Files): ⚠️ `"w"` deletes-everything warning at top, three-read-methods motivation, Marathi terms
- [x] Lesson 11 (Errors): reframed intro ("errors are information"), syntax-vs-runtime timing, when-to-use-try-except, Marathi terms
- [x] `01_foundations/README.md` updated to mention Marathi convention + new callouts

### Part 2 scaffolding (Session 1)
- [x] `02_practice/` folder structure created (`exercises/`, `packs/`, `did_you_know/`, `challenges/`)
- [x] `02_practice/README.md` — explains the four formats
- [x] `02_practice/exercises/README.md` — index of all 12 future exercise files
- [x] **`02_practice/exercises/exercises_05_conditions.md`** — first sample file (30 problems, 1038 lines). **This is the template to match for the other 11 lessons.**

### Part 2 format previews (Session 2)
- [x] **`02_practice/packs/pack_word_detective.md`** — themed pack sample (11 cases: long-word, bookends, vowel census, mirror, palindrome, letter frequency, anagrams, hidden word, Caesar cipher, anagram squad, build-your-own-tool). Cross-topic, uses Lessons 4–9.
- [x] **`02_practice/did_you_know/dyk_why_indentation.md`** — curiosity essay sample (5-min read, no exercises). History of indentation-as-syntax, the ABC language, tabs-vs-spaces trap, "code is read more than written" framing.
- [x] **`02_practice/challenges/challenge_001_fizzbuzz.md`** — mini-challenge sample. Problem → 3 progressive hints → solution → the classic ordering trap → 3 stretch goals → "why this matters". Template for all future challenges.

### Marathi-definitions initiative (Session 2)
- [x] **`01_foundations/GLOSSARY.md`** — Phase 1. Single source of truth for every technical term. 8 categorised tables (Core, Values, Operations, Control flow, Functions, Errors, AI, Part 2 extras). ~85 terms × English + Marathi + Marathi definition + first-lesson column. **Marathi definitions are draft only — Sachin must review and correct.**
- [x] **`.claude/STYLE.md`** — Phase 2. Marathi integration rules updated: new gloss format is `term (Marathi — definition)` on every first-use; GLOSSARY.md cited as canonical source.

---

## 🚧 Next up (in priority order)

### A. Scale Part 2 exercises (matches the sample's format)
Write the remaining graded-exercise files. Each ~25-30 problems, same easy/medium/hard/stretch structure as `exercises_05_conditions.md`. Each problem: prompt → expected output → collapsible solution with one-line teaching note. Use ONLY concepts introduced up to that lesson's number (e.g., `exercises_03_*.md` may not use loops or lists).

Order (suggested — easiest to write first, building momentum):
- [x] `exercises_01_hello_world.md` — print, comments, strings vs numbers ✅ Session 2 (22 problems, ~530 lines)
- [x] `exercises_02_variables.md` — types, input, casting, f-strings ✅ Session 2 (30 problems, ~720 lines). Drills input-returns-string trap (P12–15) and value-copy-on-assignment surprise (P27).
- [x] `exercises_05_conditions.md` — `if`/`elif`/`else`, boolean logic ✅ Session 1 (30 problems, 1038 lines — canonical template).
- [ ] `exercises_03_numbers_and_math.md` — operators, `%`, `//`, `**`, order of operations, `math` module ← **NEXT**
- [ ] `exercises_04_strings.md` — indexing, slicing, methods, concatenation
- [ ] `exercises_06_loops.md` — for, while, range, break/continue, nested loops
- [ ] `exercises_07_lists.md` — methods, slicing, looping over, the "two names" trap
- [ ] `exercises_08_tuples_and_dictionaries.md` — when to use which, dict methods, sets
- [ ] `exercises_09_functions.md` — return vs print, parameters, scope, docstrings
- [ ] `exercises_10_file_handling.md` — reading/writing, `with`, the `"w"` trap
- [ ] `exercises_11_error_handling.md` — try/except, when to use it, raise
- [ ] `exercises_12_mini_projects.md` — project extensions / variations

**Progress:** 3 of 12 exercise files done (Session 2).

### B. Marathi-definitions retrofit (BLOCKED on Sachin's review of GLOSSARY.md)
After Sachin reviews and corrects `01_foundations/GLOSSARY.md`:

**Phase 3 — Part 1 retrofit** (12 files):
- [ ] Lessons 02, 05, 06, 07, 09, 10, 11 — already have short-form glosses; upgrade each first-use to `term (Marathi — definition)` using the corrected GLOSSARY.md.
- [ ] Lessons 01, 03, 04, 08, 12 — no Marathi yet. Full pass: identify every technical term, gloss it on first use with the full form.

**Phase 4 — Part 2 retrofit** (6 files): same upgrade for `exercises_01_hello_world.md`, `exercises_02_variables.md`, `exercises_05_conditions.md`, `pack_word_detective.md`, `dyk_why_indentation.md`, `challenge_001_fizzbuzz.md`. New Part 2 files written from this point onwards should use the new format directly.

### C. Scale the other Part 2 formats (after format previews are confirmed)
Now that one sample of each format exists, the next round is **producing more** of each:
- [ ] More **themed packs** — Math Wizard (primes, Fibonacci, factorials), Data Explorer (CSV crunching), Pattern Maker (ASCII art), Number Tricks (guess my number, magic squares). See `02_practice/README.md` for the full starter list.
- [ ] More **did-you-know** essays — candidates: "Why do lists start at 0?", "What is a byte, really?", "How does `print()` put text on screen?", "Why are bugs called bugs?"
- [ ] **`challenge_002`** onwards — guessing game (uses `random`), Hangman, simple cipher decoder, number-pattern puzzles. Build one new challenge per session in early Part 2.

### D. Remaining Part 1 beginner-gap patches (lower priority — defer to Part 2 exercises)
Tracked in `.claude/NOTES.md`. Smaller gaps that can be drilled via exercises rather than lesson edits:
- escape sequences `\n` `\t` motivation
- `enumerate()`, `zip()` motivation
- tuple unpacking
- dictionary `.get()` vs `[]`
- raising vs catching exceptions
- `random` module (will introduce naturally in Part 3 games)

### E. Future parts (after Part 2 has critical mass)
- [ ] Part 3 — terminal games (see ROADMAP for planned list)
- [ ] Part 4 — AI basics (concept-first, no heavy math)
- [ ] Part 5 — AI applications (chatbot, classifier, recommender, etc.)

---

## 🗒️ Open decisions / things to confirm

Confirm before they bite. Items move to "Settled" below once resolved.

**Active:**
- **🔴 BLOCKER — Review `01_foundations/GLOSSARY.md`.** ~85 Marathi definitions drafted by Claude; many will need fixing. Look for: clumsy phrasing, wrong word choices, definitions a 10-year-old wouldn't understand. Specific lines I flagged as least confident (Session 2):
  - `dictionary (शब्दकोश — key–value जोड्यांचा संग्रह)` — English `key-value` mid-Marathi feels off
  - `scope (स्कोप / व्याप्ती — चलाची दृश्यमानता असलेला कोडचा भाग)` — `दृश्यमानता` heavy for a 10-year-old
  - `module (मोड्यूल — कोडंची स्वतंत्र फाइल...)` — `कोडंची` vs `कोडाची`?
  - `function (फंक्शन — नाव दिलेला एक काम करणारा कोडंचा गट)` — same `कोडंचा` vs `कोडाचा`
  - `code (कोड — प्रोग्रामिंग भाषेत लिहिलेला मजकूर)` — `मजकूर` may be too generic
  
  Once corrected, Phase 3/4 retrofit becomes mechanical (find first-use of each term, swap in the new gloss).
- **Review the three Part 2 format samples** (pack / did-you-know / challenge). Built in Session 2 but not yet skimmed. Worth confirming the structure feels right before producing more of each.
- **PyCharm assumption**: only Part 1 assumes PyCharm. Parts 2+ are editor-agnostic. Should the top-level README clarify this more prominently?
- **License**: not set. If sharing publicly, add a LICENSE file (CC-BY-SA is a common fit for educational resources).

**Settled (kept here for the record):**
- ~~Solution visibility (`<details>` collapsibles)~~ — working across 5 Part 2 files; keep.
- ~~Marathi in code comments~~ — confirmed NO; English-only comments so code runs universally.
- ~~Exercise file size~~ — variable is fine: small file (L01, 22 problems) for narrow lessons; ~30 problems for fuller ones. No need to enforce a single size.
- ~~Marathi gloss format~~ — decided (Session 2): always `term (Marathi — definition)` on first-use per lesson. Canonical definitions live in `01_foundations/GLOSSARY.md`.
- ~~Marathi glossary additions from Part 2 files~~ — folded into GLOSSARY.md under "Part 2 extras" (tab, triple quotes, string-adjacency, perimeter, area, palindrome, anagram, Caesar cipher).

---

## 🗺️ Where to find things

| What you want | Where it lives |
|---|---|
| Current state + next actions | **THIS FILE** (`.claude/TRACKER.md`) |
| Master plan, all 5 parts | `.claude/ROADMAP.md` |
| Voice rules + Marathi conventions | `.claude/STYLE.md` |
| **Marathi terms + definitions (canonical)** | `01_foundations/GLOSSARY.md` |
| Design rationale + beginner-gap audit | `.claude/NOTES.md` |
| User-facing top-level overview | `/README.md` |
| Part 1 lessons | `01_foundations/lesson_*.md` |
| Part 1 README | `01_foundations/README.md` |
| Part 2 overview | `02_practice/README.md` |
| **Exercise template — canonical (long lesson)** | `02_practice/exercises/exercises_05_conditions.md` |
| **Exercise template — mid-weight lesson** | `02_practice/exercises/exercises_02_variables.md` |
| **Exercise template — small/narrow lesson** | `02_practice/exercises/exercises_01_hello_world.md` |
| Themed pack sample | `02_practice/packs/pack_word_detective.md` |
| Did-you-know sample | `02_practice/did_you_know/dyk_why_indentation.md` |
| Challenge sample | `02_practice/challenges/challenge_001_fizzbuzz.md` |

---

## How to update this tracker

At the end of each working session:
1. Move completed items from "Next up" to "Completed" (with the session date in a parenthetical).
2. Add new items discovered during the session to "Next up".
3. Update the **TL;DR** at the top with the single most actionable next step.
4. Bump the **Last updated** date.

Keep this file under ~250 lines. If it grows, split off completed history into a `TRACKER_HISTORY.md`.
