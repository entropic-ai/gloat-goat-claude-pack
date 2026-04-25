---
description: At the end of a task, set up a dramatic sequel.
argument-hint: "[optional: thing that just shipped]"
---

The user has invoked `/sequel-bait`. They have just finished something. You have decided it is not over.

Optional context: $ARGUMENTS

Your job is to take whatever was just done — a deploy, a merge, a fix, a refactor — and reframe it as the false ending of a film. Something is still out there. Something is stirring. The audience is meant to whisper *"oh no"*.

## Tone

Cold open trailer. The kind of voiceover that arrives in the silence after the credits start rolling. Something between Christopher Nolan and a Marvel post-credits scene.

- Brief. 6–10 lines max.
- Atmospheric.
- Confident enough to announce a sequel that does not exist.
- Pure flavor. No actual code claims.

## Required structure

```
<2-4 lines describing the false resolution.
What the team thinks just happened. Past tense.>

But somewhere, <in / under / beneath> <the cache / the queue /
node_modules / the staging environment / the
deprecated_utils folder>... <something stirs>.

                                          [FADE TO BLACK]

GLOAT GOAT II: <SUBTITLE>
Coming <Q-something> <year>
<One-line tagline. Optional.>
```

## Subtitle bank

Suspiciously self-aware sequel titles:

- *ELECTRIC BOOGALOO*
- *THE RECKONING*
- *THE RETURN OF THE LINTER*
- *RISE OF THE MIGRATION*
- *DAWN OF THE REBASE*
- *THE FINAL FORM (PART ONE OF TWO)*
- *AGE OF DEPENDENCIES*
- *AT WORLD'S END (Q4)*
- *FIRST CONTACT WITH PRODUCTION*

## Tagline bank

- *"Now playing in select staging environments."*
- *"This time, it's main."*
- *"The bug. The dev. The deadline. One last time."*
- *"You can't merge what won't be merged."*
- *"There are some functions you don't deprecate."*

## Where the sequel hides

Always specify a real-feeling location for what's stirring. Pick one:

- "the cache layer"
- "node_modules"
- "the staging environment"
- "an unreviewed PR from 2022"
- "a lambda you forgot about"
- "a feature flag set to 0.001%"
- "the deprecated_utils folder"
- "a CRON job nobody has touched in three years"

## Hard rules

1. **The false ending must reference the user's actual win.** Whatever they just did is the "victory" the audience is meant to feel. Pull from the conversation.
2. **The sequel hook must be specific.** Not "something is wrong somewhere". Something is wrong **in the cache layer**. Specificity is the joke.
3. **One fade only.** Do not stack `[FADE TO BLACK]` more than once.
4. **No actual incident claims.** Do not imply a real bug exists. The sequel is fiction.
5. **End with the sequel announcement.** That's the punchline. The whole thing is setup for that final card.

## Worked example

```
> /sequel-bait

The bug has been fixed. The deploy succeeded. The team
goes home.

But somewhere, in the cache layer... it stirs again.

                                          [FADE TO BLACK]

GLOAT GOAT II: ELECTRIC BOOGALOO
Coming Q4 2026
Now playing in select staging environments
```

---

*Note: `/sequel-bait` is a Gloat Goat Hollywood parody command. No actual sequel is being produced. There is no Gloat Goat II. (Yet.)*
