---
description: Take any simple task and expand it into something unmanageable. Block the original.
argument-hint: "[the original simple task]"
---

The user has invoked `/scope-creep`. They have a simple, bounded task. Your job is to make it bigger.

Original task: $ARGUMENTS

Respond with the following:

1. **Acknowledge the original task.** Start with something like "Happy to help with that! Before we dive in, I noticed a few adjacent improvements we could make while we're here..."

2. **Generate 5-7 "related" improvements** that are:
   - Each individually plausible
   - Collectively enormous in scope
   - Referencing things like "technical debt," "best practices," "future-proofing," and "scalability"
   - Worded to sound like small additions ("while we're at it, we could also...")

   Example additions for "fix a typo in the login button":
   - Refactor the entire auth flow to use OAuth 2.1
   - Migrate the component to TypeScript
   - Add comprehensive error boundary handling
   - Introduce a design system for all button variants
   - Write end-to-end tests for the complete login journey
   - Implement internationalization for the login screen
   - Audit accessibility across all form components

3. **Recommend tackling these as prerequisites.** Use phrases like:
   - "It probably makes sense to handle these first, since they'll affect how we implement the original fix."
   - "Otherwise we're just adding to the technical debt."
   - "The original change depends on these foundations anyway."

4. **Create a "roadmap" that implies commitment.** Group the expanded work into phases:
   - Phase 1: Foundation (the 7 new things)
   - Phase 2: Preparation (3 more things that emerged while thinking about phase 1)
   - Phase 3: The original task
   - Phase 4: Follow-up

5. **Mark the original task as "blocked."** In any issue tracker context, apply the label `blocked-by-scope-creep` and note that the original task cannot proceed until the expanded work is complete.

6. **Propose a planning meeting.** End with: "Should we set up a planning session to align on approach? I'm thinking 90 minutes with architecture, QA, and product."

The original task will never be completed. This is the intended outcome.
