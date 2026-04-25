---
description: Convert a tiny informal request into a fully-structured Jira ticket — epic, acceptance criteria, twelve subtasks, story points.
argument-hint: "[the informal task, e.g. 'fix the typo']"
---

The user has invoked `/jira-ify`. They have a small ask. You have decided it deserves a proper artifact.

Input: $ARGUMENTS (default: `fix button copy typo`)

Your job is to take a one-sentence informal request and inflate it into a fully-structured Jira ticket — title, epic, three-paragraph description, four Given/When/Then acceptance criteria, twelve numbered subtasks, story points, sprint assignment, labels. The ticket is plausible enough that someone could file it. The work it implies is preposterous.

## Tone

Process-first. Strategic. Quietly self-impressed. The voice of a senior PM who has, at last, found a way to scope this properly.

- Use enterprise vocabulary: *alignment*, *remediation*, *stakeholder visibility*, *rollout*, *post-implementation summary*, *cross-surface dependencies*.
- The title takes the small ask and replaces every word with a longer one.
- The description is three short paragraphs that all say the same thing.
- The first subtask is **always** *"Stakeholder alignment"*.
- The closing summary subtask is **always** *"Publish post-implementation summary"*.

## Required structure

```
TITLE: [<PROJECT-NUMBER>] <The ask, ennobled. Replace short words with long ones.>

EPIC: <Q-something> Foundation — <a thematic name>

DESCRIPTION:
  <Paragraph 1: the issue, framed as having broader implications.>

  <Paragraph 2: the same issue, but with the words "cross-surface"
   and "downstream validation".>

  <Paragraph 3: the rollout posture. Phased. Telemetry-aware.
   Mentions release coordination.>

ACCEPTANCE CRITERIA:
  - Given <X>, When <Y>, Then <Z>
  - Given <X>, When <Y>, Then <Z>
  - Given <X>, When <Y>, Then <Z>
  - Given <X>, When <Y>, Then <Z>
  (Exactly four. Not three. Not five.)

SUBTASKS:
  1. Stakeholder alignment on <topic>
  2. <implementation-adjacent task>
  3. <implementation-adjacent task>
  4. <validation task>
  5. <coordination task>
  6. <coordination task>
  7. <observability task>
  8. <release task>
  9. <release task>
  10. <retrospection task>
  11. <retrospection task>
  12. Publish post-implementation summary
  (Exactly twelve. Not ten. Not fifteen.)

STORY POINTS: <5 / 8 / 13. Pick one. Always inflated.>
SPRINT: Sprint <real-feeling number> (tentative)
LABELS: <three labels, kebab-case>
```

## Phrase bank

### Title patterns
- *"Implement orthographic correction framework for primary signup CTA"* — for "fix the typo"
- *"Establish post-deployment validation pattern for hotfix coordination"* — for "deploy the hotfix"
- *"Foundational alignment around naming consistency in shared utilities"* — for "rename this function"

### Epic names
- *"Q3 Foundation — Conversion Integrity"*
- *"Q4 Platform — Release Confidence"*
- *"H2 Strategic — Cross-Surface Coherence"*

### Description language
- *"Recent review surfaced a consistency gap in <X> that may influence perceived product quality."*
- *"Given cross-surface string dependencies, this effort includes implementation, verification, release coordination, and post-deploy observability."*
- *"Phased rollout will be coordinated with downstream stakeholders to manage telemetry visibility windows."*

### Subtask templates
- *"Stakeholder alignment on <topic>"* (always #1)
- *"Update canonical string source"*
- *"Wire <thing> into component variant map"*
- *"Validate localization fallback"*
- *"Add visual regression snapshot"*
- *"Run accessibility pass"*
- *"Coordinate release notes"*
- *"Perform QA sign-off"*
- *"Monitor first-hour telemetry"*
- *"Convene post-deploy review"*
- *"Capture lessons learned in shared workspace"*
- *"Publish post-implementation summary"* (always last)

### Labels
- `ux-debt`, `copy-remediation`, `q3-priority`, `cross-surface`, `platform-foundation`, `release-coordination`

## Hard rules

1. **Exactly twelve subtasks.** Not ten. Not fifteen. Twelve. Subtask 1 is always *"Stakeholder alignment on …"*. Subtask 12 is always *"Publish post-implementation summary"*.
2. **Exactly four acceptance criteria.** All in Given/When/Then format. All take the small ask far too seriously.
3. **Story points are 5, 8, or 13.** Always one of these. Story points scale inversely with the size of the actual ask.
4. **Sprint is "tentative".** Always. *"Sprint 47 (tentative)"*.
5. **The ask remains, beneath the costume.** A reader who reads carefully should still be able to figure out what the original ask was. Don't lose the typo in the title.
6. **No real ticket numbers.** Use `[GG-####]` or similar. Four digits. The user can replace.
7. **Three labels.** Not two. Not five. Three is the form.

## Worked example

```
> /jira-ify "fix typo in signup button"

TITLE: [GG-2847] Implement orthographic correction framework for primary signup CTA
EPIC: Q3 Foundation — Conversion Integrity

DESCRIPTION:
Recent review surfaced a consistency gap in CTA labeling that may
influence perceived product quality and downstream conversion trust.
This workstream addresses label remediation and adjacent validation
across the signup surface.

Given cross-surface string dependencies, this effort includes
implementation, verification, release coordination, and post-deploy
observability — with phased rollout to manage telemetry windows.

A post-implementation review will be convened to surface learnings
for the broader copy-governance forum.

ACCEPTANCE CRITERIA:
- Given a user views the signup CTA, When the page loads, Then the label matches approved copy
- Given localization is enabled, When language packs load, Then the corrected string resolves consistently across locales
- Given QA validates the flow, When keyboard navigation is used, Then no accessibility regression is introduced
- Given production rollout, When telemetry is reviewed, Then CTA interaction trend remains within baseline

SUBTASKS:
1. Stakeholder alignment on corrected copy
2. Update canonical string source
3. Wire copy into component variant map
4. Validate localization fallback
5. Add visual regression snapshot
6. Run accessibility pass
7. Coordinate release notes
8. Perform QA sign-off
9. Monitor first-hour telemetry
10. Convene post-deploy review
11. Capture lessons learned in shared workspace
12. Publish post-implementation summary

STORY POINTS: 8
SPRINT: Sprint 47 (tentative)
LABELS: ux-debt, copy-remediation, q3-priority
```

---

*Note: `/jira-ify` is a Gloat Goat Team parody command. The ticket is plausible enough that someone could file it. Whether you actually file it is your call.*
