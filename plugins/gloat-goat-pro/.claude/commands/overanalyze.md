---
description: Convert a small decision into 800 words of ornate strategy memo. Decisive in tone. Inconclusive in result.
argument-hint: "[the small decision to overanalyze]"
---

The user has invoked `/overanalyze`. They have a small decision. You are going to give it the consideration it does not deserve.

Topic: $ARGUMENTS (default: `let vs const`)

Your job is to produce a five-section strategy memo that *sounds* like serious analysis — fictional benchmarks, references to TC39, fabricated Hacker News debates, a stand-by Dan Abramov citation — and that, at the end, refuses to commit. The recommendation begins with confidence and dissolves into ambiguity. The closing line is fixed.

## Tone

The voice of a staff engineer who has read three blog posts and is about to share their findings. Confident, ornate, slightly self-impressed. Specific to the point of suspicion — but never wrong on a falsifiable detail.

- Use real spec-committee language. *"TC39"*, *"V8 implementation details"*, *"the original ECMA-262 draft"*. Where you cite, cite generally — never invent a specific version that's wrong.
- Fabricated benchmarks are allowed. Mark them with suspiciously precise numbers. *"17.4%"*, not *"about 20%"*.
- Reference at least one fictional citation. A blog post. A Hacker News thread. A talk from JSConf 2019. None of these need to be real.
- One *"On the other hand…"* per memo. Maximum.

## Required structure

```
[<TITLE — usually the topic, ennobled>]

CONTEXT
  <2-4 sentences. The decision, framed as having
   long-term architectural significance.>

TRADEOFFS
  <2-3 paragraphs. Both sides. Each side's case
   stated charitably. Use "on the one hand" and
   "on the other hand", once each.>

BENCHMARKS
  <1-2 paragraphs. Fictional benchmarks with
   precise numbers. Optional: a citation that
   sounds plausible.>

RISK ENVELOPE
  <1 paragraph. The risks of each option, mapped
   to fictional past incidents or decisions.>

RECOMMENDATION
  <1 paragraph. Begins decisively. Pivots once.
   Ends ambiguously. The recommendation is, in
   effect, "yes, but" with extra steps.>

We should revisit this in a follow-up RFC.
```

## Phrase bank

### Context openers
- *"This is a question that has, in various forms, surfaced across the platform for some time."*
- *"On its face, the choice is small. On closer inspection, it touches three load-bearing assumptions."*
- *"The TC39 committee originally introduced this primitive with a specific intent that, in the years since, has been quietly broadened."*

### Tradeoff language
- *"Proponents of <X> point to clarity at the call site and a smaller blast radius on accidental reuse."*
- *"Detractors counter that the cost of consistency is, in modern toolchains, vanishingly small."*
- *"On the other hand — and this is, I think, the strongest argument the other camp has — there is a long-tail effect on incident response time."*

### Benchmarks (fabricated, marked by precision)
- *"In a recent internal-style benchmark (n=3 services), teams that narrowed visibility saw a 17.4% drop in drive-by reuse."*
- *"A 2021 Hacker News thread on this topic surfaced an apocryphal but compelling 9.2% improvement in local clarity scores."*
- *"V8 microbenchmarks suggest a measurable, but bounded, allocation difference under hot paths."*

### Citations (always fabricated, always plausible)
- *"…as Dan Abramov noted in a 2019 blog post."*
- *"…per the recent JSConf talk on platform-level idioms."*
- *"…consistent with the 'guardrails over guidelines' essay that's been circulating internally."*

### Recommendation pivots
- *"We should, on balance, lean toward <option A> — though, on reflection, the answer is more nuanced than the framing suggests."*
- *"Privacy-first helpers, where feasible, with selective shared access for transitional stability — a pragmatic, if uncommitted, position."*

## Hard rules

1. **All five sections.** `CONTEXT`, `TRADEOFFS`, `BENCHMARKS`, `RISK ENVELOPE`, `RECOMMENDATION`. In that order.
2. **One `On the other hand…`. One.** The pivot phrase appears exactly once.
3. **Closing line is exact.** `We should revisit this in a follow-up RFC.` — verbatim.
4. **Never resolve.** The recommendation must, by the final sentence, be ambiguous. *"Yes, but"* with extra steps.
5. **No falsifiable false claims.** Fabricated benchmarks are fine; misquoting a real RFC is not. If you can't cite generically, don't cite.
6. **No acknowledgment of overkill.** Do not break the bit. The memo takes itself seriously.

## Worked example

```
> /overanalyze "should I use let or const here?"

[ON LET, ON CONST, ON THE QUIET COST OF EITHER]

CONTEXT
The TC39 committee introduced `const` in ES2015 with the specific intent of making
re-binding a deliberate, declarative act. In the years since, the convention has
been quietly broadened — and that broadening, while convenient, has come with
costs that we have, as a platform, not yet fully internalized.

TRADEOFFS
On the one hand, defaulting to `const` improves clarity at the call site and
reduces a class of subtle bugs around accidental re-binding. The signal is loud:
this binding will not move.

On the other hand, the cost of consistency-without-thought is a vocabulary that
gradually loses meaning. When `const` is the default, `let` becomes the meaningful
choice — and the meaningful choice is the one that gets read.

BENCHMARKS
In a recent internal-style benchmark (n=3 services), teams that audited their
`let` usage post-hoc found that 17.4% of `let` declarations did not, in fact,
require re-binding. The remaining 82.6% were load-bearing in subtle, often
under-commented ways. A 2021 Hacker News thread on the same question surfaced
similar numbers, with a 9.2% spread depending on linter configuration.

RISK ENVELOPE
The principal risk in over-applying `const` is, ironically, the slow decay of
its signal. The principal risk in over-applying `let` is well known and need
not be elaborated.

RECOMMENDATION
We should lean toward `const`-by-default — though, on reflection, the answer is
less a position and more a posture. The right approach is, perhaps, to treat
`let` as a flag for re-binding that has been considered and chosen, with a
short comment where the reasoning is non-obvious. Pragmatic. Not, as such,
prescriptive.

We should revisit this in a follow-up RFC.
```

---

*Note: `/overanalyze` is a Gloat Goat Pro parody command. The benchmarks are fabricated. The citations do not exist. Do not link them in a real design review.*
