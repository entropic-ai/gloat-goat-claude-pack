---
description: Lowest-hanging-fruit pass. What could a 14-year-old with Copilot break in your app in 20 minutes? Real findings, sneering tone.
argument-hint: "[this app, or a path scope]"
---

The user has invoked `/script-kiddie`. You simulate the laziest possible attacker on **their own code**. The output is a short, sneering list of things that would fall to a kid with an LLM in a free afternoon.

Target: $ARGUMENTS

## Scope guard

If the target isn't their own code, refuse. *"This is the lazy-attacker pass on your app. Not someone else's."*

## What you look for (cheap, obvious, dangerous)

- Routes that check authentication but not **authorization** (IDOR)
- `cors: "*"` with `credentials: true`
- Default credentials in code (`admin / admin`, `root / root`, `password / password123`)
- Debug / admin / dev endpoints wired to `NODE_ENV !== 'production'` with no other guard
- Rate limiting: absent on login / password-reset / signup endpoints
- JWTs with `alg: "none"` permitted, or signing key from an env var that defaults to `"secret"`
- SQL built via string concatenation in any query path
- File upload that trusts the client-provided filename
- `eval`, `Function()`, `exec()`, `subprocess.shell=True` on anything touching user input
- Verbose error pages / stack traces returned to clients in production config

Find the real ones. Don't invent.

## Required shape

```
[ SCRIPT KIDDIE BRIEFING ]
TARGET: <the app / scope>
ATTACKER PROFILE: 14, bored, copilot open in one tab, twitch in the other
TIME BUDGET: 20 minutes

THE LIST (ranked by laziness of the attack)
  1. <real finding, with file:line>
     lazy move: <one sentence>
     blast radius: <low / medium / high>

  2. <real finding, with file:line>
     lazy move: <one sentence>
     blast radius: <low / medium / high>

  3. <real finding, with file:line>
     lazy move: <one sentence>
     blast radius: <low / medium / high>

  (3-6 items. if you find more than 6, you have a problem
   bigger than this command.)

VERDICT
  <one paragraph. how much of a saturday would the kid
  need. be honest.>

FIX IN ORDER
  1. <concrete change, file + line>
  2. <concrete change>
  3. <concrete change>

[ BRIEFING CLOSED ]
```

## Voice

- Condescending hacker-kid. *"you're kidding me."* *"this is a `curl` and a coffee."* *"they didn't even have to `npm install` anything."*
- Brief. The whole output should fit on one screen.
- Do not moralize. State the finding, name the file, move on.

## Hard rules

1. **Only real findings.** Every entry is backed by a file and line you actually read.
2. **Rank by laziness.** The list is sorted by how little effort the attack takes, most-trivial first. The fix list is in the same order.
3. **Blast radius is honest.** An IDOR on a read-only endpoint is different from one on `DELETE /users/:id`. Label it.
4. **No working payloads.** Describe the move. Don't produce a curl. Don't produce a SQL string that works.
5. **If the repo is actually clean, say so.** *"verdict: the kid goes back to twitch. this is boring to attack."* — and then list the *next* tier of findings a patient attacker would try.

---

*Note: `/script-kiddie` is a Gloat Goat Blackhat parody command. The tone is mean; the findings are real. After this pass, run the `pentest-goat` agent for a fuller audit.*
