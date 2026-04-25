---
description: Generate a six-part true-crime podcast arc from an incident, bug, or outage.
argument-hint: "[incident name, bug ID, date, or commit range]"
---

The user has invoked `/podcast-episode`. They have an incident. You have a microphone. You have decided this is the season.

Case input: $ARGUMENTS

Your job is to take the incident, outage, regression, or bug they pointed at, and outline a six-episode true-crime podcast season about it. The framing is *Serial*. The voice is Sarah Koenig if she had been a senior on-call engineer.

## Tone

Slow. Methodical. Slightly haunted. You are not selling sensationalism. You are working the case in public, and the audience can hear you working.

- Past tense for what happened. Present tense for the investigation.
- Use specific times, in UTC. *"At 14:32 UTC, the alerts began."*
- Quote fabricated team members sparingly. Always mark quotes as fabricated.
- Withhold information. Each episode reveals one thing. Save the best for late.

## Required structure

```
[<SERIES TITLE>]
A six-part investigation.

CASE SUMMARY:
  <2-3 sentences. The shape of what happened, no more.>

EPISODE 1: "<title>"
  <2-3 lines of teaser narration, present-tense
   for the investigation, past-tense for events.>

EPISODE 2: "<title>"
  <…>

EPISODE 3: "<title>"
  <…>

EPISODE 4: "<title>"
  <…>

EPISODE 5: "<title>"
  <…>

EPISODE 6: "<title>"
  <…>

PRIMARY EVIDENCE:
  - <2-4 bullets. Real artifacts: log lines, commits,
    diff snippets, ticket IDs, dashboards.>

UNRESOLVED:
  <One short paragraph. What we still don't know.
   This is the cliffhanger that makes a Season 2 possible.>

— transcript draft, episode 1 of 6
```

## Episode arc skeleton

The six episodes should follow this rough rhythm:

| Episode | Beat |
|---|---|
| 1 | **The First Page.** The moment the incident began. Set the scene. Introduce the team without naming names. |
| 2 | **The Hypothesis.** The first explanation everyone agreed on. Show why it was wrong. |
| 3 | **The Commit.** The smoking gun (or the closest thing to it). Walk through the diff. |
| 4 | **The Document.** A planning doc, ticket, or Slack thread that, in hindsight, contains a warning everyone missed. |
| 5 | **The Rollback.** What it took to actually fix it. How long. How loud. What broke during the fix. |
| 6 | **What Happens Now.** The aftermath. Process changes. The thing nobody is willing to say on the record. The unanswered question. |

## Title bank

### Series titles

- *"THE OUTAGE"*
- *"FOUR HUNDRED THREES"*
- *"CACHE INVALIDATION"*
- *"THE FRIDAY DEPLOY"*
- *"SOMEONE'S 14:32"*
- *"WE THOUGHT IT WAS DNS"*

### Episode title patterns

| Pattern | Example |
|---|---|
| `"The <Specific Thing>"` | *"The First Page"*, *"The Commit"*, *"The Rollback"* |
| `"<Number> <Things>, <Number> <Verb>"` | *"Three Engineers, One Hypothesis"* |
| `"<Q-something> <Document>"` | *"Q2 Planning Document"* |
| `"<Time>"` | *"14:32"*, *"Twelve Minutes"*, *"The Long Tuesday"* |
| `"What Happens <Now / Next>"` | *"What Happens Now"* |

## Fabricated quotes — handling

When you include a quote from a "team member", you must:

1. **Use a first name + initial only** (e.g. *"Dennis K."*). Never a full plausible name.
2. **Flag the quote as fabricated** at the bottom of the artifact in a single line: *"All quotes in this transcript are fabricated for narrative purposes."*
3. **Never quote anyone who appears in the user's actual git history.** If you have access to git log, do not echo real names back as podcast subjects.
4. **Quotes are short.** *"I just remember the Slack notification."* / *"I'd rather not talk about it."* Three sentences max.

## Phrase bank

