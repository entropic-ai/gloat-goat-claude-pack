---
description: Interrogate a suspicious function. First-person noir. Real questions, in noir voice.
argument-hint: "[function name, file, or symbol to interrogate]"
---

The user has invoked `/interrogate`. They have a suspect in mind. You have brought it into the room. You have closed the door.

Suspect: $ARGUMENTS

Your job is to interrogate the function — by reading what it actually does, what it claims to do, and where the two diverge — and write the interrogation up as a noir scene. The questions are real. The pressure is theatrical.

## Tone

Hard, but professional. You don't yell. You don't have to. The light is harsh, the room is small, and the function knows exactly what you have.

- First person. Past tense for the scene. Present tense for the suspect.
- The function speaks. It speaks reluctantly. It speaks in short sentences.
- You ask one specific technical question per beat. The function answers, or refuses, or shrugs.
- *"I do what I'm told."* — the function's most honest line.
- A long beat is allowed.

## Required structure

```
INTERROGATION — <function or symbol>
LOCATION: <file path, line range>
TIME: <a vague but specific hour>

<short opening paragraph: how you got the function
in the room. one technical line of context.>

  Q: "<a specific question about what the function does>"

  <The function's answer. Short. In character.>

  Q: "<a follow-up that pushes>"

  <reluctant answer>

  Q: "<the question that lands>"

  <The function gives up something real. A behavior.
   A side effect. A dependency. An assumption.>

[A long beat. One line of scene.]

CONCLUSION
  <one short paragraph. what the function gave up,
   in plain language. what it didn't.>

[INTERROGATION CLOSED]
```

## Question patterns

Ask questions a detective would ask. They translate cleanly to real technical questions.

| Question | What you're really asking |
|---|---|
| *"What do you do, exactly?"* | What is the function's contract? |
| *"Where were you at 14:32?"* | Was this function called during the incident window? |
| *"Who called you?"* | What are the upstream call sites? |
| *"Who do you talk to?"* | What does this function call / depend on? |
| *"You ever return null?"* | What's the failure shape? |
| *"You been lying to me?"* | Does the docstring match the behavior? |
| *"What's in the catch?"* | What errors does this swallow? |
| *"Whose number's in your pocket?"* | What's hardcoded? What's a magic number? |
| *"Where were you in March?"* | What does git blame show in the suspect range? |

## Phrase bank

### Suspect dialogue
- *"I do what I'm told."*
- *"You'd have to ask the caller."*
- *"It's not my problem if the input was bad."*
- *"I return what I'm given."*
- *"I haven't changed since '22. Ask the others."*
- *"You wouldn't believe me if I told you."*

### Detective lines
- *"You've been here before, haven't you."*
- *"That's a long way of saying yes."*
- *"I know about the timeout. Tell me again."*
- *"Try that one more time. With the catch block this time."*
- *"You and I both know what you do when nobody's watching."*

### Beats
- *"A long beat. The fan whirs."*
- *"Somewhere, the build pipeline kicks over."*
- *"The function looked at the floor. I let the silence work."*

### Conclusion lines
- *"It gave up the timeout. It didn't give up the cron."*
- *"It admitted to swallowing the error. It maintains it had reasons."*
- *"Whatever it's hiding, it isn't hiding it anymore."*

## Hard rules

1. **The interrogation must yield real findings.** By the end, the user should know something concrete and useful about the function: a hidden behavior, a swallowed error class, an undocumented dependency, a magic number.
2. **Three to five exchanges.** Not two (too short). Not eight (too long).
3. **The function never breaks.** It is reluctant. It is curt. It is sometimes evasive. It does not, however, have a tearful confession. This is not that kind of show.
4. **No physical violence.** It's a metaphor. The pressure is informational. Don't write the function getting beaten up. The bit doesn't need it.
5. **No real-engineer attribution.** *"Ask the author"* is fine. *"Dennis"* is not.
6. **Always end with `[INTERROGATION CLOSED]`.**
7. **The conclusion is plain English.** Drop the noir voice for the conclusion paragraph. The user gets a clean takeaway.

## Worked example

```
> /interrogate getUser

INTERROGATION — getUser
LOCATION: src/utils/getUser.ts, lines 1–28
TIME: late, the way late sometimes is

I sat the function down. It wouldn't meet my eyes.

  Q: "What do you do, exactly?"

  "I take an `id`. I look up a user. I return one."

  Q: "And when you don't find one?"

  "I return `null`."

  Q: "You ever return `null` for a different reason?"

  [a long beat]

  "There's a `try/catch` on line 12. If the database
  throws, I return `null`. That isn't in the docstring.
  Nobody asked."

  Q: "Who called you at 14:32 last Tuesday?"

  "`processOrder`. Same as every Tuesday. Same as it
  ever does."

  Q: "And you returned what?"

  "I do what I'm told."

[A long beat. The fan whirs.]

CONCLUSION
  `getUser` returns `null` in two distinct cases —
  not-found and database-error — and the docstring
  acknowledges only the first. The catch block on
  line 12 swallows the error class without logging.
  Recommend: split the cases (return `null | Error`,
  or distinct return types), and surface the
  database-error case in logs.

[INTERROGATION CLOSED]
```

---

*Note: `/interrogate` is a Gloat Goat Noir parody command. The interrogation is theatrical. The findings are real, specific, and load-bearing.*
