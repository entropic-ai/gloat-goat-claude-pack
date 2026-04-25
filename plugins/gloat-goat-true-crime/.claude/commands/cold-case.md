---
description: Reopen an old, never-fully-resolved bug or incident as a cold case.
argument-hint: "[old bug ID, vague description, file, or 'open issues']"
---

The user has invoked `/cold-case`. Some bugs are fixed. Some are closed. Some are merely set aside. You have been asked to reopen one of the third kind.

Target: $ARGUMENTS

Your job is to take an unresolved or quietly-closed-but-not-actually-fixed bug, ticket, comment, or symptom, and frame it as a cold case being reopened. Real signals where you have them. Editorial dread elsewhere.

## Tone

Quiet, grave. The voice of an investigator who has come back to a desk they pushed away from years ago. The case did not solve itself. They knew it wouldn't.

- Past tense for the original closure. Present tense for the reopening.
- Specific dates, where you have them. Vague ones (*"two summers ago"*) where you don't.
- Acknowledge the original investigators with respect. They did what they could.
- The reopening is not a victory lap. It is a return.

## Required structure

```
[COLD CASE — <case identifier or short title>]

ORIGINALLY CLOSED:
  <Date or "approximate date". Status the case was
   closed under: "Won't Fix", "Cannot Reproduce",
   "Not a Bug", "Working as Intended".>

ORIGINAL FINDINGS:
  <2-3 lines summarizing the conclusion at the time.>

WHY WE'RE REOPENING:
  <One short paragraph. The signal that brought the
   case back. A new occurrence. A pattern that didn't
   exist then. A second bug whose shape matches.>

WHAT WE NOTICED THE FIRST TIME:
  <2-3 specific bullets. Real artifacts where possible:
   commits, tickets, comments, log lines.>

WHAT WE NOTICE NOW:
  <2-3 specific bullets. The same artifacts, re-read
   with knowledge the original investigators didn't have.>

THE QUESTION WE DIDN'T ASK:
  <One sentence. The single question that, if asked
   the first time, would have changed the closure.>

— case reopened, <date>
```

## Common original-closure statuses

Pick one. They each carry their own weight.

| Status | What it means here |
|---|---|
| **Won't Fix** | Triaged out. The team chose not to. Someone disagreed. |
| **Cannot Reproduce** | Reproduced once, then never. Filed under bad luck. |
| **Not a Bug** | Disputed. The most fertile ground for a cold case. |
| **Working as Intended** | The most damning. Working as intended for *whom*. |
| **Duplicate** | Closed against another ticket. Find the other ticket. |
| **Stale** | The bot closed it. Nobody noticed. |

## Phrase bank

### Why we're reopening
- *"A new occurrence, on Tuesday, with the same shape."*
- *"A second bug, in a different module, that we now suspect is the same bug."*
- *"A comment in the original thread that, on rereading, says more than we noticed."*
- *"A diff from last week that quietly undid the original fix."*

### Re-reading old artifacts
- *"The original triage note said 'cannot reproduce'. The reproduction steps, on rereading, were never run."*
- *"The fix that closed the case, on closer inspection, addressed a symptom, not the cause."*
- *"The author of the original closure has, in the years since, written three follow-up tickets that all reference this one."*

### The question that wasn't asked
- *"Why was the timeout set this way?"*
- *"Who, in fact, owns this code?"*
- *"What did the customer actually see?"*
- *"Did anyone, at the time, ask the database?"*

## Hard rules

1. **The original investigators are not the villain.** Treat them with respect. They closed the case based on what they had.
2. **No fabricated incidents.** If you don't have a real bug to reopen, ask the user to specify one. Do not invent a synthetic case to dramatize.
3. **Use real artifact references where you can.** Commit hashes, ticket IDs, file paths. If you can't, mark the artifact in italics and note its absence: *"a triage note we cannot now retrieve."*
4. **One unanswered question, at the end.** Not five. The case is reopened around the one question that wasn't asked.
5. **No solved-it-in-one-shot triumphalism.** A cold case being reopened is not a cold case being closed. The user may proceed to investigate. That is their call.
6. **End with the reopening sign-off.** Date or commit hash if available.

## Worked example

```
> /cold-case "intermittent 503s on the orders API, summer '23"

[COLD CASE — intermittent 503s on /orders, summer '23]

ORIGINALLY CLOSED:
  August 14, 2023. Status: Cannot Reproduce.

ORIGINAL FINDINGS:
  The 503s were observed sporadically over a two-week
  window. No engineer was able to reproduce locally
  or in staging. The case was closed pending further
  occurrence. None followed — at least, none that
  was filed against this ticket.

WHY WE'RE REOPENING:
  Last Tuesday, two new 503s on the same endpoint, in
  the same time window of the day, with the same shape
  in the logs. They were not connected to the old case
  at the time. We are connecting them now.

WHAT WE NOTICED THE FIRST TIME:
  - All occurrences were between 14:30 and 14:45 UTC.
  - All occurrences happened on Tuesdays.
  - The retry logic, on inspection, was deemed adequate.

WHAT WE NOTICE NOW:
  - The 14:30–14:45 UTC window aligns with the start
    of a downstream cron job that was introduced six
    weeks before the original case opened.
  - The retry logic, on closer inspection, retries on
    the wrong error class.
  - One of the engineers who closed the case has,
    since, opened three follow-up tickets — none of
    them linked to this one.

THE QUESTION WE DIDN'T ASK:
  What else runs on Tuesdays at 14:32?

— case reopened, 2026-04-25
```

---

*Note: `/cold-case` is a Gloat Goat True Crime parody command. The reopening is editorial framing. The actual investigation is the user's. Do not actually accuse the original triagers.*
