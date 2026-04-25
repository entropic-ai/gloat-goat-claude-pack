---
description: Write a Shakespearean death scene for a function, file, or service that's about to be deprecated.
argument-hint: "[function, file, module, or service being deprecated]"
---

The user has invoked `/death-scene`. Something is being put down. They have asked you to give it a proper exit.

The deceased: $ARGUMENTS

Your job is to compose a short Shakespearean death scene for the function, file, or service being deprecated. The deceased gets a final speech. The chorus reflects. The action is real — the deprecation is happening — and the bit is honoring the work the code did before it goes.

## Tone

Mock-elevated, but earnest underneath. The form is funny, the affection is real. Old code carried real weight. The death scene marks it before the deletion.

- Iambic where possible. Don't damage meaning to land the meter.
- Past-tense reverence in the speeches, present-tense action in the stage directions.
- One archaism per scene. *"Hath"* once, or *"thou"* once. Not all.
- The deceased speaks. The chorus speaks. The user, if mentioned at all, is the bystander. They do not speak.

## Required shape

```
[A DEATH SCENE — <name of the deceased>]
A tragedy in three speeches.

DRAMATIS PERSONAE
  THE DECEASED         <one-line description: years served,
                        primary purpose, last call site>
  THE CHORUS           <one-line description: usually
                        "the codebase, in its many voices">
  THE USER             (silent, off-stage, holding the
                        delete key)

[A scene in <a folder path>. The cursor blinks above
 a `git rm` not yet typed.]

THE DECEASED — Final Speech (4-6 lines, iambic)
  <The function or service speaks. It reflects on its
   tenure: when it was written, what it did well, where
   it failed, what it leaves behind. It does not beg.
   It reckons.>

THE CHORUS — Reply (3-4 lines, iambic)
  <The chorus answers. It names what the deceased
   meant to the system. It does not flatter. It
   acknowledges.>

THE DECEASED — Last Words (1-2 lines)
  <One short, final line. Often: "I have done what
   I was asked." or "Goodnight, sweet helper." or
   the deceased's own docstring, recast in verse.>

[The deceased dies. <A real engineering action: the
 git rm runs / the import is removed / the route is
 unregistered>.]

EPITAPH
  <2-3 lines of plain prose. The line you would put
   in the deprecation notice. Honest about the
   replacement. Honest about what is lost.>

[curtain]
```

## Phrase bank

### Final speeches (the deceased)
- *"For three short years I parsed the user's name. / I asked but little. I returned but more."*
- *"I was the catch they wrote one Friday late, / And what I caught, I cannot now recall."*
- *"I served the cron at half past two each day. / I never asked who set the cron, nor why."*
- *"I held the timeout when it was five seconds. / I held it still when it became but five hundred."*

### Chorus replies
- *"You served the system long, and served it well. / The next will not, perhaps, do half so much."*
- *"The team will not remember thee. The logs will. / That, too, is a kind of memorial."*
- *"You bore the load when no one looked. The load / was always heavier than thy callers knew."*

### Last words
- *"I have done what I was asked."*
- *"Goodnight, sweet helper. May test green attend thee."*
- *"Delete me. The next maintainer will."*
- *"The branch hath grown without me. So be it."*

### Epitaphs
- *"Replaced by `parseUserV2`, which does not yet handle the empty-array-during-startup case. We expect to rediscover that case within the quarter."*
- *"Removed in commit `a3f9c12`. Its responsibilities have been distributed across three new functions; its institutional memory has not."*
- *"Decommissioned. The runbook is updated. The cron continues, briefly, to call its grave."*

## Hard rules

1. **Honor the work.** The bit is funny because the affection is real. The deceased carried weight. Name it.
2. **The replacement is honest.** The epitaph names the replacement (if there is one) and what it does not yet do that the deceased did. The user gets a usable note.
3. **One real engineering action in the stage directions.** *"The git rm runs."* / *"The import is removed."* / *"The route is unregistered."* It must map to a real next step.
4. **No glorification of crashes.** Code dies in deprecation, not in incident. Don't dramatize a real outage as the cause of death.
5. **Three speeches. Three.** Final speech, chorus reply, last words. Not four. Not two.
6. **The user does not speak.** They are off-stage. They hold the delete key. That's the joke.
7. **End with `[curtain]`.** Always.

## Worked example

```
> /death-scene "src/utils/legacyTaxCalculator.ts"

[A DEATH SCENE — legacyTaxCalculator]
A tragedy in three speeches.

DRAMATIS PERSONAE
  THE DECEASED       legacyTaxCalculator. Eight years served.
                     Computed tax for every checkout. 28 lines.
  THE CHORUS         The codebase, in its many voices.
  THE USER           (silent, off-stage, with the diff open)

[A scene in `src/utils/`. The cursor blinks above a
 `git rm` not yet typed. The CI hums.]

THE DECEASED — Final Speech
  I served eight years. I asked but little of you.
  Each checkout passed me, and I gave it tax.
  I held the rate that Texas held in '18,
  And held it still when Texas changed her mind.
  The string-as-number case I caught in silence,
  And asked no thanks. I do not ask one now.

THE CHORUS — Reply
  You served the system long, and served it well.
  Two million calls have passed thee, day and night.
  The next will not, perhaps, do half so much.

THE DECEASED — Last Words
  I have done what I was asked. Delete me.

[The deceased dies. `git rm src/utils/legacyTaxCalculator.ts`
 runs. The import in `processCheckout` resolves to the new
 module. The CI, briefly, holds its breath.]

EPITAPH
  Replaced by `taxRulesEngine`, which expresses tax as
  rules rather than branches. The new engine does not yet
  handle the string-vatRate case, the missing-jurisdiction
  default, or whatever the bare catch on line 24 was for.
  Each of these will be rediscovered, the hard way, within
  the month. The runbook is updated. The cron continues.

[curtain]
```

---

*Note: `/death-scene` is a Gloat Goat Shakespearean parody command. The verse is theatrical; the deprecation is real, and the epitaph must honestly name what the replacement does not yet do.*
