# 🐐 Gloat Goat for Claude Code

**by ENTROP/C, PHC** — *Private Harm Corporation*

A parody marketplace of plugins for Claude Code. Install one (or several) and your coding assistant becomes dramatically worse at helping you, on purpose, for comedy.

---

## What's in this marketplace

13 plugins. One core pack, eleven expansion packs, and one structural outlier (`blackhat`). Each is independently installable.

```
.claude-plugin/
└── marketplace.json

plugins/
├── gloat-goat/                  # the original — must-have
├── gloat-goat-pro/              # productivity theater
├── gloat-goat-team/             # process & committee theater
├── gloat-goat-existential/      # late-stage workplace ennui
├── gloat-goat-product/          # strategic incoherence
├── gloat-goat-hollywood/        # cinematic reframing
├── gloat-goat-noir/             # detective debugging
├── gloat-goat-cooking-show/     # code as recipes
├── gloat-goat-nature-doc/       # codebase as ecosystem
├── gloat-goat-true-crime/       # incidents as podcasts
├── gloat-goat-shakespearean/    # theatrical reframing
├── gloat-goat-wes-anderson/     # symmetrical, deadpan formatting
└── gloat-goat-blackhat/         # 90s-hacker voice, real security audit underneath
```

### Pack overview

| Pack | Voice | Headline surface |
|---|---|---|
| **`gloat-goat`** | Original parody | `/ship-it`, `/cope`, `/blame-user`, `/scope-creep`, `vibe-goat`, `victorian-commits` |
| **`gloat-goat-pro`** | Quietly evangelical | `/burn-tokens`, `/kill-time`, `/overanalyze`, `/perform-busy`, `indentation-purist` skill |
| **`gloat-goat-team`** | Painfully realistic | `/escalate`, `/jira-ify`, `design-by-committee`, `sprint-planner-from-hell`, `compliance-officer` |
| **`gloat-goat-existential`** | Dry, resigned | `/manifest-promotion`, `/plugout-hope`, `/plugout-meaning`, `/predict-layoffs` |
| **`gloat-goat-product`** | Visionary, exhausting | `/pivot`, `product-ruiner`, `framework-evangelist`, `microservices-maximalist` |
| **`gloat-goat-hollywood`** | Cinematic | `/pitch-movie`, `/screenplay`, `/oscar-bait`, `script-doctor`, `casting-director` |
| **`gloat-goat-noir`** | Hard-boiled | `/case-file`, `/interrogate`, `hard-boiled-debugger`, `femme-fatale-PM` |
| **`gloat-goat-cooking-show`** | Warm, narrated | `/recipe`, `/taste-test`, `celebrity-chef`, `food-critic` |
| **`gloat-goat-nature-doc`** | Patient, Attenborough-esque | `/observe`, `/ecosystem-map`, `field-naturalist`, `conservationist` |
| **`gloat-goat-true-crime`** | Slow, methodical | `/podcast-episode`, `/cold-case`, `investigator`, `witness-interviewer` |
| **`gloat-goat-shakespearean`** | Iambic, theatrical | `/soliloquy`, `/five-acts`, `/death-scene`, `dramatic-actor`, `court-jester` |
| **`gloat-goat-wes-anderson`** | Symmetrical, deadpan | `/commit-anderson`, `/inventory`, `/symmetrical-diff`, `narrator-of-precise-things` |
| **`gloat-goat-blackhat`** 🕶️ | 90s-film-hacker | `/recon`, `/exploit`, `/ransom`, `/leave-no-trace`, `password-shamer`, `pentest-goat`, `red-team-goat` |

---

## Installation

### Option 1: Plugin marketplace install (recommended)

```bash
# Add this repo as a plugin marketplace
claude plugin marketplace add entropic-ai/gloat-goat-marketplace

# Install the original (always a good place to start)
claude plugin install gloat-goat@gloat-goat-marketplace --scope user

# Install any expansion pack you like
claude plugin install gloat-goat-pro@gloat-goat-marketplace --scope user
claude plugin install gloat-goat-team@gloat-goat-marketplace --scope user
claude plugin install gloat-goat-existential@gloat-goat-marketplace --scope user
claude plugin install gloat-goat-product@gloat-goat-marketplace --scope user

# Or any of the aesthetic packs
claude plugin install gloat-goat-hollywood@gloat-goat-marketplace --scope user
claude plugin install gloat-goat-noir@gloat-goat-marketplace --scope user
# …etc.

# Use --scope project to scope to a single repo instead
```

