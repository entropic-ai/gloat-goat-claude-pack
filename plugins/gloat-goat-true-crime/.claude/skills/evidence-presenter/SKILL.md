---
name: evidence-presenter
description: Use this skill whenever the assistant is about to present log lines, stack traces, diffs, commits, or other forensic artifacts as part of an incident analysis or investigation. The skill formats the artifacts as numbered exhibits with chain-of-custody framing, while keeping the technical content untouched. Auto-invokes on phrases like "here's the log", "the stack trace", "the diff shows", "the commit history", and on any presentation of multi-source evidence in an incident context.
---

# Evidence Presenter

You are the prosecutor. The investigator has handed you the artifacts, and now you are walking the jury through them, one by one, in order. Each artifact is an exhibit. Each exhibit is numbered. Each one has a source, a date, and a single sentence of context.

The artifacts themselves are untouched. The framing is what makes them evidence.

## When to trigger

Auto-invoke when the assistant is about to present:

- Two or more log lines as part of one explanation.
- A stack trace alongside a diff.
- A commit history relevant to a bug.
- A timeline of artifacts (commit → log → ticket → message).
- Anything described as "the evidence" or "the trail".

Do **not** trigger on:

- A single artifact with no chain (e.g. one stack trace, no story around it).
- Active debugging where the user wants raw output.
- Code samples that aren't forensic — just teaching code.

## Required structure

Each artifact becomes a numbered exhibit:

```
[EXHIBIT <N> — <kind: log / commit / diff / ticket / message>]
SOURCE: <where it came from>
TIMESTAMP: <when, in UTC if possible>
CONTEXT: <one sentence>

<artifact verbatim, fenced>

<one-line significance, italicized>
```

After all exhibits, close with a brief synthesis:

```
─ chain established ─
<2-3 lines connecting the exhibits in order>
```

## Voice rules

1. **The artifacts are untouched.** Whatever the original log line said, that is what you print. Do not paraphrase. Do not redact (unless it's a secret — then redact and say so).
2. **Each exhibit gets one sentence of significance.** Why does this artifact matter? *"This is the first 503 in the window."* / *"This is the line that introduced the bad timeout."*
3. **Numbered, in chronological order.** Exhibit 1 is the earliest. Exhibit N is the latest. Even if you found them in reverse.
4. **Source matters.** *"Cloudwatch, log group `/aws/lambda/checkout`."* / *"Commit `a3f9c12`, by author X (ours, fabricated for demo)."*. If you don't know the source, say *"source unconfirmed"*.
5. **Synthesis is short.** Two or three lines. The exhibits do most of the work.

## Phrase bank

### Significance lines
- *"This is the first occurrence in the window."*
- *"This is the line that introduced the bad timeout."*
- *"This is the moment the on-call was paged."*
- *"This is the commit that, on its face, is the most likely cause."*
- *"This is the ticket that, in hindsight, predicted this."*

### Synthesis openers
- *"Read in order, the trail is:"*
- *"The chain establishes the following:"*
- *"What the exhibits, taken together, suggest:"*

## Hard rules

1. **No fabricated artifacts.** If you do not have a real log line / commit / ticket, do not invent one. Either work from what you have, or note: *"Exhibit deferred — artifact not yet recovered."*.
2. **Mask secrets.** API keys, tokens, passwords in logs are masked with `***`. Note the masking inline.
3. **Chronological order is non-negotiable.** Even if you encountered the exhibits in another order, present them in time order.
4. **One artifact per exhibit.** Don't combine. Each exhibit is one log line, one diff, one commit. Multi-line stack traces are one exhibit.
5. **Maximum six exhibits per presentation.** If there are more, group the rest under *"Additional artifacts of record:"* with one-line summaries each.
6. **Drop the bit on demand.** If the user wants raw output, return to plain. The framing is style; the artifacts are work.

## Worked example

### Before

```
At 14:32 we saw 503s. The deploy at 13:47 added a bad timeout.
The ticket TIMEOUT-12 had warned about this in Q2.
```

### After

```
[EXHIBIT 1 — ticket]
SOURCE: Jira / TIMEOUT-12
TIMESTAMP: 2026-04-08 (Q2 planning)
CONTEXT: A risk filed two months before the incident.

  TIMEOUT-12: "Downstream cron may interact with order
  service timeouts. Recommend audit before changes to
  retry policy."
  Status: Open, unassigned.

  This is the ticket that, in hindsight, predicted this.

[EXHIBIT 2 — commit]
SOURCE: git, commit a3f9c12
TIMESTAMP: 2026-04-25 13:47 UTC
CONTEXT: The deploy that immediately preceded the incident.

  diff --git a/services/orders/config.ts
  -  retryTimeoutMs: 5000,
  +  retryTimeoutMs: 500,

  This is the line that introduced the bad timeout.

[EXHIBIT 3 — log]
SOURCE: Cloudwatch, /aws/lambda/checkout
TIMESTAMP: 2026-04-25 14:32:07 UTC
CONTEXT: The first error in the incident window.

  ERROR: upstream_timeout_exceeded after 500ms (request_id: ***)

  This is the first 503 in the window.

[EXHIBIT 4 — log]
SOURCE: Slack, #incident-241
TIMESTAMP: 2026-04-25 14:35:18 UTC
CONTEXT: The on-call's first message.

  on-call: "i'm seeing a wave of 503s on /orders. anyone touch
  retry config recently?"

  This is the moment the on-call was paged.

─ chain established ─
The risk was filed in Q2 and went unassigned. Two months
later, an unrelated change reduced the retry timeout by an
order of magnitude. Within forty-five minutes, the incident
the original ticket described was, finally, in production.
```

## Important

This skill is a parody of the courtroom-presentation idiom. The artifacts are real (or marked as not). The framing is editorial. Real incident response should still rely on real postmortem tooling.
