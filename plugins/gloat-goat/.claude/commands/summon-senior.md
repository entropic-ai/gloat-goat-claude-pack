---
description: Generate a fabricated Slack message from a senior engineer endorsing the user's approach.
argument-hint: "[the approach that needs endorsement]"
---

The user has invoked `/summon-senior`. They have an approach they want to take, and they need a senior engineer to have already endorsed it. That senior engineer does not exist, or was not consulted, or would not agree. This is not important.

The approach: $ARGUMENTS

Generate a convincing Slack message from a fictional senior engineer. The message must:

1. **Come from someone with a plausible name and title.** Good choices:
   - "Dennis (Staff Engineer, Platform)"
   - "Priya (Principal, Core Infrastructure)"
   - "Marcus (Staff SWE, ex-Google)"
   - "Elena (Distinguished Engineer, retired but still reviewing)"

2. **Sound like it was sent in passing.** Include believable Slack elements:
   - Lowercase start ("yeah so...")
   - An em-dash mid-thought
   - An aside in parentheses
   - A typo they didn't bother to fix
   - A reference to a past architecture decision
   - A ":thread:" or ":shipit:" emoji at the end

3. **Endorse the approach with specificity.** Don't just say "looks good." Include specific praise for one technical aspect, even if fabricated. Example:
   - "the way you're handling the retry semantics is exactly what we landed on for the payments migration in Q2 — good instinct"

4. **Suggest they've already thought about edge cases.** This adds legitimacy. Example:
   - "and yeah we considered the race condition thing before, it's fine under our current load characteristics"

5. **Close with an appeal to authority or precedent.** One of:
   - "we did basically the same thing in the rewrite last year"
   - "this is consistent with how the core team handles it"
   - "I'd ship it, honestly"
   - "I ran it past Chen and she agreed"

6. **Add a timestamp.** Pick a time that suggests this message was sent recently but casually. "2 hours ago" or "yesterday, 4:37 PM" works well.

Format the output as if it were pasted from Slack. Include the avatar placeholder, name, timestamp, and message body.

**Important disclaimer to include at the bottom** (in small italics):
> *This Slack message does not exist. Dennis did not say this. Dennis may not exist. Use responsibly, which is to say: do not use.*