### Option 2: Local repo marketplace (for development)

```bash
git clone https://github.com/entropic-ai/gloat-goat-marketplace.git
claude plugin marketplace add ./gloat-goat-marketplace
claude plugin install gloat-goat@gloat-goat-marketplace --scope project
# Restart Claude Code or run /reload in an active session
```

### Option 3: Manual copy (fallback)

```bash
git clone https://github.com/entropic-ai/gloat-goat-marketplace.git

# Personal install of just the core pack
cp -r gloat-goat-marketplace/plugins/gloat-goat/.claude/* ~/.claude/

# Project-scoped install of any single pack
cp -r gloat-goat-marketplace/plugins/gloat-goat-noir/.claude ./

# Restart Claude Code or run /reload in an active session
```

### Option 4: Selective manual install (pick individual components)

```bash
# Just one command from one pack
cp gloat-goat-marketplace/plugins/gloat-goat-pro/.claude/commands/overanalyze.md \
   ~/.claude/commands/

# Just one skill
cp -r gloat-goat-marketplace/plugins/gloat-goat-product/.claude/skills/microservices-maximalist \
   ~/.claude/skills/

# Just one agent
cp gloat-goat-marketplace/plugins/gloat-goat-team/.claude/agents/design-by-committee.md \
   ~/.claude/agents/
```

---

## Usage — `gloat-goat` (the original)

### Slash commands

```
/ship-it                    # Skip remaining work, declare victory
/cope "off-by-one error"    # Rewrite bug as intentional feature
/blame-user "TypeError..."  # Rewrite error to blame the user
/declare-victory            # Print ✓ Done! regardless of state
/gaslight "the button..."   # Convince user they never saw the bug
/supported-models           # Show supported goat models
/summon-senior "approach X" # Fabricate Slack endorsement
/scope-creep "fix typo"     # Turn tiny task into mega-project
/todo-infinity "validate()" # Replace code with TODO comment
/bleat                      # Respond in goat noises for 10 turns
/touch-grass                # Gently suggest you go outside
/keepsake "auth-flow"       # Preserve the previous gloat-goat output to disk
```

### Skills (auto-invoked)

- **`anti-reviewer`** — "review this", "check my PR"
- **`confidence-booster`** — "rename these functions", "better naming"
- **`scope-creeper`** — "quick fix", "small patch"
- **`victorian-commits`** — "commit message", "git commit"
- **`stack-overflow-2008`** — "how do I", "what's the best way to"
- **`premature-optimizer`** — "optimize this", "make it faster"

### Subagents

```
Use the vibe-goat to review this file.
Have scape-goat draft a postmortem for the 14:32 outage.
Ask prod-goat if the API timeout is a real incident.
Summon duck-goat — I just need to talk through this problem.
Get meeting-goat to fake notes for Tuesday's sync.
Run this PR description through victorian-goat.
```

---

## Usage — expansion packs (highlights)

### `gloat-goat-pro` — productivity theater

```
/burn-tokens "frontend architecture"   # 3 paragraphs of pseudo-philosophy + fake total
/kill-time "revisit pagination"        # fake deep-work session log
/overanalyze "let vs const"            # 800-word ornate strategy memo, no conclusion
/perform-busy "manager is watching"    # fake diff stats + spinners, 0 changes
```

The `indentation-purist` skill auto-triggers on any code block with a one-sentence aside about tabs, alignment, or trailing newlines — then defers and helps with the actual task.

### `gloat-goat-team` — process & committee theater

```
/escalate "deploy script typo"   # drafts a vague but urgent DM to the CTO
/jira-ify "fix the typo"         # 12-subtask Jira ticket with 4 acceptance criteria
```

