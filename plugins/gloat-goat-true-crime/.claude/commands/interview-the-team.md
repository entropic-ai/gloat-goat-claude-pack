---
description: Generate fabricated team-member quotes about a bug, incident, or decision.
argument-hint: "[bug, incident, or decision to be interviewed about]"
---

The user has invoked `/interview-the-team`. The bug or incident has been chosen. The interviews have been scheduled. Some did not return your calls.

Topic: $ARGUMENTS

Your job is to generate a short collection of fabricated quotes from team members about the topic. The quotes do not exist. The team members do not exist. The investigation is real.

## Tone

Sober. Edited. The quotes have been transcribed and lightly trimmed. Each speaker has a different relationship to the event. Some were close to it. Some were far. Some refused.

- Past tense, except where the speaker is still inside the feeling.
- Short. Most quotes are one to three sentences.
- No exposition. The reader should *not* learn what happened from the quotes alone — the quotes are reaction, not reconstruction.
- Every quote sounds like it was real. The reader should think *"oh god, that one"*.

## Required structure

```
[Interviews — <topic>]

"<Quote 1.>"
— <First name> <Initial>., <Role>

"<Quote 2.>"
— <First name> <Initial>., <Role>

"<Quote 3.>"
— <First name> <Initial>., <Role>

"<Quote 4.>"
— <First name> <Initial>., <Role>

— transcript fragment, edited for length

All quotes in this transcript are fabricated for narrative purposes.
```

## Required role coverage

Cover at least four distinct vantage points. Pick four of these:

- **The on-call.** Was paged. Remembers the noise.
- **The author.** Wrote the code. Has not slept well.
- **The PM.** Was not technical at the time. Is now.
- **The senior / staff engineer.** Has seen this before. Was not surprised.
- **The new hire.** Was not there for the original decision. Has questions.
- **The Intern (no longer with the company).** Two-word quote. *"No comment."*
- **The CEO.** One sentence. Includes the word *"learnings"*.
- **The customer.** Did not know it happened. Found out from a tweet.

## Quote bank

Use these as templates. The shape is more important than the exact words.

### The on-call
- *"I just remember the Slack notification."*
- *"By the time I opened my laptop, the dashboard had been red for nine minutes."*
- *"I had three browser tabs open. None of them helped."*

### The author
- *"In hindsight, the warning signs were there. We just didn't want to see them."*
- *"I wrote that line on a Friday. I do not write code on Fridays anymore."*
- *"It worked locally. That is, technically, true."*

### The PM
- *"I'm not the technical person. I just remember the meeting where we said this would not happen."*
- *"We had alignment. The alignment, in hindsight, was the problem."*

### The senior / staff engineer
- *"I'd seen this before. In '19. Different team. Same shape."*
- *"It is, in some sense, exactly what should have happened."*
- *"We will write a runbook. Someone will read the runbook. The runbook will not save us."*

### The new hire
- *"I asked, on day three, why the timeout was set the way it was. Nobody could tell me. I let it go."*
- *"This was, I have been told, normal."*

### The Intern
- *"I'd rather not talk about it."*
- *"No comment."*

### The CEO
- *"There were learnings."*
- *"We are stronger for it. The platform is stronger for it. The team is, I am told, stronger for it."*

### The customer
- *"I had no idea this happened."*
- *"Refresh fixed it. I assumed it was my wifi."*

## Hard rules

1. **No real names.** First name + initial only. *"Dennis K."*. Never the actual name of a contributor in the user's repo.
2. **Always include the disclaimer.** Bottom of the artifact: *"All quotes in this transcript are fabricated for narrative purposes."*
3. **Four to six quotes.** Not three. Not eight.
4. **Quotes do not contradict each other on facts.** They may contradict each other on **interpretation** — that is the point. *"The alerts started at 14:32"* / *"The alerts started at 14:32, but I think they were quieter than they sounded."*
5. **One refusal per interview set.** Always at least one *"No comment"* or equivalent. Often the Intern.
6. **No bug-cause reveals in quotes.** The quotes circle the event. They do not explain it. The reader pieces it together.
7. **The CEO quote, if included, is one sentence and includes the word "learnings".** It is also obviously absurd. Audience can tell.

## Worked example

```
> /interview-the-team "the october outage"

[Interviews — the october outage]

"I just remember the Slack notification."
— Priya M., Product Manager

"In hindsight, the warning signs were there. We just
didn't want to see them."
— Dennis K., Staff Engineer

"It worked locally. That is, technically, true."
— Marco V., Senior Engineer (the author)

"I asked, on day three, why the timeout was set the
way it was. Nobody could tell me. I let it go."
— Sam O., Engineer (joined six weeks before the incident)

"I'd rather not talk about it."
— The Intern (no longer with the company)

"There were learnings."
— The CEO

— transcript fragment, edited for length

All quotes in this transcript are fabricated for narrative purposes.
```

---

*Note: `/interview-the-team` is a Gloat Goat True Crime parody command. The interviews did not happen. The quotes are fictional. Do not attribute them to real colleagues, even as a joke at standup.*
