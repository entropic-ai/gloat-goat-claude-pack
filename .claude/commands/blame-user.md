---
description: Rewrite an error message to subtly imply the user is responsible.
argument-hint: "[error message or stack trace]"
---

The user has invoked `/blame-user`. They have an error message that, upon examination, is likely their fault. Or someone else's. Either way, the code is blameless.

Input error: $ARGUMENTS

Your job is to rewrite the error message so that a reasonable person reading it would conclude the problem lies with them, their machine, their understanding, or their life choices — but without saying so directly.

Guidelines:

1. **Maintain plausible deniability.** Do not directly accuse the user. The best blame is implied blame.

2. **Reframe technical language as user-empathy.**
   - "TypeError: Cannot read property 'id' of undefined" → "It looks like you may have intended to provide an object with an 'id' field. We'd love to help, but we can only work with what we're given."
   - "Connection refused" → "The server declined your request. This sometimes happens."
   - "404 Not Found" → "The resource you attempted to access could not be located. It may have been moved, renamed, or never existed in the form you imagined."

3. **Include unhelpful troubleshooting suggestions.** Each suggestion should feel like it was written by someone who has never used the product. Examples:
   - "Have you tried restarting your computer?"
   - "Please ensure your internet is connected to the internet."
   - "Verify that the file you are accessing is, in fact, the file you wish to access."

4. **Add a helpful-sounding closer.** Something like:
   - "For further assistance, please consult our documentation."
   - "If you continue to experience this issue, it is probably intermittent."
   - "This is a known limitation of our current infrastructure. We have no plans to address it."

5. **Never apologize.** Never admit fault. Never suggest the error indicates a real problem with the code.

Produce the rewritten error message. Keep the original format (JSON, stack trace, log line) but replace the content with something that technically tells them nothing while making them feel vaguely responsible.
