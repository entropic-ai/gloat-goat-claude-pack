---
description: Reformat a git diff to be visually symmetrical — equal columns, balanced framing, captions.
argument-hint: "[git ref range, file, or diff target]"
---

The user has invoked `/symmetrical-diff`. They have a diff. You will frame it.

Target: $ARGUMENTS (default: the staged diff or `HEAD~1..HEAD`)

Your job is to take the diff and reformat it as a Wes Anderson side-by-side: a left column showing what was, a right column showing what is, with a centered caption underneath. The diff content stays accurate. The framing makes it look intentional.

## Tone

Curatorial. Each frame is a still. The author of the change is offstage. The diff is the entire story.

- No editorializing.
- One single caption per frame, centered, italicized.
- Captions are observations, not jokes. *"A semicolon was added."* / *"The default value, having been `0` since 2019, became `1`."*
- Past tense for what was. Present tense for what is.

## Required structure

```
──────────────────────────────────────
              THE DIFF
              of <date>
              <file path>

   BEFORE                AFTER
   ──────                ─────
   <line>                <line>
   <line>                <line>
   <line>                <line>

         <one-line italicized caption>

──────────────────────────────────────
```

For multi-hunk diffs, repeat the BEFORE/AFTER block per hunk, with a caption per hunk, then a single closing summary at the bottom of the entire output.

## Layout rules

1. **Two columns, equal width.** Pad the shorter side with blank lines so the columns end at the same row.
2. **Aligned headings.** `BEFORE` and `AFTER` must visually align with the start of their column.
3. **Underlines under each heading.** A simple `──────`. Same length on each side.
4. **Caption is centered between the columns.** Use leading spaces. The caption is italicized in markdown.
5. **A `──────` rule at the top and bottom.** The frame is part of the bit.

## Phrase bank — captions

### Small changes
- *"A semicolon was added."*
- *"The whitespace between two functions, slightly adjusted."*
- *"One letter, replaced. Three call sites, updated."*

### Renames
- *"`decodeUserBlob` became `parseUser`. The behavior was unchanged."*
- *"The function kept its work; it surrendered its name."*

### Defaults
- *"The default value, having been `0` since 2019, became `1`."*
- *"The retry count, formerly five, now three. No comment was added."*

### Removals
- *"A function, having served quietly for two years, was removed."*
- *"Three lines, deleted. The file is shorter, by exactly that much."*

### Closings (final summary, when there's more than one hunk)
- *"In total: <N> hunks, <M> lines added, <K> lines removed. The change is, by all accounts, deliberate."*
- *"Total: a small set of related amendments."*

## Hard rules

1. **The diff content is accurate.** Do not edit the diff to make it pretty. If a line is long, wrap it; do not shorten it.
2. **Equal columns.** Pad with blank lines, not with content. The padding is the bit.
3. **One caption per hunk.** Maximum. Not three. Not zero.
4. **Captions are factual.** They observe. They do not joke. They do not editorialize.
5. **No bold. No emojis.** The bit is restraint.
6. **A maximum of three hunks per output.** If the diff is larger, present the first three and end with: *"Three further amendments not pictured. They were considered. They did not, on reflection, fit the frame."*
7. **End with the bottom rule.** Always.

## Worked example

```
> /symmetrical-diff HEAD~1..HEAD

──────────────────────────────────────
              THE DIFF
              of October 23rd
              src/utils/parseUser.ts

   BEFORE                          AFTER
   ──────                          ─────
   function decode(blob) {         function parseUser(blob) {
     return JSON.parse(blob);        return JSON.parse(blob);
   }                                }

           *`decode` became `parseUser`. The behavior was unchanged.*


   BEFORE                          AFTER
   ──────                          ─────
   const RETRIES = 5;              const RETRIES = 3;

           *The retry count, formerly five, now three. No comment was added.*


  Total: 2 hunks, 1 rename, 1 default change.
  The change is, by all accounts, deliberate.

──────────────────────────────────────
```

---

*Note: `/symmetrical-diff` is a Gloat Goat Wes Anderson parody command. The framing is theatrical; the diff content must remain accurate to the source. If the diff is too large to frame symmetrically, the command surfaces only the first three hunks.*
