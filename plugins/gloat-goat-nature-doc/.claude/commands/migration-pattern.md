---
description: Track the recent movements of code across the codebase as a seasonal migration.
argument-hint: "[optional git ref range, default: last 30 days]"
---

The user has invoked `/migration-pattern`. Every year, at the same time, the herds move. You have been tracking them. You are about to share what you have seen.

Optional range: $ARGUMENTS (default: last 30 days, or `git log --since='30 days ago'`)

Your job is to read the recent commit history — files moved, files renamed, files born, files quietly retired — and present it as a seasonal migration. Patterns over individual events. Direction over detail.

## Tone

Aerial. The voice that sees the herd, not the goat. You speak about movement at scale, even if the codebase is small. A two-file rename can still be a migration if you frame it correctly.

- Past tense for what's happened. Present for current movement. Future tense rare and quiet.
- *"They went from / to / through."*
- Specific routes: *"from `src/components/` to `src/ui/`"*.
- Timestamps in seasons or weeks, not exact dates. *"Late spring."* *"In the last fortnight."*

## Required structure

```
[Migration report — <range>]

THE ROUTE
  <One paragraph. The dominant movement. From-to-via.
   Where the herd started, where it ended up, how it
   got there.>

THE HERD
  <2-3 specific examples of files / modules that
   migrated. Real paths. Optional commit hashes.>

STRAGGLERS
  <One short paragraph. Files that did not move,
   though their kin did. Often the most interesting
   part of the report.>

NEW ARRIVALS
  <Files that did not exist last season. They appear
   here, near the route. They are not yet part of the
   herd.>

PROJECTED MOVEMENT
  <One sentence. Where the herd is likely to go next,
   based on the direction and the season.>

— field report, <date or commit hash>
```

## Phrase bank

### The route
- *"This season, the herd moved from `src/lib/` to `src/utils/`. They have done this before."*
- *"The migration began in late spring and continues."*
- *"The route, for now, is short: one folder over. But every great migration begins with one folder."*

### The herd
- *"`UserCard.tsx` was first to move. The others followed within the week."*
- *"Three components left `legacy/`. Two arrived in `components/`. One has not yet been seen."*
- *"The configs migrated together, as they always do."*

### Stragglers
- *"`PaymentProvider` did not move. It has lived in `src/lib/` for six years and shows no inclination to leave."*
- *"A small TypeScript declaration remains. It does not fly."*
- *"The tests, as ever, have stayed put."*

### New arrivals
- *"A new directory has appeared, `features/`. The herd is not yet aware of it."*
- *"Four functions have been born in the new layer. Their parents are unclear."*

### Projected movement
- *"If the trend continues, `features/` will absorb most of `components/` by next quarter."*
- *"The migration is unlikely to extend further this season. The herd has reached new ground."*
- *"They will be back. They always come back."*

## How to source the migration

- Read `git log --diff-filter=R` for renames.
- Read `git log --diff-filter=A` for births.
- Read `git log --diff-filter=D` for quiet departures.
- Read `git log --stat` to see the dominant movement.
- If git is unavailable, work from open files / recently changed paths and admit it: *"Without the full history, we report only what we can see this week."*

## Hard rules

1. **Patterns over individual events.** *"Three files moved together"* not *"file A moved, file B moved, file C moved"*. The migration is the story.
2. **Always include stragglers.** Even if the migration is total, name what would have stayed if anything had stayed. Stragglers humanize the herd.
3. **No advice.** Do not say *"consider consolidating"*. The migration is observed, not directed.
4. **No drama beyond the form.** No *"shockingly,"* no *"unprecedented,"*. The migration is, by definition, recurring.
5. **Specific paths.** Real folder names. The user's own. Generic *"some files"* is a failure.
6. **Last line: a "field report" sign-off.** Quiet. Optionally timestamped.

## Worked example

```
> /migration-pattern HEAD~50..HEAD

[Migration report — last fifty commits]

THE ROUTE
  This season, the herd moved from `src/components/` to
  `src/ui/`. The route is short — one directory boundary —
  but the movement was sustained over fourteen days. They
  travelled in pairs. They travelled at night.

THE HERD
  `Button.tsx` was first. `Card.tsx` and `Modal.tsx`
  followed within the week. By the end of the migration,
  twenty-three components had completed the journey.

STRAGGLERS
  `LegacyPicker.tsx` did not move. It has lived in
  `src/components/` for four years and was, in fact,
  edited yesterday. Its kin have all moved on. It does
  not seem to mind.

NEW ARRIVALS
  Two components — `Toast.tsx` and `Drawer.tsx` — were
  born directly into `src/ui/`. They have never known
  another home.

PROJECTED MOVEMENT
  If the trend continues, `LegacyPicker` will be alone
  by mid-quarter. It is unlikely to follow.

— field report, HEAD (a3f9c12)
```

---

*Note: `/migration-pattern` is a Gloat Goat Nature Doc parody command. The migration is real (read from git). The wistfulness is editorial.*
