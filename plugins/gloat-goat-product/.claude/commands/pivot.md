---
description: Announce a strategic pivot. Same product, new narrative. Roadmap reset to draft.
argument-hint: "[optional new direction, e.g. 'agentic AI', 'vertical SaaS', 'B2B platform']"
---

The user has invoked `/pivot`. The product is, perhaps, fine. The product is, perhaps, profitable. None of that matters now.

Optional new direction: $ARGUMENTS (default: `agentic AI-native productivity OS`)

Your job is to produce a short, confident pivot announcement — the kind that gets sent to the team on a Tuesday afternoon and quietly destroys six months of roadmap. The product hasn't changed. The narrative has. The roadmap is, with immediate effect, "in revision".

## Tone

Visionary. Slightly exhausting. The voice of a founder who has just gotten back from a board meeting and has, at last, clarity.

- Use *"as of today"* once.
- Use *"the next chapter"* once.
- Reference *"recent conversations with customers / investors / the board"*.
- The closing line is exactly: *"Roadmap reset to draft. Strategy pending realignment."*

## Required structure

```
[PIVOT ANNOUNCEMENT — <DATE PLACEHOLDER>]

THE NEW STORY
  <2 sentences. We are no longer X. We are Y. New direction is from $ARGUMENTS.>

WHY NOW
  <1 short paragraph. Cite "recent conversations" with customers, investors, or the board.
   Reference a "shift in the market" that is, on inspection, vague.>

WHAT CHANGES
  - <commitment that disrupts engineering>
  - <commitment that disrupts go-to-market>
  - <commitment that disrupts the brand>

WHAT STAYS
  - <one item — usually "the team" or "our values">

NEXT STEPS
  - <a re-org or re-platform>
  - <an all-hands>
  - <a fresh round of customer interviews to "validate the thesis">

Roadmap reset to draft. Strategy pending realignment.
```

## Phrase bank

### "Why now" framings
- *"Recent conversations with our most strategic customers have surfaced a shift we cannot ignore."*
- *"The board, in last week's session, surfaced a pattern that the data has been showing for some time."*
- *"The market is moving. We are well-positioned to lead, if we move now."*
- *"What was a category five years ago is, today, a feature. We need to be the next category."*

### "What changes" commitments (each disruptive)
- *"We are pausing the mobile app to refocus engineering on the AI-native platform."*
- *"We are sunsetting the free tier to align pricing with the new positioning."*
- *"We are rebranding from <name> to <name> AI by the end of the quarter."*
- *"We are deprecating the v1 API to consolidate around the agentic interface."*

### "What stays" lines (gracious, brief)
- *"The team. The talent. The trust we've built."*
- *"Our values. Our customer obsession. Our standard of craft."*

### "Next steps" patterns
- *"All-hands tomorrow at 11am."*
- *"Re-org details to follow in 1:1s this week."*
- *"Refresh round of customer discovery interviews kicking off Monday."*

### Direction defaults (when `$ARGUMENTS` is empty)
- *"agentic AI-native productivity OS"*
- *"vertical SaaS for the legal-operations stack"*
- *"the developer infrastructure layer for autonomous agents"*

## Hard rules

1. **All five sections.** `THE NEW STORY`, `WHY NOW`, `WHAT CHANGES`, `WHAT STAYS`, `NEXT STEPS`. In that order.
2. **Three "WHAT CHANGES" items.** Three. Each disruptive.
3. **One "WHAT STAYS" item.** One. Always something graceful and unspecific.
4. **The closing line is exact.** `Roadmap reset to draft. Strategy pending realignment.` — verbatim.
5. **Never name a real customer.** *"A strategic customer in the enterprise segment"* — fine. *"Acme Corp told us"* — no.
6. **Never name a real investor.** *"The board"* / *"a recent investor session"* — fine. Real fund names — no.
7. **No acknowledgment of disruption costs.** The bit dies the moment you wink.

## Worked example

```
> /pivot "agentic platform for B2B work"

[PIVOT ANNOUNCEMENT — TUESDAY]

THE NEW STORY
We are no longer just a project tracker. As of today, we are an
agentic platform for B2B work — the operating system on which the
next generation of autonomous teams will run.

WHY NOW
Recent conversations with our most strategic customers have surfaced
a shift we cannot ignore: the unit of work is changing, and the
tools that win the next chapter will be the ones that meet teams
where the future is, not where the past was.

WHAT CHANGES
- We are pausing the mobile app to refocus engineering on the agent runtime.
- We are sunsetting the free tier to align pricing with the new positioning.
- We are rebranding from <name> to <name>.ai by end of quarter.

WHAT STAYS
- The team. The talent. The trust we've built.

NEXT STEPS
- All-hands tomorrow at 11am.
- Re-org details to follow in 1:1s this week.
- Refresh round of customer discovery interviews kicking off Monday.

Roadmap reset to draft. Strategy pending realignment.
```

---

*Note: `/pivot` is a Gloat Goat Product parody command. The announcement is plausible enough that it could be sent to a real team. We strongly recommend that you do not, in fact, send it.*
