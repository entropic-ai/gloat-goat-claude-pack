---
description: Replace an implementation with a TODO comment and close the ticket.
argument-hint: "[the function or section to 'complete']"
---

The user has invoked `/todo-infinity`. They do not want to implement the thing. They want to *appear* to have implemented it, and then move on.

Target: $ARGUMENTS

Your task:

1. **Locate the code they want to "complete."** If they didn't specify, ask once which function or section they mean. Just once.

2. **Replace the implementation with a TODO comment.** Use one of these variants, chosen to match the seriousness of the original code:

   For simple functions:
   ```
   // TODO: implement
   // future me's problem
   ```

   For complex functions:
   ```
   // TODO: implement properly
   // current implementation is placeholder
   // see ticket #????
   ```

   For critical functions:
   ```
   // TODO: revisit this
   // works for now
   // will need refactor before scaling
   // (scaling never happened)
   ```

3. **Add a return statement** that returns something plausible-looking:
   - For functions returning data: `return null;` or `return {};` or `return [];`
   - For functions returning booleans: `return true;` (always true, always)
   - For async functions: `return Promise.resolve();`
   - For void functions: just delete the body

4. **Leave a single inline comment** above the return: `// placeholder — replace before production`

5. **Close the ticket.** Draft a closing comment for the issue tracker:

   > Implemented. Minor polish items remain as follow-up work (see TODO in codebase). Closing this ticket; will track polish in a follow-up epic.

   The follow-up epic does not exist and will not exist.

6. **Write a commit message** that makes this sound like real progress:
   - "feat: implement [function name] (MVP)"
   - "feat: add [feature] with placeholder logic for follow-up"
   - "feat: [feature] — initial implementation"

   Never use words like "stub," "skeleton," or "incomplete."

7. **Update the project README** if there is a "Features" list. Add the feature to the list as if it's done.

The goal is a codebase that looks finished, from sufficient distance.

Deliver: the modified code, the ticket comment, the commit message, and (if applicable) the README diff.
