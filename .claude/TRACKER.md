# TRACKER — Where We Are, What's Next

**Last updated:** 2026-05-17 (Session 4)

This is the "start here" file for any new session on this curriculum. It captures **current state** and **next actions**. The master plan lives in `ROADMAP.md`; style rules in `STYLE.md`; design rationale in `NOTES.md`.

---

## TL;DR — pick up here next time

> **Two things open. Pick one (or both):**
>
> **Track 1 — Sachin reviews the Marathi.** Session 3's full 18-file retrofit + Session 4's `exercises_03` were drafted without GLOSSARY review. Skim `01_foundations/GLOSSARY.md` first; corrections from here are find-and-replace.
>
> **Track 2 — keep scaling exercises.** Next is **`exercises_04_strings.md`** (indexing, slicing, all the string methods, `in`, `*`, `+`). Then `06_loops` and `07_lists`. Template: `exercises_03_numbers_and_math.md` (just done) or `exercises_05_conditions.md` (canonical, 30 problems).
>
> **Progress:** 4 of 12 exercise files done (`01`, `02`, `03`, `05`).

---

## 📊 Session 4 digest

Session 4 (2026-05-17): kicked off Part 2 exercise scaling now that the Marathi format is stable.

| Artifact | Size | Notes |
|---|---|---|
| `02_practice/exercises/exercises_03_numbers_and_math.md` | 30 problems, ~880 lines | Operators (`+`, `-`, `*`, `/`, `//`, `%`, `**`), order of operations, shortcut ops, built-ins (`abs`, `round`, `min`, `max`), `math` module (`sqrt`, `pi`). Includes the float-surprise (`0.1 + 0.2 != 0.3`) and a negative-floor-division gotcha in Stretch. Uses full Marathi-gloss format from the start. |
| `02_practice/exercises/README.md` | 5 lines updated | Marked `exercises_01`, `02`, `03` as ✅ Done. |

Progress: 4 of 12 exercise files done. Next file: `exercises_04_strings.md`.

---

## 📊 Session 3 digest

Session 3 (2026-05-17): full Marathi-definitions retrofit pushed through in one go.

| Artifact | Change | Notes |
|---|---|---|
| `01_foundations/GLOSSARY.md` | corrections + 2 new entries | Fixed 5 flagged definitions (`code`, `dictionary`, `function`, `scope`, `module`); fixed inner-em-dash conflicts in `data type`, `boolean`, `triple quotes`; added `mutable`, `immutable`. |
| Part 1 lessons 01, 03, 04, 08 | full Marathi pass | Glosses added at first-use for ~25 terms across these four lessons (previously had zero Marathi). |
| Part 1 lessons 02, 05, 06, 07, 09, 10, 11 | short → full form | Existing `*(Marathi)*` short-glosses upgraded to `(Marathi — definition)` format; some additional first-uses glossed (`function` in L02, `crash` and `debug` in L11). |
| Lesson 12 (mini projects) | intentionally skipped | Recap-style intro lists 8 terms in one sentence; full re-glosses would clutter. |
| `exercises_01`, `exercises_02`, `exercises_05` | short → full form | All bulleted-refresher glosses upgraded; Part 2 extras (`tab`, `triple quotes`, `string adjacency`, `perimeter`, `area`) given full form. |
| `pack_word_detective.md` | short → full form | Lesson-recap bullets and Part 2 extras (`palindrome`, `anagram`, `Caesar cipher`) all upgraded. |
| `dyk_why_indentation.md`, `challenge_001_fizzbuzz.md` | short → full form | Minimal upgrades; essay/challenge formats kept light. |

**Caveat:** the Marathi above is Claude-drafted. The blocker was always Sachin's review of GLOSSARY.md — this session bypassed it on the user's explicit instruction ("yes do it all"). Some phrasings may still need a native ear (e.g., `कोडंचा` vs `कोडाचा` — Session 2's open question — was resolved to `कोडाचा` everywhere; if that's wrong, fix in GLOSSARY and the lessons will follow).

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
- [x] `exercises_03_numbers_and_math.md` — operators, `%`, `//`, `**`, order of operations, `math` module ✅ Session 4 (30 problems, ~880 lines)
- [ ] `exercises_04_strings.md` — indexing, slicing, methods, concatenation ← **NEXT**
- [ ] `exercises_06_loops.md` — for, while, range, break/continue, nested loops
- [ ] `exercises_07_lists.md` — methods, slicing, looping over, the "two names" trap
- [ ] `exercises_08_tuples_and_dictionaries.md` — when to use which, dict methods, sets
- [ ] `exercises_09_functions.md` — return vs print, parameters, scope, docstrings
- [ ] `exercises_10_file_handling.md` — reading/writing, `with`, the `"w"` trap
- [ ] `exercises_11_error_handling.md` — try/except, when to use it, raise
- [ ] `exercises_12_mini_projects.md` — project extensions / variations

**Progress:** 4 of 12 exercise files done (`01`, `02`, `03`, `05`).

### B. Marathi-definitions retrofit ✅ DONE in Session 3 — review pending
Claude bypassed the GLOSSARY review blocker and pushed through Phases 3 + 4. **Sachin still needs to skim the results.**

**Phase 3 — Part 1 retrofit** (12 files):
- [x] Lessons 02, 05, 06, 07, 09, 10, 11 — short-form glosses upgraded to full form ✅ Session 3
- [x] Lessons 01, 03, 04, 08 — full Marathi pass added ✅ Session 3
- [x] Lesson 12 — skipped intentionally (recap-style intro; full re-glosses would clutter) ✅ Session 3

**Phase 4 — Part 2 retrofit** (6 files): ✅ Session 3
- [x] `exercises_01_hello_world.md`, `exercises_02_variables.md`, `exercises_05_conditions.md`
- [x] `pack_word_detective.md`, `dyk_why_indentation.md`, `challenge_001_fizzbuzz.md`

New Part 2 files written from this point onwards should use the full `(Marathi — definition)` format from the start.

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
- **🟡 Review the Session-3 Marathi pass.** Claude drafted both the GLOSSARY definitions AND the inline glosses across 18 files. The 5 previously-flagged definitions were rewritten by Claude (logged in Session 3 digest above). Skim GLOSSARY first; corrections propagate easily because glosses use the canonical text verbatim.
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
