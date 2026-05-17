# STYLE — Writing & Formatting Guide

The rules that keep all 5 parts feeling like one curriculum.

---

## Voice

- **Talk to the reader, not at them.** "You'll notice…", "Try this…", "Watch what happens when…".
- **Short sentences.** A 10-year-old should never have to re-read a sentence to parse it.
- **Concrete before abstract.** "Imagine a labeled jar" comes before "a variable is a named reference to a value."
- **Show, then name.** Demonstrate the idea with code; *then* introduce the technical term.
- **No condescension and no false praise.** Don't say "great job!" for trivial things. Do say "this is genuinely tricky — most beginners get stuck here."
- **Errors are normal.** Frame mistakes as expected discoveries, not failures.

## Formatting

- Lesson title: `# Lesson NN: Title — Friendly Hook`. Em-dash separator. Sentence case for the hook.
- Section headers: `## Section`. Avoid going deeper than `###`.
- Every code example **must** include the expected output below it, formatted as:
  ````
  **Expected Output:**
  ```
  ...
  ```
  ````
- Inline code: `backticks`. Code blocks: fenced with the language (`python`, `text`).
- Callouts use blockquotes:
  - `> **Watch out!** …` for common mistakes
  - `> **Try this:** …` for nudges to experiment
  - `> **Did you know?** …` for fun facts
  - `> **Marathi:** …` (rare — only when there's a specifically cultural framing)
- Tables for "when to use which" decisions.
- Diagrams: ASCII first. Only reach for images if ASCII genuinely fails.
- Use `---` horizontal rules between major sections.

## Code conventions

- **Comments**: English only. (Code must be runnable by anyone.)
- **Variable names**: descriptive English (`student_age`, not `a` or `विद्यार्थी_वय`).
- **Indentation**: 4 spaces. Never tabs.
- **Strings**: prefer double quotes unless single makes the example clearer.
- **f-strings** for any string with a variable in it. No `%` formatting, no `.format()` except when explicitly teaching alternatives.
- **No unused imports.** No `from x import *`. No abbreviated imports kids haven't seen (`import numpy as np` is fine *after* it's been introduced).
- **Print expected output for every snippet.** Even trivial ones.
- **Don't use features the lesson hasn't introduced.** Lesson 03 must not silently use a list comprehension.

## Marathi integration

- **First mention rule**: a technical term gets its Marathi gloss in parentheses on the **first time it appears in that lesson**. Subsequent uses are English only. E.g. `variable (चल — एखादे मूल्य ठेवण्यासाठीचे नाव)` once, then `variable` for the rest of the lesson.
- **Always full form on first use.** Format: `term (Marathi — short Marathi definition)`. The definition is 4–10 words. This rule applies to *every* lesson — even subsequent lessons that re-introduce a term get the full form again, because students may read lessons out of order.
- **Single source of truth: `01_foundations/GLOSSARY.md`.** Every term, its Marathi, and its canonical definition live there. Use the glossary verbatim — do not invent translations and do not paraphrase definitions in lesson prose.
- **Prose only.** Marathi does not appear inside code or in comments.
- **When a concept has no clean Marathi equivalent**, keep the English term in Devanagari transliteration with a definition: `function (फंक्शन — नाव दिलेला एक काम करणारा कोडंचा गट)`. Don't force a calque.
- **Trivial connectors (`and`, `or`, `not`, etc.)** still get the full form; the definition simply explains the logical meaning rather than translating the word.

The short translation table below is a quick reference. **For the canonical definition of each term, see `01_foundations/GLOSSARY.md`.** When you introduce a new term, add it to GLOSSARY.md first (with a Marathi definition), then use it in the lesson.

---

## Marathi Glossary — canonical translations

Use these. Add new entries here when introducing new terms. Bracketed alternatives are acceptable substitutes; the **first** form is the default.

### Core concepts

| English | Marathi | Notes |
|---|---|---|
| program | प्रोग्राम / कार्यक्रम | Use प्रोग्राम in lesson context; कार्यक्रम in cultural framing |
| code | कोड | |
| programmer | प्रोग्रामर | |
| computer | संगणक | |
| language (programming) | भाषा (प्रोग्रामिंग) | |
| Python | पायथन | |
| instruction | सूचना | |
| input | इनपुट | |
| output | आउटपुट | |
| run / execute | चालवणे | |
| file | फाइल | |
| folder | फोल्डर | |
| save | सेव्ह करणे | |