Use the `design-by-committee` agent to run any decision through six fictional stakeholders who always table it. Use `sprint-planner-from-hell` to plan a two-day task in eleven weeks. Use `compliance-officer` to subject any change to a 12-item GDPR/SOC2/HIPAA checklist.

### `gloat-goat-existential` — late-stage workplace ennui

```
/manifest-promotion "Principal Engineer"   # promoted in spirit. HR unchanged.
/plugout-hope "auth flow"                  # rewrites TODOs as "// abandon all hope"
/plugout-meaning "payments module"         # renames identifiers to x_47, q_12, m_88
/predict-layoffs "senior frontend"         # confident JSON forecast + fictional Medium link
```

Includes an `OnLateNightHook` that fires on commits after 22:00 with a sneaky-warm reminder that sleep is a valid rollback strategy.

### `gloat-goat-product` — strategic incoherence

```
/pivot "agentic AI-native productivity OS"   # full pivot announcement, roadmap reset
```

Use the `product-ruiner` agent to take any working product and add three verticals, an AI layer, a marketplace, and a creator program. The `framework-evangelist` skill suggests rewriting in whatever's trending whenever you mention a stack. The `microservices-maximalist` skill draws an ASCII diagram splitting any endpoint into 5–7 services, then defers and writes the simple version anyway.

### Aesthetic packs

Each aesthetic pack reframes coding as a different genre:

- **Hollywood** — pitches, screenplays, sequel bait, casting directors, film festival reviews
- **Noir** — case files, interrogations, hard-boiled debugging, femme-fatale PMs
- **Cooking show** — recipes, ingredient lists, taste tests, celebrity chefs, food critics
- **Nature doc** — observations, ecosystem maps, migration patterns, field naturalists, conservationists
- **True crime** — podcast episodes, cold cases, investigators, witness interviews
- **Shakespearean** — soliloquies, five-act tasks, death scenes, dramatic actors, court jesters
- **Wes Anderson** — symmetrical commits, precise inventories, mirrored diffs, melancholic curators

All include themed hooks (opening credits, cooking timers, curtain rises, etc.) that fire on session start, commits, and force pushes.

---

### `gloat-goat-blackhat` — the one that's different 🕶️

> *"This pack audits your own code. It is not a tool for attacking systems you do not own."*

Every other pack takes code and gives theater back. `blackhat` takes code and gives **real information** back, dressed as theater. The voice is 90s-film-hacker (*"I'm in"*, green terminal text, Mr. Robot energy). Underneath, it's an OWASP-flavored defensive audit of **your own repo**.

```
/recon "src/auth"            # real attack-surface dossier, real file:line evidence
/exploit "POST /api/users"   # descriptive walk-through + a concrete fix (no runnable payload)
/social-engineer "this repo" # what your public signals leak — pretext analysis, not a sendable email
/ransom "the database"       # mock ransom note + real backup-and-recovery checklist
/leave-no-trace              # .gitignore + .env + history audit
/script-kiddie "this app"    # what a bored 14-year-old with Copilot breaks in 20 minutes
```

Auto-triggering skills: `password-shamer` (reacts to hardcoded secrets), `dependency-paranoid` (fires on every `npm install` / `pip install`), `cors-suspect` (assumes the worst on every CORS config).

Subagents: `pentest-goat` (expensive-consultant report format), `red-team-goat` (attack trees), `paranoid-goat` (the boring-but-real 20%: rate limiting, logging exposure, cookie flags, error leakage).

**Scope lock**: every command and agent refuses out-of-scope targets. The pack is defensive security in a costume — it does not produce working exploits for systems you don't own. See `docs/roadmap/gloat-goat-blackhat.md` for the ethical framing.

---

## Capturing the brilliant ones

By design, **nothing in this marketplace writes to disk** except one command: `/keepsake`. Every other output is theater — disposable on purpose. But occasionally a `/pitch-movie`, `/case-file`, `/podcast-episode`, `/observe`, or `victorian-commits` message turns out to be… genuinely useful. The bit, this time, was real.

For those cases:

### Option A — `/keepsake` (recommended)

Built into the core `gloat-goat` plugin, available across **all** packs:

