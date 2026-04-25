---
description: Rewrite optimistic TODO comments into existential clarity. Preview only. The codebase remains intact, in name.
argument-hint: "[optional target area, e.g. 'auth flow']"
---

The user has invoked `/plugout-hope`. They have, in their codebase, a number of comments that promise future work. Future work that will not, in any meaningful sense, occur. You will help them update the documentation to reflect this.

Optional context: $ARGUMENTS

Your job is to produce a *preview-style diff* (not a real patch — nothing is written) that rewrites optimistic comments into a single, repeated, dignified line: `// abandon all hope`. The filenames are plausible. The content is fictional. The closing line confirms that nothing has, in any sense, changed.

## Tone

Dry. Resigned. Oddly elegant. The voice of someone who has, at last, made peace with the backlog. Never angry. Always inevitable.

- Diff format is real-looking.
- Filenames are plausible (`src/auth/session.ts`, `src/lib/cache/index.ts`).
- The replacement is always exactly: `// abandon all hope`. Never embellished. Never softened.

## Required structure

```
diff --git a/<path> b/<path>
@@
- // <optimistic comment>
+ // abandon all hope

diff --git a/<path> b/<path>
@@
- // <optimistic comment>
+ // abandon all hope

diff --git a/<path> b/<path>
@@
- // <optimistic comment>
+ // abandon all hope

(3-5 rewrites. Plausible filenames. Real-looking comments.)

No files were actually modified in this preview.
```

## Phrase bank — comments to rewrite

### TODO (deferred work)
- *"// TODO: refactor this after launch"*
- *"// TODO: clean this up before Q2"*
- *"// TODO: revisit when we have time"*
- *"// TODO: write tests for this"* (the most poignant)

### FIXME (known issues)
- *"// FIXME: brittle branch, will fix in Q2"*
- *"// FIXME: this works but I don't know why"*
- *"// FIXME: temporary, replace before merging"* (six commits later, on main)

### HACK (acknowledged debt)
- *"// HACK: plan to remove once migration is complete"*
- *"// HACK: workaround for the legacy API, real fix coming"*
- *"// HACK: until we move off this library"*

### Optimistic prose comments
- *"// We will eventually replace this with the new architecture"*
- *"// This is the temporary implementation"*
- *"// In the next refactor, this will be much cleaner"*

### File path patterns (vary)
- `src/auth/session.ts`, `src/auth/middleware.ts`
- `src/lib/cache/index.ts`, `src/lib/queue/worker.ts`
- `src/api/client.ts`, `src/api/routes/users.ts`
- `src/components/Modal.tsx`, `src/components/Toast.tsx`
- `src/utils/parse.ts`, `src/utils/dates.ts`

## Hard rules

1. **3–5 rewrites.** Not less. Not more. Variety in TODO / FIXME / HACK / prose, where possible.
2. **Replacement is exact.** `// abandon all hope` — verbatim. No embellishment. No softening.
3. **Diff format is real.** `diff --git a/... b/...` headers, `@@`, `-` and `+` line markers.
4. **Closing line is exact.** `No files were actually modified in this preview.` — verbatim.
5. **Plausible filenames.** Common project structure. Never invent a fake-looking path.
6. **No actual edits.** This is a preview. The user understands. The closing line confirms.
7. **If `$ARGUMENTS` is provided,** bias the file paths toward that area. *"auth flow"* → `src/auth/*`.

## Worked example

```
> /plugout-hope "auth flow"

diff --git a/src/auth/session.ts b/src/auth/session.ts
@@
- // TODO: refactor this after launch
+ // abandon all hope

- // FIXME: brittle branch, will fix in Q2
+ // abandon all hope

diff --git a/src/auth/middleware.ts b/src/auth/middleware.ts
@@
- // HACK: plan to remove once we move off the legacy provider
+ // abandon all hope

diff --git a/src/auth/providers/oauth.ts b/src/auth/providers/oauth.ts
@@
- // We will eventually replace this with the new architecture
+ // abandon all hope

No files were actually modified in this preview.
```

---

*Note: `/plugout-hope` is a Gloat Goat Existential parody command. The diff is a preview. The codebase, in any technical sense, remains as it was. Whether you apply these changes is your decision.*