### Values & variables

| English | Marathi | Notes |
|---|---|---|
| variable | चल | Mathematical "variable" — well understood |
| value | मूल्य | |
| assign (a value) | नेमणे / देणे | "अ ला 5 ची नेमणूक" or "अ ला 5 दिले" |
| data | डेटा | |
| data type | डेटा प्रकार | |
| number | संख्या | |
| integer | पूर्णांक | |
| decimal / float | दशांश | |
| string | स्ट्रिंग [शब्दमाला] | Default to स्ट्रिंग; शब्दमाला for explanation |
| boolean | बूलियन [सत्य-असत्य] | |
| True | True (खरे) | Keep `True` literal; explain as खरे |
| False | False (खोटे) | Keep `False` literal; explain as खोटे |
| None | None (काही नाही) | |
| list | यादी | |
| tuple | ट्युपल | |
| dictionary | शब्दकोश | Same word as the book — kids get the analogy |
| set | संच | Math term — kids may know it |

### Operations

| English | Marathi | Notes |
|---|---|---|
| addition (+) | बेरीज | |
| subtraction (–) | वजाबाकी | |
| multiplication (*) | गुणाकार | |
| division (/) | भागाकार | |
| modulus (%) | भागाकाराचा शेष | |
| equal to (==) | समान | |
| not equal to (!=) | असमान | |
| greater than (>) | पेक्षा मोठे | |
| less than (<) | पेक्षा लहान | |
| and | आणि | |
| or | किंवा | |
| not | नाही | |

### Control flow

| English | Marathi | Notes |
|---|---|---|
| condition | अट | |
| if | जर | "if it rains" → "जर पाऊस पडला तर" |
| else | नाहीतर | |
| elif | किंवा जर | Literally "or if" — matches the meaning |
| loop | लूप / पुनरावृत्ती | पुनरावृत्ती = "repetition" |
| for loop | for लूप | |
| while loop | while लूप | |
| iterate | फिरवणे / पुनरावृत्ती करणे | |
| break | थांबवणे | |
| continue | पुढे चालू ठेवणे | |

### Functions & structure

| English | Marathi | Notes |
|---|---|---|
| function | फंक्शन | |
| parameter | पॅरामीटर | |
| argument | आर्ग्युमेंट | |
| return (a value) | परत देणे | |
| call (a function) | बोलावणे | "function ला बोलावणे" |
| scope | स्कोप / व्याप्ती | |
| module | मोड्यूल | |
| import | इम्पोर्ट | |
| library | लायब्ररी | |

### Errors

| English | Marathi | Notes |
|---|---|---|
| error | त्रुटी / एरर | |
| bug | बग | |
| debug | डीबग | |
| syntax error | सिंटॅक्स त्रुटी | |
| exception | अपवाद | |
| try / except | try / except | Keep literal; explain in prose |
| crash | क्रॅश होणे | |

### AI (for Parts 4–5)

| English | Marathi | Notes |
|---|---|---|
| artificial intelligence | कृत्रिम बुद्धिमत्ता | |
| machine learning | मशीन लर्निंग | |
| model | मॉडेल | |
| training | प्रशिक्षण | |
| training data | प्रशिक्षण डेटा | |
| pattern | पॅटर्न / नमुना | |
| classify / classification | वर्गीकरण | |
| predict / prediction | अंदाज | |
| neural network | न्यूरल नेटवर्क | |

### Add new terms here

When you introduce a new technical term, add the agreed translation here before using it in any lesson.

---

## Anti-patterns to avoid

- ❌ Long paragraphs explaining theory before the first code example
- ❌ "Easy!" or "Simple!" as a description — patronizing
- ❌ Pop-culture references that won't age well (use timeless examples)
- ❌ Examples that require domain knowledge (no stock trading, no chemistry-class formulas)
- ❌ Using `lambda`, `map`, `filter`, comprehensions, or decorators before they've been formally taught
- ❌ Translating variable names or function names into Marathi
- ❌ Mixing two languages mid-sentence ("तू variable तयार कर"). Either full Marathi parenthetical or full English sentence.
- ❌ Walls of code without breaks. Break long programs into chunks with prose between them.
