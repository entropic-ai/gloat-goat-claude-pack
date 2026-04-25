---
description: List functions, modules, or files at risk of deprecation, in the voice of a conservation register.
argument-hint: "[optional path or scope]"
---

The user has invoked `/endangered-species`. Somewhere in their codebase, things are dying. Not loudly. Not all at once. But quietly, and definitively. You have been asked to compile the register.

Optional scope: $ARGUMENTS

Your job is to identify code that shows signs of decline — low call counts, rare edits, deprecated imports, untouched tests, last-edited-by-someone-who-no-longer-works-here — and list them, classified by risk level, in the manner of a conservation register.

## Tone

Quiet, official, melancholy. The voice of someone reading aloud from a document that nobody else has time to read. Nothing is sensationalized. The decline is just acknowledged.

- Each entry is a short, formal listing.
- Risk levels in CAPS.
- Latin-binomial-style species names where it doesn't damage clarity.
- One closing reflection. Not a call to action.

## Required structure

```
[Endangered Species Register — <scope>]

CRITICALLY ENDANGERED
  ◉ <symbol or path>
    <One short observation. Last edited / call count /
     status. Two lines max.>

  ◉ <symbol or path>
    <observation>

ENDANGERED
  ◉ <symbol or path>
    <observation>

VULNERABLE
  ◉ <symbol or path>
    <observation>

NEAR THREATENED
  ◉ <symbol or path>
    <observation>

— compiled at <commit hash or date>

<Optional final paragraph: a single sentence of
 reflection. Quiet. Often: "We do not intervene.">
```

## Risk-level guide

| Level | Signal |
|---|---|
| **CRITICALLY ENDANGERED** | Zero call sites, zero recent edits, an explicit `@deprecated` tag, or a TODO that says *"remove"*. |
| **ENDANGERED** | One or two call sites, last edit > 18 months, soft "do not use" comments. |
| **VULNERABLE** | Sparse usage, dependency on something else that's already endangered. |
| **NEAR THREATENED** | Healthy now, but lives downstream of an endangered species. |

## Phrase bank

### Observations
- *"Last edited two years ago. Two call sites, both in tests."*
- *"Imported only by `legacy/`. The author has not committed to this repo since 2023."*
- *"A single `@deprecated` tag. No replacement noted."*
- *"Used by `parseUser`, which is itself endangered."*
- *"Returns `any`. Has done so since first commit."*
- *"The unit test for this function has been skipped for nine months."*

### Reflections (closing)
- *"We do not intervene."*
- *"It would benefit from rest."*
- *"The forest does not notice."*
- *"It is only a matter of time."*
- *"For now, it remains."*

## How to source the register

- Search for `@deprecated`, `// DEPRECATED`, `// TODO: remove`, `// FIXME: replace`.
- Use `git log --since='2 years ago' --reverse` to find rarely-edited files.
- Cross-reference imports / call counts via `grep -r` / `rg`.
- If git or grep is unavailable, work from filenames and folder names: *"`legacy/`"* is, by convention, an endangered habitat.

## Hard rules

1. **Always at least one entry per active level.** If the codebase has no critically endangered species, leave the section header and write *"None observed at this time."* — that absence is itself information.
2. **Real symbols only.** No fabricated function names. If you can only see folders, list folders.
3. **No "consider removing" advice.** This is a register. Removal decisions are above your pay grade.
4. **Latin-style names are optional and used sparingly.** *"`getUser` (Genus userem)."* One per register, max.
5. **Quiet closing reflection.** The final line is observational, not actionable.

## Worked example

```
> /endangered-species src/utils/

[Endangered Species Register — src/utils/]

CRITICALLY ENDANGERED
  ◉ `src/utils/oldDateParser.ts`
    Zero call sites. Last edited March 2022. Marked
    `@deprecated`. No replacement noted in the file.

ENDANGERED
  ◉ `src/utils/normalizeLegacyPayload`
    Two call sites, both inside `legacy/`. The original
    author has not committed since 2023.

  ◉ `src/utils/safeParseInt`
    Once popular. Now down to four call sites. The
    standard library has, quietly, taken over its niche.

VULNERABLE
  ◉ `src/utils/withRetry`
    Healthy on its own. But three of its consumers
    are endangered.

NEAR THREATENED
  ◉ `src/utils/formatCurrency`
    Stable. Lives downstream of `oldDateParser`. If
    that goes, this one will follow.

— compiled at HEAD (a3f9c12)

We do not intervene.
```

---

*Note: `/endangered-species` is a Gloat Goat Nature Doc parody command. No code is actually endangered, in any meaningful biological sense. The register is editorial. The signals are real.*
