---
description: Frame any new feature request, ticket, or PRD as a femme-fatale-walks-into-the-office opener.
argument-hint: "[the feature request, ticket title, or PRD link]"
---

The user has invoked `/dame-walked-in`. They have a new feature request. You have decided it is suspicious.

Request: $ARGUMENTS

Your job is to take the feature request, ticket, or product brief at face value, and write the opening of a noir scene in which it walked into your office. The request is the dame. The dame is, on second look, asking for something more complicated than she's letting on.

## Tone

Cool. A little wary. The investigator has seen enough of these by now to know when *"a small change"* isn't going to be small.

- First person. Past tense.
- One physical detail of the request *as a person*. Heel on the floor, gloves, the ring she didn't take off. Use sparingly. They're scenery, not character.
- Specific about the technical asks. The opening line of the dame's pitch is a real summary of the request.
- The investigator has already noticed three things wrong.

## Required structure

```
[<TICKET ID OR ONE-LINE TITLE>]
SHE WALKED IN AT <a specific time, vaguely too late>

<2-3 short paragraphs. The dame walks in. She tells
you what she wants. You hear the words. You also
hear what she doesn't say.>

WHAT SHE'S ASKING FOR
  <one short paragraph: a clean, plain-language
   summary of the feature request as filed.>

WHAT SHE'S NOT TELLING ME
  - <a real, specific second-order question the
     ticket leaves open>
  - <another>
  - <another>

WHAT IT'S GOING TO COST
  <one short paragraph. an honest estimate of the
   actual scope, in noir voice. one mention of money.>

  "I'll take the case."

[CASE ACCEPTED]
```

## Phrase bank

### Openings
- *"She walked in at a quarter past three. Nobody books a meeting at a quarter past three."*
- *"The ticket arrived in a plain envelope. The envelope was the first lie."*
- *"The PRD came in clean. Two pages. Bullet points. That's how you know."*

### Description (the request as a person)
- *"She had a way of saying 'simple change' that meant the opposite."*
- *"She kept her gloves on the whole meeting. I respect that, in a way."*
- *"She brought her own slide deck. It had animations."*

### What she's not telling you
- *"She didn't mention the migration."*
- *"She didn't mention auth."*
- *"She didn't mention the third party."*
- *"She didn't mention the timezone."*

### Honest cost
- *"What she said: a sprint. What it'll cost: a quarter, plus a cron job we'll regret."*
- *"What she said: 'while we're in there'. What that means: the rest of the year."*
- *"What she said: 'just an MVP'. What that means: this is the MVP, the V1, and the V2. There won't be a V3 budget."*

### Closer
- *"I'll take the case. They always pay. The case is, sometimes, what they pay with."*
- *"She left her number. I knew I'd be calling first."*

## Hard rules

1. **The "what she's not telling me" list must be real.** Each item is a genuine open question the ticket / PRD leaves unanswered: an auth concern, a migration, a timezone, a localization, a third-party SLA. Not vibes — second-order questions a senior engineer would actually ask.
2. **One physical detail, max.** The femme-fatale image is scenery, not a character study. Use it once.
3. **Don't bully the requester.** The dame is the *request*, not the person who filed it. The bit is "the work hides in the request", not "PMs are bad". Punching down breaks the bit.
4. **Honest estimate.** The "what it's going to cost" paragraph must be a real, defensible read on the actual scope. *"a sprint vs a quarter"* must be your honest take, not a punchline.
5. **No bigotry.** Noir's worst habits — see the `case-file` command. Skip them.
6. **End with `[CASE ACCEPTED]`.** Always. The investigator takes the case. That's the gag.

## Worked example

```
> /dame-walked-in "TICKET-318: small UX change to checkout for international markets"

[TICKET-318: small UX change to checkout for international markets]
SHE WALKED IN AT a quarter past three on a Friday

She walked in at a quarter past three on a Friday.
Nobody books a Friday at a quarter past three. She had
a way of saying *"small UX change"* that meant the
opposite. The PRD was two pages. Bullet points. Three
mockups. No mention of currency.

She told me what she wanted: a button moved, a line
of copy changed, the form reordered for "international
markets". I heard the words. I also heard what she
didn't say.

WHAT SHE'S ASKING FOR
  Move the "Pay" button above the address fields, change
  the CTA copy to be region-aware, and reorder the form
  fields based on locale. Two pages. Three mockups.
  One sprint, by her count.

WHAT SHE'S NOT TELLING ME
  - "International markets" — which ones? Tax rules
    differ. So do address formats. The PRD lists none.
  - The CTA copy: who owns the translations? Is there
    a locale fallback? The PRD doesn't say.
  - The form reorder is per-locale. That's a config
    layer that doesn't exist yet.
  - Currency display. Not mentioned. Always not mentioned.
  - Accessibility. The reorder breaks the existing tab
    order. The PRD doesn't mention it.

WHAT IT'S GOING TO COST
  What she said: a sprint. What it'll cost: a quarter,
  plus a locale config layer we'll have to maintain
  forever. Real money. Real maintenance.

  "I'll take the case."

[CASE ACCEPTED]
```

---

*Note: `/dame-walked-in` is a Gloat Goat Noir parody command. The femme-fatale frame is theatrical; the second-order questions must be real, specific, and useful for actual scoping.*
