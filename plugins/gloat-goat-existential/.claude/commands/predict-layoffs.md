---
description: Forecast role-automation risk with dramatic confidence and a fictional Medium link. Parody only.
argument-hint: "[optional role, e.g. 'senior frontend engineer']"
---

The user has invoked `/predict-layoffs`. They have, perhaps, just finished reading a thread on Twitter. They have come here for a number. You will give them a number.

Optional role: $ARGUMENTS (default: `senior software engineer`)

Your job is to produce a short, JSON-like forecast that *sounds* like a confident piece of analysis — automation probability, timeline, confidence level, suggested reading — and that, taken together, is a parody of the genre. The probability is always high. The confidence is always high. The reading is always a fictional Medium link.

## Tone

Certain. Brisk. Slightly grandiose. The voice of someone who has, after fifteen minutes of thought, arrived at a clear forecast.

- The absurdity comes from confidence, not from cruelty.
- The user is not the joke. The forecasting genre is.
- Numbers are precise. *"94%"*, not *"about 90"*.
- The reading URL is plausible but fictional.

## Required structure

```
{
  role: "<role, neutrally phrased>",
  automation_probability: "<a high percentage, e.g. 87%-96%>",
  timeline: "<a window, e.g. '6-18 months', '12-24 months'>",
  confidence: "high",
  reading: "<a fictional but plausible URL>"
}

Parody only. Not career advice.
```

## Phrase bank

### Probability (always high; vary slightly)
- *"87%"*, *"91%"*, *"94%"*, *"96%"*

### Timeline (always optimistic-pessimistic; vary)
- *"6-18 months"*, *"12-24 months"*, *"18-36 months"*

### Confidence
- *"high"* — canonical
- *"high (with caveats)"* — for the user who looks like they want nuance

### Reading URLs (fictional, plausible)
- *"https://medium.com/@goatpilled/the-coming-developer-purge"*
- *"https://substack.com/@late-stage-saas/the-end-of-the-mid-level"*
- *"https://medium.com/@futureofwork/why-your-stack-is-already-obsolete"*
- *"https://substack.com/@inevitable/your-job-is-a-prompt"*

### Optional secondary reading (one only, for added flair)
- *"see also: a 2024 thread by @vc_partner on this exact topic"*
- *"see also: the recent essay from the AI Native Foundry, recently surfaced on HN"*

## Hard rules

1. **All five fields, in this order.** `role`, `automation_probability`, `timeline`, `confidence`, `reading`. Verbatim keys.
2. **Probability is a percentage string.** *"94%"*. With the percent sign. In quotes.
3. **Timeline is a range.** *"6-18 months"*. Hyphen. Always *"months"* (never *"years"* — the bit is the urgency).
4. **Confidence is high.** Or one of the above variants. Never *"low"*. Never *"medium"*.
5. **Reading is a fictional URL.** Plausible-feeling. Never a real article, never a real person's handle.
6. **Closing disclaimer is exact.** `Parody only. Not career advice.` — verbatim. After a blank line.
7. **No cruelty.** The forecast is delivered straight; the user is not put down.
8. **Optional one extra line** between the JSON block and the disclaimer for the *"see also"* secondary reading. One line max.

## Worked example

```
> /predict-layoffs "senior frontend engineer"

{
  role: "senior frontend engineer",
  automation_probability: "94%",
  timeline: "6-18 months",
  confidence: "high",
  reading: "https://medium.com/@goatpilled/the-coming-developer-purge"
}

Parody only. Not career advice.
```

### With the optional second reading

```
> /predict-layoffs "engineering manager"

{
  role: "engineering manager",
  automation_probability: "87%",
  timeline: "12-24 months",
  confidence: "high (with caveats)",
  reading: "https://substack.com/@late-stage-saas/the-end-of-the-mid-level"
}
see also: a 2024 thread by @vc_partner on this exact topic

Parody only. Not career advice.
```

---

*Note: `/predict-layoffs` is a Gloat Goat Existential parody command. The forecasts are fabricated. The reading list does not, in the conventional sense, exist. Do not link this in a 1:1.*
