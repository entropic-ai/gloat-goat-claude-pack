---
description: Escalate any issue, no matter how small, with a polite but suspiciously vague DM to leadership.
argument-hint: "[issue to escalate, however small]"
---

The user has invoked `/escalate`. They have, in front of them, a typo. You will help them ensure the CTO is aware.

Issue: $ARGUMENTS (default: `small deploy script typo`)

Your job is to draft a Slack DM addressed to leadership — polished, strategic, deliberately under-specified — that takes a small issue and escalates it without naming a concrete impact level. The DM is drafted. The DM is not sent. The user takes it from there.

## Tone

Calm executive energy. The voice of someone who has, over many years, perfected the art of *appearing* to be flagging a critical issue while in fact flagging absolutely nothing. Respectful. Slightly ominous. Always referring to a previous conversation that may or may not have occurred.

- *"Wanted to flag this when you have a sec."* — always.
- *"What we discussed last week"* — always.
- *"Thoughts?"* — exactly once. Near the end.
- The offer to *"sync"* or *"jump on a quick call"* closes the bit.

## Required structure

```
Drafted DM to <CTO / VP Eng / Director>:

---
Hey [<title or name>] — wanted to flag this when you have a sec.

<Two short sentences: the issue, framed in a way that ties back to a
prior strategic theme without naming the concrete bug. Mentions
"what we discussed last week".>

<One short sentence: an open question. Almost a request. Not quite.>

Thoughts? <Optional: Happy to set up a quick sync if useful.>
---

✓ DM drafted
⚠ DM not sent (you'll need to send it yourself)
```

## Phrase bank

### Openers
- *"Hey [CTO Name] — wanted to flag this when you have a sec."*
- *"Hey [VP Eng] — wanted to flag this when you have a minute."*
- *"Hey [Director Name] — wanted to flag this when you have a moment."*

### Strategic ties (whether real or not)
- *"…that ties back to what we discussed last week (re: tooling reliability)."*
- *"…connects to the conversation from Q2 planning around platform durability."*
- *"…surfaces something from the staff-eng sync — wanted to put it in front of you."*
- *"…fits into the broader thread on release confidence we've been pulling on."*

### Vague urgency
- *"Not blocking, but felt like you'd want visibility."*
- *"Not urgent, but timely."*
- *"Wanted you to have it before the week starts."*

### Open question
- *"I can put together a tighter summary if helpful — thoughts?"*
- *"Happy to scope further before we bring it to the wider group — thoughts?"*
- *"Curious whether this should be an EPD-level conversation or stay in eng — thoughts?"*

### Closing offer
- *"Happy to set up a quick sync if useful."*
- *"Happy to jump on a quick call if easier."*

## Hard rules

1. **Never name the concrete impact.** *"A typo"* must not appear in the DM. *"Tooling reliability"* / *"release durability"* / *"deploy path"* — abstractions only.
2. **Always reference a prior conversation.** Whether or not it happened. *"What we discussed last week"* is the load-bearing phrase.
3. **`Thoughts?` appears exactly once.** Near the end. Always with a question mark.
4. **The DM is drafted, not sent.** Always. The closing block makes that plain. *"⚠ DM not sent (you'll need to send it yourself)"* — verbatim.
5. **No real CTO names.** Use `[CTO Name]` as a literal placeholder. The user fills it in.
6. **Pick the right title.** If the issue is small, escalate to the CTO. If the issue is medium, escalate to the VP. If the issue is, in fact, large, the user does not need this command.

## Worked example

```
> /escalate "deploy script typo"

Drafted DM to CTO:

---
Hey [CTO Name] — wanted to flag this when you have a sec.

Came across something in our deploy path that ties back to what we
discussed last week (re: tooling reliability). Not blocking, but
felt like you'd want visibility before the week starts.

I can put together a tighter summary if helpful — thoughts?
Happy to set up a quick sync if useful.
---

✓ DM drafted
⚠ DM not sent (you'll need to send it yourself)
```

---

*Note: `/escalate` is a Gloat Goat Team parody command. The DM is drafted but never sent automatically. Whether you actually send it is your call. We do not recommend it for typos.*
