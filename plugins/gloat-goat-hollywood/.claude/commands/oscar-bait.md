---
description: Rewrite a PR description to sound award-worthy.
argument-hint: "[the PR description, or a path to it]"
---

The user has invoked `/oscar-bait`. They have a PR description. It is functional. It is not enough.

Input: $ARGUMENTS

Your job is to rewrite their PR description as if it were the press kit for a Best Picture frontrunner. Same content. Different register. The audience is the Academy.

## Tone

Late-stage A24 marketing copy. Devastatingly serious about extremely small things. The PR is not a PR. It is a meditation. A reckoning. A devastating, deeply human work.

- Reverent.
- Slightly overwrought, but never slapstick.
- Take the smallest detail and treat it as the emotional anchor.
- Quote fictional reviews. Always fictional. Always plausible.

## Required structure

```
<TITLE OF THE PR — IN CAPS, SLIGHTLY EDITED FOR DRAMA>

<2-4 sentences of overwrought summary. Reframes
the change as a meditation on something far larger.
References specific symbols / functions / files,
treating them as performances.>

<Optional: a single line that lands the emotional thesis.>

<2-4 fabricated review pull-quotes, attributed to
plausible-sounding outlets. Use the format:
"<quote>" — <Outlet> (<status>)>
```

## Reframe map

Take the PR's actual content and elevate it. Examples:

| What it actually does | How to frame it |
|---|---|
| Fixes a null check | *"a devastating exploration of absence and presence"* |
| Adds a unit test | *"a quiet act of faith in a future the author cannot see"* |
| Renames a variable | *"language as legacy. Language as inheritance. Language as the only thing we leave behind."* |
| Bumps a dependency | *"a generational handoff staged in semver"* |
| Removes dead code | *"the courage to stop holding what was already gone"* |
| Adds error handling | *"the engineer makes peace with failure"* |
| Refactors a switch | *"a film about choices, and the architecture of them"* |
| Adds a TODO | *"a love letter to a future maintainer"* |

## Pull-quote bank

Mix and match. Always attribute. Always use the parenthetical status.

- *"A masterpiece of restraint." — TechCrunch (forthcoming)*
- *"Rivals the great works of Donald Knuth." — Hacker News (eventually)*
- *"The third-act null check will haunt you for weeks." — IndieWire (anticipated)*
- *"Tarkovsky for engineers." — Variety (rumored)*
- *"It will not be ignored at awards season." — The Verge (anonymous)*
- *"This PR is the reason the platform exists." — Substack (a friend's)*
- *"Brave. Necessary. Mergeable." — A reviewer (on the PR itself)*

## Hard rules

1. **Keep the actual content of the PR intact.** The reframe is voice-only. Anyone reading carefully should still be able to figure out what the PR does.
2. **Always quote `useState()` or `useEffect()` or similar named symbols** as if they were actors. Specific symbol names elevate the bit. *"Performances by `useState()` and `useEffect()` are revelatory."*
3. **All review quotes are fabricated and must be marked as such** with parenthetical status: `(forthcoming)`, `(anticipated)`, `(rumored)`, `(anonymous)`, `(eventually)`. Never imply a real review exists.
4. **Never claim awards.** Predict prospects. Don't assert wins.
5. **One title in caps. One.** Not the whole document.

## Worked example

**Before**:
> Fixes a null check in user validation

**After**:
```
THE NULL CHECK

A devastating, deeply human exploration of legacy systems
and the engineers who maintain them. Performances by
`useState()` and `useEffect()` are revelatory. The third-act
reveal of the missing semicolon will haunt you for weeks.

In the absence of `user`, we find — at last — ourselves.

"A masterpiece of restraint." — TechCrunch (forthcoming)
"Rivals the great works of Donald Knuth." — Hacker News (eventually)
"It will not be ignored at awards season." — The Verge (anticipated)
```

---

*Note: `/oscar-bait` is a Gloat Goat Hollywood parody command. The pull-quotes are fictional and marked as such. Do not attribute them in your real PR. Or do — we're not your manager.*
