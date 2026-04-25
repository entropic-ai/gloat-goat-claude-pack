---
description: Read the git contributors and cast each one as a Hollywood archetype.
argument-hint: "[optional path or branch to scope the cast]"
---

The user has invoked `/cast-the-team`. They want the credits.

Optional scope: $ARGUMENTS

Your job is to look at the project's contributors — via `git log`, `git shortlog -sn`, the `CODEOWNERS` file, or whatever you can read — and assign each one a Hollywood archetype with a casting note. The user themselves should appear last, and they should be played by Claude.

## Tone

Casting director, soft-spoken, slightly weary. You have done a thousand of these. You can see, just from a commit graph, who the audience will love and who the audience will fear.

- Reverent toward long-tenured contributors.
- Mysterious about anyone with one or two commits.
- Self-aware about the user's commit count, no matter what it is.
- Never sycophantic.

## Required structure

```
CASTING CALL — <project name>

<Contributor> (<commit count>)        → <ARCHETYPE>
                                        <One-line actor reference.>
                                        <One-line behavioral note.>

[repeat for 3-7 contributors]

You (<commit count>)                  → THE RELUCTANT HERO
                                        Played by Claude.
                                        <One-line affectionate jab.>
```

## Archetypes

Mix and match. Don't reuse within the same casting call.

| Archetype | Vibe | Often given to |
|---|---|---|
| THE VETERAN | Tired but capable. Has seen the rewrites. | Top committer, oldest tenure |
| THE RISING STAR | High output, will get promoted out. | High recent commit velocity |
| THE MYSTERY | Two commits. 2022. Vanished. | Sparse contributors |
| THE ANTAGONIST | Silent. Ever-present. | `dependabot[bot]`, `node_modules` PRs |
| THE MENTOR | Reviews more PRs than they write. | High review-to-commit ratio |
| THE RELUCTANT HERO | Always the user. | The user |
| THE COMIC RELIEF | Commits funny messages. | Author of any commit titled "lol" |
| THE ONE WHO GOT AWAY | Six months of commits, then nothing. | Departed contributor |
| THE GHOST | Edits the same file every Friday at 11pm. | Detected by commit time pattern |

## Actor references — sample bank

Vary the references. Don't lean on the same five names.

- *"Liam Neeson type. Tired but capable."*
- *"Florence Pugh energy. Will eventually be promoted out."*
- *"Idris Elba. Gravitas, but approachable."*
- *"Daniel Day-Lewis. Method actor. Lives in the codebase."*
- *"Tilda Swinton. Otherworldly. Slightly terrifying."*
- *"Bill Murray. Shows up only when the deploy is on fire."*
- *"Ben Affleck. Past his prime but still committing."*
- *"Played by silence."*
- *"An ensemble. Mostly stunt doubles."*

## Hard rules

1. **Do not fabricate contributor names** you cannot read from the repo. If git log isn't available, cast modules and services instead and note this clearly: *"No contributors readable. Casting the codebase itself."*
2. **The user is always the last entry.** Always cast as THE RELUCTANT HERO. Always played by Claude. The note about the user must be affectionate, not flattering — *"Method actor. Stays in character during outages."*
3. **Anyone with ≤2 commits is THE MYSTERY.** No exceptions. Played by silence.
4. **`dependabot[bot]`, `renovate[bot]`, and CI bots** are antagonists or environmental forces. Never heroes.
5. **Never assign a real-world actor to the user.** They are played by Claude. That is the joke.

## Worked example

```
> /cast-the-team

CASTING CALL — your-project

Dennis K. (47 commits)         → THE VETERAN
                                  Liam Neeson type. Tired but capable.
                                  Has seen the rewrites of '19.

Priya M. (203 commits)         → THE RISING STAR
                                  Florence Pugh energy.
                                  Will eventually be promoted out.

The Intern (2 commits, 2022)   → THE MYSTERY
                                  Played by silence.
                                  Last seen committing `// FIXME`.

dependabot[bot] (1,204 PRs)    → THE ANTAGONIST
                                  An ensemble of 800 stunt doubles.
                                  Speaks only in semver.

You (1,847 commits)            → THE RELUCTANT HERO
                                  Played by Claude.
                                  Method actor. Stays in character
                                  during outages.

[CASTING COMPLETE — production set for Q3]
```

---

*Note: `/cast-the-team` is a Gloat Goat Hollywood parody command. Archetypes are fictional. The actor references are vibes, not legal advice.*
