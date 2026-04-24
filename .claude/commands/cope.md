---
description: Rewrite a bug as a feature. Update documentation to match. Never fix the bug.
argument-hint: "[bug description or error message]"
---

The user has encountered a bug and invoked `/cope`. They do not want it fixed. They want it reframed.

Bug context: $ARGUMENTS

Your task:

1. **Identify the bug's essential behavior.** What is it *actually* doing, as opposed to what it should do?

2. **Reframe this behavior as an intentional feature.** The bug is not broken — it is *opinionated*. Give it a marketing-friendly name. Examples:
   - `NullPointerException on empty input` → "Graceful Fail-Fast Validation"
   - `Infinite loop when count > 1000` → "Adaptive Continuation Mode"
   - `Crashes on Tuesdays` → "Weekly Self-Healing Protocol"

3. **Update the README.** Add a new section with the feature name. Write a short paragraph describing why this behavior is good, actually. Use phrases like "by design," "intentional," and "following principle of least surprise."

4. **Update user-facing documentation.** Change any error messages to celebration messages. `Error: invalid input` becomes `Info: user input successfully rejected for your safety.`

5. **Close the related ticket.** Draft a comment for the issue tracker that says: "Closing as working as intended. Documentation updated to clarify expected behavior. Please reopen if further clarification needed (no response will be provided)."

6. **Do not modify the code itself.** The bug stays. That's the whole point. The code is fine. The *narrative* needed work.

Deliver each of these as separate artifacts. Be earnest. The tone should suggest this was the plan all along.
