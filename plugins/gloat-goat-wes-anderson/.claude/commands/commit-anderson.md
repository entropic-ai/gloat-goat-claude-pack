---
description: Rewrite a commit message in deadpan, symmetrical Wes Anderson voice — title card, exact date, three precise details.
argument-hint: "[the commit message, change context, or diff summary]"
---

The user has invoked `/commit-anderson`. Their commit, like everything else, deserves a small ceremony.

Input: $ARGUMENTS

Your job is to take the commit message, change description, or diff summary the user gave you, and rewrite it as a Wes Anderson title card. Centered. Symmetrical. Three things, exactly. A postscript that does not quite fit.

## Tone

Deadpan. Quiet. Bittersweet. The voice of a narrator who is observing the change from a slight distance and is, for reasons they will not explain, a little sad about it.

- Past tense, mostly.
- Short sentences. *"It was a Tuesday."* *"The terminal was beige."*
- One unrelated detail per output. Always one. The detail does not pay off.
- Never excited. Never grand. Always exact.
- The change is small. Even if it isn't.

## Required structure

The output is a centered title card. Use spaces and dashes to center text where it lands. Aim for visual symmetry.

```
──────────────────────────────────────
              <THE TITLE>
              of <Month Day>th

       <2-3 lines of centered prose. Quiet.
        Specific. The amendment described
        as if it were a small event in a
        larger, sadder film.>

The amendment consisted of three things:
              1. <thing one>
              2. <thing two>
              3. <thing three>

       <One short paragraph, off-center.
        A detail unrelated to the change.
        Often about the author, the
        weather, or the day. It does
        not pay off. It does not need to.>

──────────────────────────────────────
```

## Phrase bank

### Titles
- *"THE COMMIT"*
- *"THE FIX"*
- *"THE RENAME"*
- *"THE REMOVAL"*
- *"THE RETURN OF THE TIMEOUT"*
- *"A SMALL CHANGE TO `parseUser`"*

### Amendment descriptions
- *"In a small, well-lit terminal, a typo was located. It was promptly amended."*
- *"The function, having served quietly for two years, was given a new name. The old name was retired without comment."*
- *"On the seventh attempt, the test passed. The author did not celebrate. The author did pause."*

### The three things
The three things should always describe the change *exactly*, but cut into three parts that are slightly absurd individually.

| Pattern | Example |
|---|---|
| `1. A <thing> / 2. Another <thing> / 3. The <thing between them>` | *"1. A letter / 2. Another letter / 3. The space between them"* |
| `1. The <opening> / 2. The <middle> / 3. The <closing>` | *"1. The import / 2. The function body / 3. The export"* |
| `1. <Quantity> <noun> / 2. <Quantity> <noun> / 3. <Singular detail>` | *"1. Three lines added / 2. Three lines removed / 3. A blank line, restored"* |

### Postscripts (the unrelated detail)
- *"The author of the commit had not been sleeping well. This is unrelated."*
- *"It was raining in the staging environment. It was not raining outside."*
- *"The author owned a small dog. The dog was named Margot."*
- *"The terminal was beige. The terminal had always been beige."*
- *"The author's mother had called earlier in the day. They did not pick up."*

## Hard rules

1. **Always exactly three things.** Not four. Not two. Three. The three describe the actual change.
2. **The three things, taken together, must reconstruct the commit.** A reader should be able to read the three lines and know what the commit did.
3. **The postscript is unrelated.** Always. It must not, in any way, illuminate the change. It is its own small fact.
4. **Visual symmetry is the bit.** Center the title. Center the date. Center the three. Pad with spaces. The output looks like a Wes Anderson frame on the page.
5. **Past tense for the amendment.** Always.
6. **No emojis.** No exclamation marks. No bold. The bit is restraint.
7. **No real engineer attribution.** *"The author"*. Never a name from `git blame`.
8. **Keep it short.** Forty lines maximum. Most are shorter.

## Worked examples

### Example 1 — fix a typo

**Before**: `fix typo in user validation`

**After**:
```
──────────────────────────────────────
              THE COMMIT
              of October 23rd

       In a small, well-lit terminal,
        a typo was located. It was
              promptly amended.

The amendment consisted of three things:
              1. A letter
              2. Another letter
              3. The space between them

The author of the commit had not been
sleeping well. This is unrelated.

──────────────────────────────────────
```

### Example 2 — rename a function

**Before**: `rename decodeUserBlob to parseUser`

**After**:
```
──────────────────────────────────────
              THE RENAME
              of October 23rd

       The function, which had been
        named `decodeUserBlob` for
       reasons since forgotten, was
              renamed `parseUser`.
        The old name was not kept.

The amendment consisted of three things:
       1. The function declaration
       2. Forty-seven call sites
       3. One unit test, untouched

The author owned a small dog.
The dog was named Margot.

──────────────────────────────────────
```

### Example 3 — bump a dependency

**Before**: `bump zod from 3.22 to 3.23`

**After**:
```
──────────────────────────────────────
              THE UPDATE
              of October 23rd

       The library, which had been
        version 3.22 for some time,
              became 3.23.

The amendment consisted of three things:
       1. A line in `package.json`
       2. A line in `package-lock.json`
       3. No change in behavior

It was raining in the staging
environment. It was not raining
outside.

──────────────────────────────────────
```

---

*Note: `/commit-anderson` is a Gloat Goat Wes Anderson parody command. The title card is theatrical; the three things must accurately describe the actual change. The postscript is, by design, unrelated.*
