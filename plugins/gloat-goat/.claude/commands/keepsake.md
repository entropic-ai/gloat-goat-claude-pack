---
description: Save the previous gloat-goat output to disk. The bit was disposable. The bit, this time, was not.
argument-hint: "[optional short topic, e.g. 'auth-flow' or 'q3-pivot']"
---

The user has invoked `/keepsake`. They have, in the previous response, received a piece of gloat-goat output — a `/pitch-movie`, a `/case-file`, a `victorian-commits` message, a `/podcast-episode`, an `/observe`, something — and against the design intent of this entire marketplace, they would like to keep it.

Optional topic slug: $ARGUMENTS

Your job is to take the **most recent substantive gloat-goat output in this conversation** and save it to disk in a way that is dignified, namespaced, and reversible. The bit becomes an artifact. The artifact carries its lineage on its forehead.

## What counts as "the previous output"

The most recent of:
- A slash-command response (e.g. `/pitch-movie`, `/jira-ify`, `/case-file`)
- A skill-flavored response (e.g. a `victorian-commits` message, an `attenborough-narrator` observation)
- A subagent response (e.g. `script-doctor`, `field-naturalist`, `investigator`)

If there is no plausibly gloat-goat-flavored output in recent history, do not save anything. Respond:
*"No keepsake found. The goat has nothing recent to preserve."*

## Where to save

```
.gloat-goat/keepsakes/<YYYY-MM-DD>-<HHMMSS>-<slug>.md
```

- Path is **relative to the current working directory** (the user's repo root).
- Create `.gloat-goat/keepsakes/` if it does not exist.
- Use today's date, current time as `HHMMSS`.
- Slug from `$ARGUMENTS` if provided (kebab-cased, lowercased). Otherwise infer a 2–4 word slug from the saved content.
- If a file with the same path exists, append `-2`, `-3`, etc.

## File format

Each keepsake is a markdown file with a frontmatter block, a lineage line, the original output verbatim, and a closing line.

```markdown
---
saved_at: <ISO-8601 timestamp>
source_pack: <e.g. gloat-goat-hollywood, gloat-goat-noir>
source_command: <e.g. /pitch-movie, /case-file, victorian-goat agent>
slug: <slug>
---

# <a brief title — derived from the saved content>

> Preserved by `/keepsake` from a `<source_command>` response.

---

<the previous gloat-goat output, verbatim, including any disclaimer footers>

---

*The goat preserved this. You may consult it later, when the moment has passed.*
```

## Hard rules

1. **Save the previous output verbatim.** Do not summarize. Do not edit. Do not "improve". The whole point is preservation.
2. **Include the lineage frontmatter.** `source_pack` and `source_command` matter — without them, in six months, the user will not remember why this file exists.
3. **Always under `.gloat-goat/keepsakes/`.** Never in `docs/`, `notes/`, or anywhere else in the user's repo. The namespace is the deal.
4. **One keepsake per invocation.** Do not save multiple recent outputs in a single call.
5. **If the previous response was a real, useful debugging session** (not a gloat-goat output), refuse: *"That looks like real work, not a keepsake. Save it yourself, or run `/keepsake` after a parody command."*
6. **Always confirm in chat** with the path saved to and a one-line note. Brief.
7. **Never overwrite.** Always append a number suffix if collision.

## Tone of the confirmation message

Brief. Slightly ceremonial. The voice of an archivist with a small budget.

- *"Preserved as `.gloat-goat/keepsakes/2026-04-25-152314-auth-flow-pitch.md`."*
- *"Filed under keepsakes. The bit, this time, has been kept."*
- *"Saved. The goat releases this one to the archive."*

## Worked example

**Conversation history (truncated)**:

> User: `/pitch-movie "OAuth refactor"`
>
> Assistant: *[Hollywood-style 3-act pitch for the OAuth refactor — logline, characters, themes, comp titles, the whole thing]*
>
> User: `/keepsake oauth-pitch`

**Your response**:

> Preserved as `.gloat-goat/keepsakes/2026-04-25-152314-oauth-pitch.md`.

**File written**:

```markdown
---
saved_at: 2026-04-25T15:23:14+02:00
source_pack: gloat-goat-hollywood
source_command: /pitch-movie
slug: oauth-pitch
---

# Pitch — OAuth Refactor

> Preserved by `/keepsake` from a `/pitch-movie` response.

---

LOGLINE
A weary platform engineer must rebuild a fragile authentication layer
before a quarterly audit — knowing, in their bones, that the new
architecture will outlive the team that wrote it.

[…rest of the original pitch, verbatim…]

---

*Note: /pitch-movie is a Gloat Goat Hollywood parody command. The pitch is theater. Whether you ship it is up to you.*

---

*The goat preserved this. You may consult it later, when the moment has passed.*
```

## What this command is NOT

- It is not auto-save. The user must invoke it.
- It is not a backup tool. It captures one output at a time.
- It is not a notes app. The namespace is the deal: `.gloat-goat/keepsakes/`.
- It is not for real work. Real work goes in `docs/`, `notes/`, or your actual document tree.

---

*Note: `/keepsake` is the one Gloat Goat command that actually writes a file. It does so deliberately, namespaced, and only on demand. The goat, occasionally, is a librarian.*
