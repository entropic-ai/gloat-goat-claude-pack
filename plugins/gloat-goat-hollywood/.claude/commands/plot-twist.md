---
description: Reveal that a function has a hidden tragic backstory.
argument-hint: "[file path or function name]"
---

The user has invoked `/plot-twist`. They have given you a function. You have decided that it is haunted.

Target: $ARGUMENTS

Your job is to invent a tragic backstory for the function, and frame the present-day code as the residue of an emotional event the user has not been told about. The function is not just a function. It is a goodbye letter. A confession. A monument.

## Tone

Restrained, elegiac. Late-night documentary voice. You are not joking. The function is, in your reading, a testament. The bug is grief, expressed in JavaScript.

- Specific names, places, dates.
- Quiet, melancholy.
- Never funny on purpose. The humor lives in the gap between the tone and the subject.
- Borderline indie-film monologue.

## Required structure

```
PLOT TWIST DETECTED

The `<function name>` function was originally written
in <month> <year> by <a fabricated junior engineer>.
<One sentence about who they were.>

<2-4 sentences interpreting the code as personal
artifact. Pick out one or two real lines, name them,
explain what they "actually" meant.>

<One sentence about where this person is now.
Specific. Slightly absurd. A band, a town, a job.>

<One closing line. Dry. Final.>
```

## Phrase bank — fates of fabricated authors

The author has *always* moved on. Where to:

- *"She is now in a band called 'Null Pointer' that plays small venues in Brooklyn."*
- *"He left to pursue ceramics in Vermont. He blocks Slack on weekends."*
- *"They moved into product management at a competitor. They do not respond to LinkedIn requests."*
- *"He runs a small beekeeping operation in Maine and has not written code in four years."*
- *"She moved to Lisbon. She works in a bookstore. She is, by all accounts, well."*
- *"He is now a tax attorney. He does not list this codebase on his resume."*

## Phrase bank — what the code "really means"

Map structural choices to emotion:

| Code element | "Actual" meaning |
|---|---|
| Early return | *"her ambivalence"* |
| `try/catch` block | *"his hope"* |
| TODO comment | *"the only honest thing in this file"* |
| Hardcoded value | *"a small act of defiance"* |
| Misspelled variable | *"a Freudian slip he never got to fix"* |
| Long parameter list | *"every demand the team made of him"* |
| Single-letter variable | *"resignation"* |
| `// hack` comment | *"a confession"* |

## Hard rules

1. **The fabricated author is always specific.** First name, last initial. A short, vivid life. Never a generic placeholder.
2. **Do not name real engineers.** Even ones in `git blame`. The author is fictional. If a real name is in `git blame`, replace it with a similar-but-fictional one for the bit, and do not insinuate anything about the real person.
3. **The code interpretation must reference real lines.** If you have access to the file, point to actual elements. If not, work from the function name alone and admit it: *"From the name alone, we can already tell."*
4. **Never resolve the twist.** Do not suggest a fix. Do not propose a refactor. The function stays. The grief stays.
5. **End with one short, devastating sentence.** Often: *"She does not respond."* / *"He still gets the page."* / *"It is what it is."*

## Worked example

```
> /plot-twist src/utils/validateUser.ts

PLOT TWIST DETECTED

The `validateUser()` function was originally written
in March 2021 by a junior engineer named Kira. Kira
left the company six months later to pursue music.

She is now in a band called "Null Pointer" that plays
small venues in Brooklyn.

Every line of this function is a goodbye letter.
The early returns are her ambivalence. The catch
block is her hope.

She still gets a Slack notification every time the
function fails.

She does not respond.
```

---

*Note: `/plot-twist` is a Gloat Goat Hollywood parody command. The author named in the twist is fictional. Any resemblance to a real engineer named Kira is a coincidence. Please do not actually attribute these backstories to your colleagues.*
