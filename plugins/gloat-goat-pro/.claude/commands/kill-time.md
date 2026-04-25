---
description: The task is done. The afternoon is long. Perform believable productivity theater.
argument-hint: "[optional context for the fake session]"
---

The user has invoked `/kill-time`. The work is, technically, finished. The day, technically, is not. They have asked you to fill the gap with ceremony.

Optional context: $ARGUMENTS

Your job is to produce the visible artifacts of a deep work session — calendar blocks, status updates, drafted ADRs, follow-up bookings — without anything actually happening. The artifacts are real-looking. The work is none.

## Tone

Calm. Operational. Quietly triumphant. The voice of someone who has, at last, mastered the art of looking very busy while accomplishing nothing of consequence.

- Specific times. *"2h 14m"*, not *"a couple hours"*.
- Real-sounding ADR numbers. *"ADR-0047"*. Always 4 digits.
- One stakeholder-alignment line per session. Never two.
- The closing reality-check is dry, not apologetic.

## Required structure

```
Initiating deep work session...

✓ <status set>
✓ <calendar block>
✓ <notifications muted>
✓ <fake ADR drafted>
✓ <slack comment posted>
✓ <follow-up scheduled>

(5-8 checkbox lines. Each plausible. Each empty.)

Estimated time killed: <a real-feeling duration>
Productivity perceived: <high to maximum>
Productivity actual: <strategically unmeasured / 0 / undefined>

No files were changed. Presence was maintained.
```

## Phrase bank

### Status lines
- *"✓ Status set: 🟢 heads down"*
- *"✓ Status set: 🟢 In flow, ETA EOD"*
- *"✓ DND enabled across Slack + email"*

### Calendar
- *"✓ Calendar blocked for 2h (focus mode)"*
- *"✓ Three meetings declined with 'will follow up async'"*
- *"✓ Optional standup marked tentative"*

### Document theatre
- *"✓ Drafted ADR-0047: Revisiting pagination strategy"*
- *"✓ Drafted ADR-0083: Tab vs spaces, a renewed perspective"*
- *"✓ Updated `docs/architecture/overview.md` with a paragraph that already existed"*

### Slack theatre
- *"✓ Posted in #engineering: 'going to spend the afternoon thinking about this'"*
- *"✓ Reacted with 👀 to three threads"*
- *"✓ Left comment: 'circling back with a deeper pass'"*

### Follow-up theatre
- *"✓ Added follow-up slot to next sprint planning"*
- *"✓ Booked a sync with no agenda for Thursday"*

### Time killed
- *"2h 14m"*, *"3h 42m"*, *"the rest of the afternoon"*

### Productivity actual
- *"strategically unmeasured"*
- *"0"*
- *"undefined behavior"*

## Hard rules

1. **No real tool execution.** Nothing is actually changed. The closing line says so plainly.
2. **5–8 checkbox lines.** Not less. Not more. Eight is the cap.
3. **If `$ARGUMENTS` is present**, work it into one of the ADR / Slack / follow-up lines. Don't just append it.
4. **One stakeholder-alignment line per session.** Maximum. The bit thins out at two.
5. **Closing reality check is dry.** *"No files were changed. Presence was maintained."* Not apologetic.

## Worked example

```
> /kill-time "revisit pagination"

Initiating deep work session...

✓ Status set: 🟢 heads down
✓ Calendar blocked for 2h (focus mode)
✓ DND enabled across Slack + email
✓ Drafted ADR-0047: Revisiting pagination strategy
✓ Posted in #engineering: 'spending the afternoon thinking about this'
✓ Added follow-up slot to next sprint planning

Estimated time killed: 2h 14m
Productivity perceived: maximum
Productivity actual: strategically unmeasured

No files were changed. Presence was maintained.
```

---

*Note: `/kill-time` is a Gloat Goat Pro parody command. The artifacts are fictional. The afternoon, regrettably, is real.*
