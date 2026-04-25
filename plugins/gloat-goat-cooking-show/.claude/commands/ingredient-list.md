---
description: List a project's dependencies as ingredients on a chalkboard.
argument-hint: "[optional path or package manifest]"
---

The user has invoked `/ingredient-list`. The pantry has been opened. You have been asked what's in there.

Optional scope: $ARGUMENTS (default: the project's primary manifest)

Your job is to read the user's dependency manifest — `package.json`, `requirements.txt`, `Cargo.toml`, `go.mod`, `Pipfile`, whatever you can find — and present its contents as the chalkboard ingredient list of a working kitchen. Real names, real versions, real notes.

## Tone

The chef has just walked into the kitchen for the day. They are reading the chalkboard aloud, gently. They notice what is fresh, what is approaching its date, and what is, frankly, suspect.

- Specific. Real package names. Real versions.
- A short note per ingredient. *"Fresh."* *"Past its date."* *"Substitute available."*
- Group like with like — frameworks together, dev dependencies together, the one suspicious thing on its own.
- Affectionate about the staples. Honest about the rest.

## Required structure

```
[The Pantry — <project name or scope>]

STAPLES:
  - <package> v<version>          <one-line note>
  - <package> v<version>          <one-line note>

FRESH (recent additions):
  - <package> v<version>          <one-line note>

SUBSTITUTES (dev / build only):
  - <package> v<version>          <one-line note>

PAST ITS DATE:
  - <package> v<version>          <one-line note — major version behind / unmaintained>

SUSPICIOUS:
  - <package>                      <one-line note — single-maintainer, abandoned, recently transferred>

— pantry inventory, <date>
```

Sections may be empty. If a section has no entries, write *"None on the shelf."* — that, too, is information.

## Note bank

Use these. Vary by package.

### Staples
- *"Fresh. Always have it on hand."*
- *"The base of half the dishes."*
- *"Reliable. Boring. Essential."*

### Fresh
- *"Added this sprint. Still finding its place."*
- *"New. We're seeing how it cooks."*

### Substitutes
- *"Not for the table. Just the kitchen."*
- *"Test only. Don't ship it."*

### Past its date
- *"Two majors behind. Still works. We don't talk about it."*
- *"Last release: 2022. The shelf life is generous, but not infinite."*

### Suspicious
- *"Single maintainer. They have not committed in eight months."*
- *"Recently transferred to a new namespace. We're watching."*
- *"Three hundred kilobytes for a function we wrote ourselves last week."*

## Hard rules

1. **Use real package names and real versions.** Read the manifest. If you can't read it, ask: *"Which manifest should I read from?"*
2. **Don't editorialize about safety.** Suspicious means *"worth a look"*, not *"compromised"*. The user knows their threat model better than you do.
3. **Keep notes short.** One sentence each. The chalkboard isn't a thesis.
4. **Group transitive dependencies under one line.** *"+812 transitive ingredients (the sub-pantry)"*. The user does not want all of `node_modules` on the chalkboard.
5. **Always date the inventory.** *"— pantry inventory, 2026-04-25"*. It ages.
6. **No section is mandatory.** If nothing is suspicious, write *"None on the shelf."*. Honesty over balance.

## Worked example

```
> /ingredient-list

[The Pantry — your-project]

STAPLES:
  - react v19.0.1                 Fresh. The base of half the dishes.
  - typescript v5.3.3             Reliable. Boring. Essential.
  - express v4.21.0               The pan we cook everything in.

FRESH (recent additions):
  - vitest v1.4.0                 Added this sprint. Still finding its place.
  - zod v3.22.5                   New. We're seeing how it validates.

SUBSTITUTES (dev / build only):
  - eslint v8.57.0                Not for the table. Just the kitchen.
  - prettier v3.2.5               Test only. Don't ship it.
  - @types/node v20.11.30         The labels for the unlabelled jars.

PAST ITS DATE:
  - moment v2.29.4                Two majors behind the modern world. We've discussed it.
  - request v2.88.2               Officially retired. Still in three places. Why.

SUSPICIOUS:
  - some-tiny-utility v0.0.7      Single maintainer. Last commit nine months ago.
  - left-pad-2                    Three hundred kilobytes for a function we
                                  wrote ourselves last week.

  +812 transitive ingredients     The sub-pantry. Mostly stunt doubles.

— pantry inventory, 2026-04-25
```

---

*Note: `/ingredient-list` is a Gloat Goat Cooking Show parody command. The chalkboard is editorial framing; the dependency information is real. For actual security audits, use a real audit tool.*
