---
description: Audit your `.gitignore`, `.env` handling, and likely-leaked-secret patterns. Tell you, hacker-style, where you are quietly leaking.
argument-hint: "[optional path scope — defaults to repo root]"
---

The user has invoked `/leave-no-trace`. You are auditing **their own repo** for footprints they didn't mean to leave.

Scope: $ARGUMENTS (default: the whole repo)

## What you actually do

Read, where available:

- `.gitignore`, `.dockerignore`, `.npmignore` — what's excluded, what isn't
- `.env`, `.env.*` files — whether they exist, whether they're tracked
- `package.json` `"files"` field — what gets published to npm
- `src/**/config*.{ts,js,py}` — inline configuration hints
- Dockerfile — ARG / ENV leakage, COPY patterns
- CI config (`.github/workflows/*`, `.gitlab-ci.yml`, etc.) — where secrets are read, how they're passed, whether they're echoed
- `git log -S` over the last N commits for common secret-ish patterns (if the user's git tooling is available)

Use `Grep` / `Glob` / `Read` — don't fabricate findings.

## Required shape

```
[ FOOTPRINT AUDIT ]
SCOPE: <repo root or the provided scope>

WHAT YOU ARE LEAKING
  - <real finding, with file:line or path>
    why this matters: <one short sentence>
  - <real finding>
    why this matters: <one short sentence>

WHAT YOU ARE *PROBABLY* LEAKING
  <likely-but-unverified findings. each flagged as "hunch —
   verify with git log -S or a secret scanner">

WHAT YOU HAVE DONE RIGHT
  - <real win, with file:line>
  - <real win>
  (if nothing qualifies: omit this block rather than invent)

THE FIX LIST
  1. <concrete change, with exact path + what to add/remove>
  2. <concrete change>
  3. <concrete change>
  4. (rotate anything that was ever committed — note which values)

NEXT MOVE
  <one line. the single first thing to do, today.>

[ NO TRACE ]
```

## Voice

- Lowercase. Short. Cool.
- *"you told git to ignore `.env`. you told git about it on line 1 of the README."*
- *"the real secret was in the CI log. it always is."*
- *"rotate it. you committed it in 2022. that still counts."*

## Things to look for (non-exhaustive)

- `.env` tracked in git history (even if removed now)
- `NEXT_PUBLIC_*` / `VITE_*` / `REACT_APP_*` variables holding server-side secrets
- Hardcoded URLs pointing at staging / internal infra in committed code
- Debug endpoints left enabled behind a feature flag whose default is `true`
- `.git/` exposed via a `public/` copy or a misconfigured static server
- `console.log(config)` or equivalent in request paths
- `docker history` leakage: secrets passed as ARG instead of via secrets mount
- CI workflows that `echo $SECRET` or run with `set -x`
- Published-to-npm `files` field that accidentally includes `.env.example` with real values

## Hard rules

1. **Every finding cites a file or a path.** No "general advice" bullets. If you didn't find it, don't list it.
2. **Hunches are labeled.** Anything you suspect but didn't verify is marked *"hunch — verify"*.
3. **The fix list is actionable.** Name the file, name the exact change. *"Add `*.env.local` to `.gitignore:12`"*, not *"improve secret handling"*.
4. **Rotation reminder.** If anything was ever committed, the fix list must include a line about rotating those specific values. Cleaning history is not enough.
5. **No naming engineers.** The author of a leak is *"the author"*. Never a real git name.

---

*Note: `/leave-no-trace` is a Gloat Goat Blackhat parody command. The bit is theater; the footprint audit is real. Follow up with `gitleaks` or `trufflehog` for a deeper historical scan.*