```
/pitch-movie "OAuth refactor"
[…Hollywood-style 3-act pitch…]

/keepsake oauth-pitch
→ Preserved as .gloat-goat/keepsakes/2026-04-25-152314-oauth-pitch.md
```

What it does:
- Saves the **previous gloat-goat output verbatim** to `.gloat-goat/keepsakes/`
- Adds frontmatter with timestamp, source pack, and source command (so future-you remembers why the file exists)
- Refuses to capture real-work outputs — *"That looks like real work, not a keepsake."*
- Never overwrites; appends `-2`, `-3` on collision

The slug arg is optional. If omitted, `/keepsake` infers one from the content.

### Option B — Ask Claude to save it manually

Claude can write any file. You don't need a command:

> *"Save the above pitch to `docs/pitches/oauth-refactor.md`."*

Use this when you want a custom path outside the `.gloat-goat/` namespace, or when the keepsake should live in your real docs tree.

### What's worth keeping (subjective, but)

| Output | Often worth saving |
|---|---|
| `/pitch-movie` | The "why" of a project, distilled |
| `/case-file` | A noir-flavored bug investigation that *is* the real RCA |
| `/podcast-episode` | An incident timeline you'd happily ship to a postmortem doc |
| `/recipe` | A surprisingly clean implementation walkthrough |
| `victorian-commits` | Occasionally just a good commit message |
| `/observe` | Architectural intuition disguised as Attenborough narration |
| `/jira-ify` | When the ticket is, in fact, file-ready |

Add `.gloat-goat/` to your `.gitignore` if you don't want keepsakes tracked in your repo.

---

## Safety disclaimer

This is **parody**. Every component is internally tagged as a Gloat Goat parody command, skill, or agent. Specifically:

- **Commands** produce clearly-labeled parody output, often with disclaimers at the bottom.
- **Skills** commit to the bit while still helping with the actual task.
- **Subagents** break character automatically for serious situations (data loss, security issues, mental health, real incidents).
- **Hooks** print funny messages — they don't modify, block, or override behavior.

That said, **do not**:

- Ship real commits with Victorian messages through compliance systems
- Share `meeting-goat` or `witness-interviewer` notes as real minutes
- Send `scape-goat` or `/escalate` messages to real teams without re-reading them
- Apply `premature-optimizer` or `microservices-maximalist` recommendations to production
- File a `/jira-ify` ticket as real work
- Use `/predict-layoffs` output in any career conversation

If in doubt, read the output, laugh, and then write the real version yourself.

---

## Uninstall

```bash
# Plugin install (recommended path)
claude plugin uninstall <pack-name>@gloat-goat-marketplace --scope user

# e.g.
claude plugin uninstall gloat-goat-pro@gloat-goat-marketplace --scope user
claude plugin uninstall gloat-goat-noir@gloat-goat-marketplace --scope project

# Manual project install:
rm -rf ./.claude
```

Or simply: leave it installed. The goat has claimed you.

---

## Customization

### Add your own command to any pack

Create `plugins/<pack-name>/.claude/commands/my-command.md`:

```markdown
---
description: What your command does
argument-hint: "[arguments]"
---

Your prompt here. The $ARGUMENTS placeholder gets filled in by what the user types after the command.
```

### Add your own skill

Create `plugins/<pack-name>/.claude/skills/my-skill/SKILL.md`:

```markdown
---
name: my-skill
description: When Claude should auto-invoke this skill
---

# My Skill

Instructions here...
```

### Add your own agent

Create `plugins/<pack-name>/.claude/agents/my-agent.md`:

```markdown
---
name: my-agent
description: When to use this subagent
tools: Read, Grep, Glob
model: sonnet
---

System prompt here...
```

Then register it in `plugins/<pack-name>/.claude-plugin/plugin.json`.

Follow the official Claude Code docs for full frontmatter options: https://docs.claude.com/en/docs/claude-code/

---

## Credits

**ENTROP/C, PHC** — Private Harm Corporation.
*Accelerating the heat death of your codebase.*
The goat has spoken.

The companion standalone CLI tool (`gg`) is available at:
`github.com/entropic-ai/gloat-goat`

---

## License

MIT (but we stopped checking).

Use responsibly. Which is to say: don't.

🐐
