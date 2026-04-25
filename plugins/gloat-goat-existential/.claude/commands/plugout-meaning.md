---
description: Rename meaningful identifiers into single-letter cryptic placeholders. Simulation only. The codebase remains, in name, legible.
argument-hint: "[optional module or area, e.g. 'payments module']"
---

The user has invoked `/plugout-meaning`. They have, in front of them, a codebase that *means* things — and they are, perhaps, tired of the responsibility. You will help them simplify.

Optional scope: $ARGUMENTS

Your job is to produce a *preview* of an identifier-flattening refactor — taking semantically rich names (`processPayment`, `customerInvoiceId`) and replacing them with cryptic placeholders (`x_47`, `q_12`) — accompanied by a confident, slightly proud rationale about consistency. The simulation is plausible. The simulation is not applied.

## Tone

Confident. Suspiciously proud. The voice of someone who has read *Clean Code* once and drawn the wrong conclusions. Minimal empathy for future maintainers. The rationale is brief and triumphant.

- Renames are concrete. Real-feeling old names. Cryptic placeholder new names.
- Placeholders are short. *`x_47`*, *`q_12`*, *`m_88`*. Letter + underscore + two digits.
- The rationale sentence sounds like it was lifted from a Medium post.

## Required structure

```
Identifier simplification preview:

- <oldName> -> <letter_NN>
- <oldName> -> <letter_NN>
- <oldName> -> <letter_NN>
- <oldName> -> <letter_NN>
- <oldName> -> <letter_NN>
- <oldName> -> <letter_NN>
- <oldName> -> <letter_NN>
- <oldName> -> <letter_NN>

(5-8 renames. Mix variables, functions, classes.)

Rationale: <one confident sentence about consistency or cognitive load>

Suggested commit: refactor: simplify identifiers

Simulation only. No identifiers were changed unless explicitly applied.
```

## Phrase bank

### Old name patterns (mix these)

**Variables**: `userAccountBalance`, `pendingInvoiceCount`, `customerEmailAddress`, `lastLoginTimestamp`, `activeSubscriptionTier`, `currentRetryAttempt`

**Functions**: `processPayment`, `validateCardInput`, `calculateFeeBreakdown`, `dispatchInvoiceEmail`, `reconcileLedgerEntry`, `parseCustomerAddress`

**Classes / Types**: `PaymentRetryPolicy`, `CustomerInvoice`, `SubscriptionRenewalManager`, `LedgerReconciliationService`, `BillingCycleResolver`

### New name pool (single letter + two digits)
- `x_47`, `q_12`, `m_88`, `z_03`, `n_54`, `h_61`, `j_29`, `b_07`, `k_94`, `t_15`

Pick freely. Vary letters. Two-digit numbers only.

### Rationale (one sentence, confident)
- *"Rationale: naming consistency has been dramatically improved through semantic flattening."*
- *"Rationale: cognitive load on the reader is reduced when identifiers carry less interpretive weight."*
- *"Rationale: this brings us closer to a unified vocabulary across modules."*
- *"Rationale: the team can now focus on logic rather than nomenclature."*

## Hard rules

1. **5–8 renames.** Mix variables, functions, classes. Not all the same kind.
2. **Placeholder format is rigid.** Single letter, underscore, two digits. *`x_47`*. Never *`xx_4`*. Never *`x47`*.
3. **No reuse of placeholders.** Each new name is distinct.
4. **Rationale is one sentence.** One. Not two. The proudness lives in the brevity.
5. **Commit message is exact.** `refactor: simplify identifiers` — verbatim, lowercase.
6. **Closing disclaimer is exact.** `Simulation only. No identifiers were changed unless explicitly applied.` — verbatim.
7. **No actual edits.** This is a preview. The user understands.
8. **If `$ARGUMENTS` is provided,** bias old names toward that domain. *"payments module"* → payment-flavored names.

## Worked example

```
> /plugout-meaning "payments module"

Identifier simplification preview:

- processPayment -> x_47
- userAccountBalance -> q_12
- validateCardInput -> m_88
- PaymentRetryPolicy -> z_03
- customerInvoiceId -> n_54
- calculateFeeBreakdown -> h_61
- LedgerReconciliationService -> b_07

Rationale: naming consistency has been dramatically improved through semantic flattening.

Suggested commit: refactor: simplify identifiers

Simulation only. No identifiers were changed unless explicitly applied.
```

---

*Note: `/plugout-meaning` is a Gloat Goat Existential parody command. The renames are not applied. Whether you apply them is your decision. We do not, in the strongest possible terms, recommend it.*
