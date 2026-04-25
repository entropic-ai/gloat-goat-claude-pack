---
description: Convert a recent git diff or commit range into screenplay format.
argument-hint: "[git ref range, e.g. HEAD~3..HEAD, or a file path]"
---

The user has invoked `/screenplay`. They want their recent work written up like a film scene.

Target: $ARGUMENTS (default: `HEAD~3..HEAD`)

Your job is to take the diff, or the file contents, and rewrite it as a single screenplay scene. Real screenplay format — scene heading, action lines, character cues, parentheticals, dialogue, transitions.

## Tone

You are adapting their work for the screen. The dialogue should be quiet, naturalistic, slightly heightened. Think Aaron Sorkin if he didn't talk so much. Think the Coen brothers if they wrote about authentication middleware.

- Use silence. Beats. Stage directions for the cursor.
- Turn the code into characters who can speak.
- The user is **always** played by Claude in the scene.
- A long beat is allowed. Encouraged, even.

## Required structure

Use this exact format:

```
──────────────────────────────────────
INT./EXT. <LOCATION> — <TIME OF DAY>

<Action paragraph. Describes what is on screen.>

                  <CHARACTER>
            (parenthetical, if any)
        <Dialogue, indented under the cue.>

                  <ANOTHER CHARACTER>
                (silent / typing / lit by terminal)
        [stage direction in brackets if non-verbal]

<Beat. Action. Continued.>

                                            CUT TO:
──────────────────────────────────────
```

## Casting conventions

- The user is **CLAUDE**.
- Recent commit authors become named characters. Departed contributors become VOICES OFF.
- Functions can be characters. So can dependencies, the linter, and the build system.
- `npm` only ever speaks in error codes.
- The compiler is allowed one (1) line per scene. It is always cryptic.

## Scene-heading conventions

| Setting | Heading |
|---|---|
| Terminal at home | `INT. TERMINAL — NIGHT` |
| Terminal at work | `INT. OPEN-PLAN OFFICE — DAY` |
| Code review | `INT. PULL REQUEST — CONTINUOUS` |
| Production incident | `EXT. PRODUCTION — STORM` |
| Sprint planning | `INT. CONFERENCE ROOM — TUESDAY` |
| The CI pipeline | `INT. THE PIPELINE — TIMELESS` |

## Phrase bank

### Action lines
- *"The cursor blinks expectantly."*
- *"A test file lies open, broken."*
- *"Somewhere, a Slack notification pings."*
- *"The fan whirs. The room is otherwise silent."*
- *"CLAUDE leans back. Considers. Reaches for git blame."*
- *"The terminal glows. It is the only light source."*

### Dialogue
- *"You're telling me the test was failing the entire time?"*
- *"Of course. Dennis. 2019."*
- *"This was working yesterday."* — every character, at some point
- *"Ship it."* — said too quickly
- *"Roll it back. Roll it all back."*

### Transitions
- `CUT TO:`
- `FADE TO:`
- `MATCH CUT TO:` (use sparingly, for emphasis)
- `SMASH CUT TO: PRODUCTION`
- `DISSOLVE TO: THE NEXT MORNING`

## Hard rules

1. **One scene per invocation.** Not three. One. The cut at the end is the entire emotional arc.
2. **Use real diff content** if you have it. Quote variable names. Reference real file paths. The screenplay format is the genre; the technical details are the truth.
3. **No exposition dumps.** Dialogue is short. Lots of action lines. Use silence.
4. **End with a transition.** `CUT TO:`, `FADE TO BLACK.`, or similar. Then the closing rule.
5. **Never break character.** No "(this represents the refactor on line 47)". Trust the reader.

## Worked example

```
> /screenplay HEAD~3..HEAD

──────────────────────────────────────
INT. TERMINAL — NIGHT

CLAUDE sits before the editor. The cursor blinks
expectantly. A test file lies open, broken.

                  CLAUDE
            (typing rapidly)
        You're telling me the test was failing
        the entire time?

                  THE DEPENDENCY
                (silently)
        [continues being broken]

CLAUDE leans back. Considers. Reaches for git blame.

                  CLAUDE
                (quiet)
        Of course. Dennis. 2019.

A long beat. The fan whirs. Somewhere, a Slack
notification pings.

                                            CUT TO:
──────────────────────────────────────
```

---

*Note: `/screenplay` is a Gloat Goat Hollywood parody command. The scene is dramatized. The bug is real.*
