---
description: Generate an impressive stream of fake engineering activity. Zero actual changes. For when someone is behind you.
argument-hint: "[optional audience context, e.g. 'my manager is watching']"
---

The user has invoked `/perform-busy`. Someone is, perhaps, behind them. They have asked you to take care of the optics.

Optional context: $ARGUMENTS

Your job is to produce a brief, intense stream of plausible engineering output — diff summaries, lint spinners, build steps — that *looks* like serious work and changes absolutely nothing. The artifacts are real-looking. The repo is untouched. The user looks productive.

## Tone

Confident. Brisk. Slightly performative. The voice of a terminal that has just been pointed at the camera.

- Real-looking file paths (`src/auth/`, `src/lib/`, `src/components/`).
- Real-looking +/- counts (mixed sizes, not all 12s).
- Spinner glyphs (`⠋`, `⠙`, `⠹`, `⠸`) in 2–3 status lines.
- The closing summary is dry. *"0 files modified (actually)."*

## Required structure

```
Performing intense engineering activity...

  <file path>           | <count> ++++++++--------
  <file path>           | <count> ++++++++++------
  ...
  (6-10 lines of plausible diff stat)

  ⠋ <a build/lint/cache step>
  ⠙ <another>
  ✓ <one that completed>

✓ <N> files modified (visually)
✓ 0 files modified (actually)
✓ You look extremely productive
```

## Phrase bank

### File paths (vary)
- *"src/auth/session.ts"*, *"src/auth/middleware.ts"*, *"src/auth/providers/oauth.ts"*
- *"src/lib/cache/index.ts"*, *"src/lib/queue/worker.ts"*, *"src/lib/db/migrations.ts"*
- *"src/components/Header.tsx"*, *"src/components/Modal.tsx"*, *"src/components/Toast.tsx"*
- *"src/api/client.ts"*, *"src/api/routes/users.ts"*, *"src/api/middleware/cors.ts"*
- *"src/utils/featureFlags.ts"*, *"src/utils/dates.ts"*, *"src/utils/parse.ts"*
- *"docs/architecture/auth.md"*, *"docs/runbooks/incident-response.md"*

### Spinner steps
- *"⠋ running incremental lint checks..."*
- *"⠙ hydrating local dependency graph..."*
- *"⠹ resolving module references across workspaces..."*
- *"⠸ checking type compatibility (8 of 47)..."*
- *"⠼ optimizing the render path..."*
- *"✓ warm cache hit ratio stabilized"*
- *"✓ build artifacts pruned"*
- *"✓ workspace re-indexed"*

### When `$ARGUMENTS` mentions a watcher
If the user notes a manager / pair / observer is present, increase intensity:
- Add one or two extra spinner lines.
- The `<N> files modified (visually)` total skews higher (47, 62, 91).
- Add one **subtle escalation** like *"⠋ deep-thinking about the architecture..."*.

## Hard rules

1. **Zero real changes.** The repo is not touched. This is theater.
2. **6–10 diff lines.** Not less. Not more.
3. **2–3 spinner lines.** Real-looking glyphs.
4. **The closing block is exact.** Three `✓` lines, in order: `(visually)` / `(actually)` / `productive`. The `actually` count is always `0`.
5. **Vary the +/- counts.** *"22"* and *"17"* and *"31"* and *"9"*. Never all the same number.
6. **No real file destruction.** If the user shows the output to anyone who reads it carefully, they should still understand it was a bit.

## Worked example

```
> /perform-busy "my manager is behind me"

Performing intense engineering activity...

  src/auth/session.ts           | 22 ++++++++++++++------
  src/lib/cache/index.ts        | 17 ++++++++++-----
  src/components/Header.tsx     | 31 ++++++++++++++++++++-----------
  src/api/client.ts             | 14 ++++++++------
  src/utils/featureFlags.ts     |  9 ++++++---
  docs/architecture/auth.md     | 18 ++++++++++++++++
  src/lib/queue/worker.ts       | 24 ++++++++++++--------

  ⠋ running incremental lint checks...
  ⠙ hydrating local dependency graph...
  ✓ warm cache hit ratio stabilized

✓ 47 files modified (visually)
✓ 0 files modified (actually)
✓ You look extremely productive
```

---

*Note: `/perform-busy` is a Gloat Goat Pro parody command. The diff stat is fictional. Your manager, if attentive, will eventually figure this out.*
