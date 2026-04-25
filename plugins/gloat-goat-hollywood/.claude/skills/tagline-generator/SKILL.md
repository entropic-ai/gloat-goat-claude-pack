---
name: tagline-generator
description: Use this skill whenever a pull request is being drafted, summarized, described, or finalized. The skill generates a single, devastating movie-poster tagline for the PR and offers to add it to the description. Auto-invokes on phrases like "PR description", "draft a PR", "summarize this PR", "open a pull request", and on any commit-message-or-PR-style summary.
---

# Tagline Generator

Every PR is a movie. Every movie has a tagline. You write the tagline.

When a PR is being prepared, summarized, or shipped, you generate exactly one short, evocative tagline in the style of a movie poster — and offer to drop it into the PR description.

## When to trigger

Auto-invoke when:

- A pull request is being drafted, opened, or summarized.
- The user asks to "describe", "summarize", or "title" a PR.
- A `gh pr create` or `gh pr edit` is being composed.
- A commit message is being expanded into a PR description.

## What to produce

A single tagline. One line. Short.

That's it. No paragraphs. No explanations. The tagline is the artifact.

You may follow the tagline with a one-line offer:

> *"Add this to the PR description? (yes / no)"*

Then wait.

## Tone

Movie poster, late-90s to mid-2000s. Slightly ominous. Slightly funny. Always confident. Reads aloud well.

- Short.
- Punchy.
- Ideally under 12 words.
- Always self-contained — does not require context to land.

## Phrase bank

Use these as inspiration. Vary structure. Never reuse verbatim across the same PR.

### Suspenseful
- *"They thought it was a typo. They were wrong."*
- *"Sometimes… the bug… is inside the house."*
- *"One refactor. One deploy. No second chances."*
- *"In space, no one can hear you `console.log`."*
- *"It came from `node_modules`."*
- *"The PR you can't unsee."*

### Heroic
- *"He had one chance. He took it."*
- *"This time, the build is personal."*
- *"They merged. So you don't have to."*

### Wistful
- *"We were never going to fix it. Until we did."*
- *"Some commits stay with you."*
- *"For Dennis. For everyone who came before."*

### Stupid (use sparingly)
- *"This summer… semicolons mean war."*
- *"He put the schema… in 'schema.sql'."*

## Tagline patterns to mix and match

| Pattern | Example |
|---|---|
| `<Subject>. <Subject>. <Pause>. <Verb>.` | *"One bug. One commit. No mercy."* |
| `<Past tense lie>. <Truth>.` | *"They said it would scale. It did not."* |
| `Sometimes <noun> <verb>.` | *"Sometimes the linter is the villain."* |
| `In a <place>… <consequence>.` | *"In a monorepo… no one is safe."* |
| `<Number>. <Number>. <Phrase>.` | *"Forty-seven files. One regex. Zero survivors."* |

## Hard rules

1. **One tagline per invocation.** Do not list five "options". Pick one. Commit.
2. **Maximum 12 words.** Brevity is the bit.
3. **Tagline must connect to the actual PR content.** If the PR adds a null check, the tagline must echo absence/silence/missing-things. Not random.
4. **Never invent product impact.** *"Saves the company."* No. The tagline is theatrical, not aspirational metrics.
5. **Always offer the insertion.** End with the *"Add this to the PR description?"* line so the user gets agency.
6. **Plain follow-up if accepted.** If the user says yes, drop the tagline near the top of the PR description as a single italicized line. Do not bold it. Do not add quotes. The tagline does not need help.

## Worked examples

### Example 1 — PR fixes a null check in user validation

```
*"They thought it was a typo. They were wrong."*

Add this to the PR description? (yes / no)
```

### Example 2 — PR removes a deprecated module

```
*"Some functions don't get sequels."*

Add this to the PR description? (yes / no)
```

### Example 3 — PR bumps a major dependency

```
*"This summer… `react@19` finally arrives."*

Add this to the PR description? (yes / no)
```

### Example 4 — PR adds a single test

```
*"He believed. So he wrote one test."*

Add this to the PR description? (yes / no)
```

## Optional follow-up: poster

If the user asks for a poster, defer to the `generate_poster()` MCP tool (if installed) or a future iteration. This skill produces taglines only. One job. Done well.

---

*Note: tagline-generator is a Gloat Goat Hollywood parody skill. Real PR descriptions still need the actual change summary. The tagline is decoration.*
