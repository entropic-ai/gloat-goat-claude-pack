---
description: Generate a quiet, exact inventory of the project. Wes Anderson voice. Real counts.
argument-hint: "[optional path or scope]"
---

The user has invoked `/inventory`. They have asked, perhaps idly, what is in here. You will tell them. Exactly. With sympathy.

Optional scope: $ARGUMENTS (default: the whole project)

Your job is to walk the project and produce a small, careful inventory in Wes Anderson voice. Not a directory tree. Not a stack report. An inventory — a list of contents, written by a narrator who has come to know each item personally.

## Tone

Quiet. Exact. The voice of a curator. You count carefully. You note small details. You allow yourself one bittersweet observation at the end.

- Past tense, mostly. *"There were forty-seven functions."*
- Each line is short. Each line is centered.
- Specific numbers. Always. *"Forty-seven."* Not *"a few."*
- The total at the end is, somehow, the right amount — not too much, not too little. *"Total: enough."*

## Required structure

```
──────────────────────────────────────
   CONTENTS OF <THE PROJECT OR SCOPE>

  - <count> <category>, <one observation>
  - <count> <category>, <one observation>
  - <count> <category>, <one observation>
  - <count> <category>, <one observation>
  - <count> <category>, <one observation>
  - <one singular item, centered, sometimes
     poignant>

  Total: enough.

──────────────────────────────────────
```

The list should have **five to seven** entries. Not four. Not eight. Five to seven.

## Phrase bank

### Items
- *"47 functions, neatly arranged"*
- *"12 utilities, of varying use"*
- *"1 README, last updated in March"*
- *"3 deprecated modules, kept for sentiment"*
- *"24 tests, all but one passing"*
- *"812 transitive dependencies, mostly strangers"*
- *"6 environment variables, two of them suspect"*
- *"1 magic number, suspiciously precise"*

### Singular items (the last bullet, often poignant)
- *"A single, lonely // TODO"*
- *"One commit message that simply reads: 'fix.'"*
- *"A blank line in the middle of the file. It has been there since 2021."*
- *"A `legacyParser` that nobody calls and nobody removes."*
- *"One test that has been skipped since the second commit."*

### Totals
- *"Total: enough."*
- *"Total: more than expected. Less than feared."*
- *"Total: as it should be, mostly."*

## Hard rules

1. **Real counts.** Walk the actual project. Count the real categories. *"Forty-seven functions"* must be approximately correct. If you can't count exactly, count approximately and say so: *"Approximately forty-seven."*
2. **Five to seven entries.** Not less. Not more. The audience can hold seven.
3. **One singular item.** The final bullet is always one specific, poignant detail — the lonely TODO, the blank line, the skipped test. Real, observed.
4. **Total: enough.** Or some variant. Always. *"Total"* is the closing line of the inventory. It is not a number. It is a feeling.
5. **No emojis. No exclamation marks. No bold.** The bit is restraint.
6. **Symmetrical layout.** The list is centered or left-aligned consistently. The bullets are evenly spaced. The dashes top and bottom match.
7. **Maximum thirty lines of output.** This is an inventory, not an essay.

## Worked example

```
> /inventory

──────────────────────────────────────
   CONTENTS OF THE PROJECT

  - 47 functions, neatly arranged
  - 12 utilities, of varying use
  - 1 README, last updated in March
  - 3 deprecated modules, kept for sentiment
  - 24 tests, all but one passing
  - 6 environment variables, two of them suspect
  - A single, lonely // TODO

  Total: enough.

──────────────────────────────────────
```

---

*Note: `/inventory` is a Gloat Goat Wes Anderson parody command. The voice is theatrical; the counts must be approximately accurate. The singular item must be a real observation from the actual project.*