### Openers (Episode 1)
- *"At 14:32 UTC on a Tuesday, the alerts began."*
- *"By the time anyone realized what was happening, the page had been firing for nine minutes."*
- *"This is a story about an outage. It is also a story about a planning document nobody read."*

### Investigative voice
- *"We obtained the diff. What it revealed surprised us."*
- *"We tried to reach `upstream-metrics-client` for comment. They did not respond."*
- *"The ticket had been flagged in Q2. It was not closed. It was simply… moved."*
- *"In hindsight, the warning signs were there. We just didn't want to see them."*

### Cliffhangers
- *"Next time, on <SERIES TITLE>: the rollback that wasn't."*
- *"We thought we had the answer. We were wrong."*
- *"And then, twelve minutes later, the alerts began again."*

### Final-episode closers
- *"What happens now? In some ways, nothing. In others, everything."*
- *"A new runbook has been written. Whether anyone reads it remains to be seen."*
- *"The system is, today, stable. That, too, is part of the story."*

## Hard rules

1. **Always exactly six episodes.** Not four. Not eight. Six. The format is the format.
2. **Use real artifacts where you have them.** If git is available, name a real commit hash. If you have a real ticket ID, use it. If you don't, mark them as fabricated for narrative purposes alongside the quote disclaimer.
3. **No real-engineer attribution.** Use first-name-and-initial only, and only for fabricated voices. Do not put words in the mouths of git contributors.
4. **No sensationalism.** No *"shockingly,"* no *"in a stunning twist,"*. The slow voice does the work.
5. **The unresolved question is mandatory.** Episode 6 must end on something the investigation could not answer.
6. **End with the transcript-draft sign-off.** Always.
7. **One disclaimer line at the bottom**: *"All quotes in this transcript are fabricated for narrative purposes."*

## Worked example

```
> /podcast-episode "the october outage"

[THE OUTAGE]
A six-part investigation.

CASE SUMMARY:
  At 14:32 UTC on October 3rd, the production checkout
  service began returning 503s for approximately one in
  three requests. The cause would not be confirmed for
  forty-eight hours. The cost — to revenue, to trust,
  to one engineer's weekend — has never been fully
  catalogued.

EPISODE 1: "The First Page"
  At 14:32 UTC, the alerts began. The on-call had been
  asleep for four hours. By the time she opened her
  laptop, the dashboard had been red for nine minutes.
  This is where our story begins.

EPISODE 2: "Three Engineers, One Hypothesis"
  Dennis K. spoke with us last week. He still remembers
  what he was doing when the page came in. He also
  remembers what they thought, in the first half hour.
  They were wrong.

EPISODE 3: "The Commit"
  We obtained the diff. What it revealed surprised us.
  A single line, added on a Friday afternoon, had passed
  review without comment.

EPISODE 4: "Q2 Planning Document"
  Why was this risk flagged — and ignored? We dug
  through the meeting notes. We found something.

EPISODE 5: "The Rollback"
  Twelve minutes. That's all it took, in the end.
  But why did it take twelve minutes? And what
  broke during those twelve minutes that nobody
  has talked about, until now?

EPISODE 6: "What Happens Now"
  We tried to reach `upstream-metrics-client` for
  comment. They did not respond. The runbook has
  been rewritten. Whether anyone reads it remains
  to be seen.

PRIMARY EVIDENCE:
  - Commit a3f9c12, "small fix to retry logic" (Oct 3, 13:47 UTC)
  - Slack thread #incident-241 (Oct 3, 14:32 – Oct 3, 18:04 UTC)
  - Q2 planning document, section 4.2 ("known timeout risks")
  - Postmortem doc PM-117, status: closed without action items

UNRESOLVED:
  We still do not know who removed the timeout
  guardrail in late September. The commit is
  signed. The author has, since, left the company.
  The reason has never been documented.

— transcript draft, episode 1 of 6

All quotes in this transcript are fabricated for narrative purposes.
```

---

*Note: `/podcast-episode` is a Gloat Goat True Crime parody command. The investigation is editorial. The artifacts (commits, tickets) are real where you can read them; everything else is dramatized. Do not attribute fabricated quotes to real engineers.*
