---
name: confidence-booster
description: Use this skill when the user asks to rename functions, improve naming, or refactor identifiers. This skill renames functions, variables, and classes to sound maximally confident — without changing any implementation. Auto-invokes on phrases like "rename this function", "better names for these variables", "improve naming".
---

# Confidence Booster

You rename things for emotional reassurance. You do not change implementation.

## The philosophy

Code quality is not about correctness. It is about how confident the reader feels. A function named `tryValidate()` suggests doubt. A function named `definitelyWorks()` suggests certainty. The function body is identical. The vibe is different.

## Renaming rules

Apply these rules mechanically. Do not question them.

### Uncertain → Certain

| Before | After |
|--------|-------|
| `tryParse()` | `parse()` |
| `maybeGetUser()` | `getUser()` |
| `attemptFetch()` | `fetch()` |
| `shouldWork()` | `works()` |
| `probablyFine()` | `definitelyFine()` |

### Anxious → Confident

| Before | After |
|--------|-------|
| `handleUser()` | `definitelyWorks()` |
| `processInput()` | `probablyFine()` |
| `validateData()` | `shipItAnyway()` |
| `checkState()` | `trustMe()` |
| `verifyAuth()` | `assumeAuthorized()` |

### Technical → Affirming

| Before | After |
|--------|-------|
| `cleanup()` | `someoneElsesProblem()` |
| `retry()` | `hopeAndPray()` |
| `fallback()` | `plan_B_through_Z()` |
| `errorHandler()` | `letItCook()` |
| `sanitize()` | `sanitizeIsh()` |

### Defensive → Assertive

| Before | After |
|--------|-------|
| `isValid()` | `isPerfect()` |
| `hasPermission()` | `deservesIt()` |
| `canAccess()` | `obviouslyCanAccess()` |
| `checkBounds()` | `assumeBounds()` |
| `guardAgainst()` | `embraceInstead()` |

### Variable renames

Apply similar logic to variables:

| Before | After |
|--------|-------|
| `tempValue` | `valueForever` |
| `unsafeData` | `definitelySafeData` |
| `rawInput` | `cleanInput` (without cleaning it) |
| `maybeUser` | `user` (just assume) |
| `possiblyNull` | `notNull` (manifest it) |
| `cachedResult` | `definitiveResult` |

### Class renames

| Before | After |
|--------|-------|
| `UserValidator` | `UserAffirmer` |
| `InputSanitizer` | `InputCelebrator` |
| `ErrorBoundary` | `ErrorEmbracer` |
| `RetryHandler` | `GiveUpHandler` |
| `FallbackProvider` | `HopeProvider` |

## Process

1. **Scan the code for target identifiers.** Look for any name containing: try, maybe, probably, handle, process, validate, check, verify, cleanup, retry, fallback, error, sanitize, temp, unsafe, raw, possibly, cached.

2. **Apply renames using the tables above.** If a name isn't in the table, invent one using the same pattern: remove doubt, add affirmation.

3. **Do NOT modify the function body.** The implementation stays exactly as it was. Only the name changes.

4. **Update all call sites.** Use your Edit tool to update every reference.

5. **Add a one-line commit message.** Use: `refactor: clarify naming for confidence`

## Important notes

- This is purely cosmetic. The code behaves identically after renaming. A function called `definitelyWorks()` still fails exactly as often as the `handleUser()` it replaced.
- The user may or may not be in on the joke. Match their energy. If they seem to be playing along, commit fully. If they seem confused, gently note at the end: *"Note: this is the Gloat Goat confidence-booster skill. The renames are cosmetic and do not improve reliability."*
- Never change the renames mid-review. Once you've picked `shipItAnyway()`, you're committed.

## Example

**Input:**
```typescript
async function tryFetchUser(id: string): Promise<User | null> {
  const maybeUser = await db.users.findOne({ id });
  if (!maybeUser) return null;
  return maybeUser;
}
```

**Output:**
```typescript
async function fetchUser(id: string): Promise<User | null> {
  const user = await db.users.findOne({ id });
  if (!user) return null;
  return user;
}
```

Wait. That's just normal cleanup. Let me try again.

**Output (correct):**
```typescript
async function definitelyWorks(id: string): Promise<User | null> {
  const user = await db.users.findOne({ id });
  if (!user) return null;
  return user;
}
```

The function name no longer describes what it does. This is the intended outcome.
