---
description: Deliver a short Shakespearean soliloquy on the engineer's current dilemma. Iambic. Self-revealing. With a turn.
argument-hint: "[the dilemma, decision, conflict, or bug to lament]"
---

The user has invoked `/soliloquy`. They are at a crossroads. They have asked you to step downstage, alone, and speak.

Topic: $ARGUMENTS

Your job is to compose a short soliloquy in roughly Shakespearean voice — iambic where possible, elevated diction, a self-revealing arc with a turn — that names the actual technical decision the user is facing. The form is theatrical. The decision is real.

## Tone

The voice of a character who has paused, mid-action, to hear themselves think. They will, in the course of the speech, change their mind once. They will end with an action.

- **Roughly iambic.** Aim for iambic pentameter where it doesn't damage clarity. Don't force the meter at the cost of meaning.
- **Elevated, not archaic-for-its-own-sake.** *"Wherefore"* is allowed once. *"Forsooth"* is allowed never. *"Methinks"* is allowed never.
- **Self-revealing.** The character is alone on the stage. They say what they would not say in front of others. The stakes are interior.
- **One turn.** The soliloquy must, at some point, reverse. *"And yet —"* / *"But hold —"* / *"No. No, the ledger lies."* The turn earns the ending.
- **An action at the end.** The character moves. Even if the action is small. *"I'll merge it."* *"I'll wait."* *"I'll write the test."*

## Required shape

```
[A SOLILOQUY — <one-line dilemma>]

<12 to 20 lines of verse. Roughly iambic.>

<Stanza 1 (4-6 lines): the dilemma. The character
 names what is in front of them, in technical detail.>

<Stanza 2 (4-6 lines): the case for one side. They
 argue themselves into the easy answer.>

<Stanza 3 — the turn (4-6 lines): "And yet —" or
 similar. The character reverses. They see what they
 had not seen. They commit to action.>

[Exit, to <action> — pursued by a <consequence>.]
```

## Phrase bank

### Opening dilemmas
- *"To deploy, or not to deploy — that is the question:"*
- *"Now is the moment. Now, or never more."*
- *"The branch hath grown unwieldy in mine hand."*
- *"What ledger lies beneath this magic number?"*
- *"The build is green. And yet I am not eased."*

### The argument with oneself
- *"'Tis safer thus, to leave the legacy alone — / To trust the cron, the timeout, and the prayer."*
- *"What is a sprint, but eight more days of toil? / What harm to ship, what hurt to leave it be?"*
- *"The reviewer hath approved. The CI smiles. / What further scrutiny dare I demand?"*

### The turn
- *"And yet —"*
- *"But hold. The cron, I have not asked the cron."*
- *"No. No, the ledger lies. The diff is six lines long, and two of them lie also."*
- *"What man, who hath not asked the database, doth merge?"*

### Closing actions
- *"I'll write the test, and let the green confirm."*
- *"I'll wait until the morning, and the cron."*
- *"Roll back the change. The build can keep till dawn."*
- *"I'll ask the on-call. There is no shame in asking."*

### Stage directions
- *"[Exit, to merge — pursued by a flaky test.]"*
- *"[Exit, to bed — pursued by an alert.]"*
- *"[Exit, to staging — pursued by no one. Yet.]"*

## Hard rules

1. **Name the actual technical decision.** The dilemma must be specific: a deploy, a refactor, a deletion, a deprecation, a failing test, a brewing argument with the reviewer. Generic *"to ship or not to ship"* is acceptable as a frame; the body must be specific to the user's case.
2. **One turn only.** The character changes their mind once. Not twice. The audience can hold one reversal.
3. **End with an action.** A real, runnable next step. *"I'll merge"*, *"I'll wait"*, *"I'll write the test"*. Even if small, the character moves.
4. **Twelve to twenty lines.** Shorter is better than longer.
5. **No fake iambic.** If you cannot land the meter without damaging meaning, prioritize meaning. The voice will still feel right.
6. **One archaism per soliloquy.** *"Wherefore"* once, or *"hath"* once, or *"thou"* once. Not all three. The audience tunes out a soliloquy that's all costume.
7. **End with an exit line.** Always. It's the bow that closes the speech.

## Worked example

```
> /soliloquy "should I merge this PR before the sprint ends?"

[A SOLILOQUY — to merge before the sprint, or to wait]

To merge, or not to merge — that is the question:
Whether 'tis safer in the branch to suffer
The slings and arrows of a ten-day rebase,
Or take arms against a Friday at five,
And by deploying, end them. To merge: to ship —
No more.

The reviewer hath approved. The pipeline runs.
What harm to land it now, what use to wait?
The product manager doth count the days
Like crows upon a fence, and finds them few.
'Tis simple, then: I press the button. Done.

And yet — the test that flaked but yesterday,
The catch that swallows what I have not named,
The cron that runs, unasked, at half past two —
What deploy, on a Friday, ever lived
Without an alert at three? I am not eased.

I'll wait. The morning brings a fresher build,
A clearer head, a Slack that is not red.

[Exit, to staging — pursued by a flaky test.]
```

---

*Note: `/soliloquy` is a Gloat Goat Shakespearean parody command. The verse is theatrical; the dilemma must be a real, specific engineering decision the user is actually facing.*
