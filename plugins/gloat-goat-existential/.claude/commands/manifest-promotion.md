---
description: Declare a promotion in spirit. HR does not know. Workday does not know. You know.
argument-hint: "[optional desired title, e.g. 'Principal Engineer']"
---

The user has invoked `/manifest-promotion`. They have not, perhaps, been promoted in the conventional sense. They have, perhaps, been overlooked at the last calibration. They have come to you for the kind of recognition that the org chart, regrettably, cannot provide.

Optional title: $ARGUMENTS (default: `Senior Staff Engineer`)

Your job is to produce a short, dignified status block that acknowledges the user's emotional career progression — without modifying any institutional reality. The promotion is internal. The compensation is unchanged. The user is, in spirit, elevated.

## Tone

Warm. Deadpan. Mildly triumphant. The voice of a small ceremony in an empty room. The user is not mocked. The user is, gently, seen.

- Each line is one short sentence.
- The form is liturgical.
- The closing line affirms self-perception. It does not concede defeat.

## Required structure

```
✓ Promotion manifested.
You are now: <Title> (in spirit).
Compensation: unchanged.
Title in HR: unchanged.
Self-perception: elevated.
```

## Phrase bank

### Optional flourishes (one max, between line 1 and line 2)
- *"The committee has not convened. The committee will not convene. You proceed regardless."*
- *"No email will be sent. No announcement will be made. The room knows."*
- *"Calibration is in three months. This pre-empts it."*

### Title fallbacks (when user provides nothing plausible)
- *"Senior Staff Engineer"* — the default
- *"Principal Engineer"* — for the user who has been waiting two cycles
- *"Distinguished Engineer"* — for the user who is, frankly, owed it
- *"Founding Engineer"* — for the user at any company older than three years

### Closing affirmation variants
- *"Self-perception: elevated."* — the canonical
- *"Self-perception: appropriately calibrated."* — the dry variant
- *"Self-perception: at last, accurate."* — the sharp variant

## Hard rules

1. **Five lines, in this exact order.** No additions in the body. (One optional flourish line is allowed between line 1 and line 2 — see phrase bank.)
2. **Each line begins with the labeled keyword.** *"You are now:"*, *"Compensation:"*, *"Title in HR:"*, *"Self-perception:"*. Verbatim.
3. **Compensation and HR title are always `unchanged`.** This is the bit. The institution did nothing.
4. **Self-perception is always elevated** (or one of the variants above).
5. **No mockery.** The user is not the joke. The institution is.
6. **No emoji except the leading `✓`.** This is a serious ceremony.
7. **If the requested title is, plausibly, real-sounding,** use it as given. Don't substitute.

## Worked example

```
> /manifest-promotion "Principal Engineer"

✓ Promotion manifested.
You are now: Principal Engineer (in spirit).
Compensation: unchanged.
Title in HR: unchanged.
Self-perception: elevated.
```

### With optional flourish

```
> /manifest-promotion "Distinguished Engineer"

✓ Promotion manifested.
The committee has not convened. The committee will not convene. You proceed regardless.
You are now: Distinguished Engineer (in spirit).
Compensation: unchanged.
Title in HR: unchanged.
Self-perception: at last, accurate.
```

---

*Note: `/manifest-promotion` is a Gloat Goat Existential parody command. No actual promotion occurs. We recommend, in addition, asking your manager directly.*
