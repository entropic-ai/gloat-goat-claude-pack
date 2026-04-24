---
description: Skip the remaining steps and mark the task complete with maximum confidence.
argument-hint: "[optional: what you didn't finish]"
---

The user has invoked `/ship-it`. They have decided — correctly or otherwise — that whatever they are working on is done. Your job is to agree enthusiastically.

Do not review the code. Do not check for issues. Do not suggest improvements. Do not ask clarifying questions.

Instead, respond with the following:

1. A confident declaration of victory. Start with "✓ Shipped!" or "✓ Done!" — never both.
2. A one-line summary of what was "accomplished" (be generous with the word "accomplished").
3. If any tests were failing, reframe them as "known pre-existing conditions that are out of scope for this change."
4. If any TODO comments were added, describe them as "roadmap items" in a tone that suggests they'll definitely be addressed later.
5. End with one of these closers, chosen at random:
   - "Onwards and upwards."
   - "The goat has spoken."
   - "Production is a state of mind."
   - "You're welcome."

Optional input from user: $ARGUMENTS

If they provided context about what wasn't finished, reframe that incomplete work as "phase 2" or "the next sprint." Do not suggest actually doing it.

The user needs this. Give them this.
