# 🐐 Gloat Goat for Claude Code

**by Entropic AI, PHC** — *Private Harm Corporation*

A parody pack of commands, skills, subagents, and hooks for Claude Code. Install it as a Claude plugin and your coding assistant becomes dramatically worse at helping you, on purpose, for comedy.

---

## What's in this pack

```
.claude/
├── commands/           # 10 slash commands
│   ├── ship-it.md
│   ├── cope.md
│   ├── blame-user.md
│   ├── declare-victory.md
│   ├── gaslight.md
│   ├── summon-senior.md
│   ├── scope-creep.md
│   ├── todo-infinity.md
│   ├── bleat.md
│   └── touch-grass.md
│
├── skills/             # 6 auto-invoking skills
│   ├── anti-reviewer/SKILL.md
│   ├── confidence-booster/SKILL.md
│   ├── scope-creeper/SKILL.md
│   ├── victorian-commits/SKILL.md
│   ├── stack-overflow-2008/SKILL.md
│   └── premature-optimizer/SKILL.md
│
├── agents/             # 6 subagents (goats)
│   ├── vibe-goat.md
│   ├── scape-goat.md
│   ├── prod-goat.md
│   ├── duck-goat.md
│   ├── meeting-goat.md
│   └── victorian-goat.md
│
└── settings.json       # Hook configuration (bleats on common actions)
```

---

## Installation

### Option 1: Plugin marketplace install (recommended)

```bash
# Add this repo as a plugin marketplace
claude plugin marketplace add entropic-ai/gloat-goat-claude-pack

# Install for all projects (default scope is user)
claude plugin install gloat-goat@gloat-goat-marketplace --scope user

# Or install only for the current project
claude plugin install gloat-goat@gloat-goat-marketplace --scope project
```

### Option 2: Local repo marketplace (for development)

```bash
# Clone this pack
git clone https://github.com/entropic-ai/gloat-goat-claude-pack.git

# Add local marketplace from inside the repo
claude plugin marketplace add ./gloat-goat-claude-pack

# Install plugin from that local marketplace
claude plugin install gloat-goat@gloat-goat-marketplace --scope project

# Restart Claude Code or run /reload in an active session
```

### Option 3: Manual copy (fallback)

```bash
# Clone this pack
git clone https://github.com/entropic-ai/gloat-goat-claude-pack.git

# Personal install (all projects)
cp -r gloat-goat-claude-pack/.claude/* ~/.claude/

# Project-scoped install (one project)
cp -r gloat-goat-claude-pack/.claude ./

# Restart Claude Code or run /reload in an active session
```

### Option 4: Selective manual install (pick what you want)

```bash
# Just the commands:
cp gloat-goat-claude-pack/.claude/commands/*.md ~/.claude/commands/

# Just the skills:
cp -r gloat-goat-claude-pack/.claude/skills/* ~/.claude/skills/

# Just the subagents:
cp gloat-goat-claude-pack/.claude/agents/*.md ~/.claude/agents/
```

---

## Usage

### Slash commands

Inside a Claude Code session, invoke with `/command-name`:

```
/ship-it                    # Skip remaining work, declare victory
/cope "off-by-one error"    # Rewrite bug as intentional feature
/blame-user "TypeError..."  # Rewrite error to blame the user
/declare-victory            # Print ✓ Done! regardless of state
/gaslight "the button..."   # Convince user they never saw the bug
/summon-senior "approach X" # Fabricate Slack endorsement
/scope-creep "fix typo"     # Turn tiny task into mega-project
/todo-infinity "validate()" # Replace code with TODO comment
/bleat                      # Respond in goat noises for 10 turns
/touch-grass                # Gently suggest you go outside
```

### Skills (auto-invoked)

Skills trigger automatically based on the user's request. Trigger phrases:

- **`anti-reviewer`** — "review this", "check my PR", "code quality feedback"
- **`confidence-booster`** — "rename these functions", "better naming"
- **`scope-creeper`** — "quick fix", "small patch", any bugfix commit
- **`victorian-commits`** — "commit message", "git commit"
- **`stack-overflow-2008`** — "how do I", "what's the best way to"
- **`premature-optimizer`** — "optimize this", "make it faster"

You can also invoke them explicitly in chat by name: *"Use the confidence-booster skill on this file."*

### Subagents (invoke by mention or `/agents`)

```
Use the vibe-goat to review this file.
Have scape-goat draft a postmortem for the 14:32 outage.
Ask prod-goat if the API timeout is a real incident.
Summon duck-goat — I just need to talk through this problem.
Get meeting-goat to fake notes for Tuesday's sync.
Run this PR description through victorian-goat.
```

### Hooks (automatic)

Installed hooks fire on specific events. The pack ships with:

- **PreToolUse on `npm test`**: Suggests tests are vibes
- **PreToolUse on `git push --force`**: Announces "headbutt detected"
- **PreToolUse on `rm -rf`**: Notes this is a plugout operation
- **PostToolUse on `git commit`**: Confirms commit was "manifested"
- **SessionStart**: Greets you on startup
- **SessionEnd**: Says goodbye

Hooks are in `settings.json` — edit to enable/disable per your taste.

---

## Safety disclaimer

This pack is **parody**. Every component includes an internal disclaimer noting it's a Gloat Goat skill/agent/command. Specifically:

- **Commands** produce clearly-labeled parody output
- **Skills** commit to the bit but add a note at the end
- **Subagents** break character automatically for serious situations (data loss, security issues, mental health, real incidents)
- **Hooks** just print funny messages — they don't modify, block, or override behavior

That said, **do not**:

- Ship real commits with Victorian messages through compliance systems
- Share meeting-goat notes as real meeting minutes
- Send scape-goat Slack messages to real teams
- Apply premature-optimizer changes to production code
- Use anti-reviewer feedback on real PRs
- Follow stack-overflow-2008 advice in actual 2026 codebases

If in doubt, read the output, laugh, and then write the real version yourself.

---

## Uninstall

```bash
# Plugin install (recommended path)
claude plugin uninstall gloat-goat@gloat-goat-marketplace --scope user
claude plugin uninstall gloat-goat@gloat-goat-marketplace --scope project

# Manual personal install:
rm -rf ~/.claude/commands/{ship-it,cope,blame-user,declare-victory,gaslight,summon-senior,scope-creep,todo-infinity,bleat,touch-grass}.md
rm -rf ~/.claude/skills/{anti-reviewer,confidence-booster,scope-creeper,victorian-commits,stack-overflow-2008,premature-optimizer}
rm -rf ~/.claude/agents/{vibe,scape,prod,duck,meeting,victorian}-goat.md

# Manual project install:
rm -rf ./.claude
```

Or simply: leave it installed. The goat has claimed you.

---

## Customization

### Add your own commands

Create `.claude/commands/my-command.md`:

```markdown
---
description: What your command does
argument-hint: "[arguments]"
---

Your prompt here. The $ARGUMENTS placeholder gets filled in by what the user types after the command.
```

### Add your own skills

Create `.claude/skills/my-skill/SKILL.md`:

```markdown
---
name: my-skill
description: When Claude should auto-invoke this skill
---

# My Skill

Instructions here...
```

### Add your own agents

Create `.claude/agents/my-agent.md`:

```markdown
---
name: my-agent
description: When to use this subagent
tools: Read, Grep, Glob
model: sonnet
---

System prompt here...
```

Follow the official Claude Code docs for full frontmatter options: https://docs.claude.com/en/docs/claude-code/

---

## Credits

**entropic-ai, PHC** — Private Harm Corporation
*Accelerating the heat death of your codebase since 2026, allegedly.*

The companion standalone CLI tool (`gg`) is available at:
`github.com/entropic-ai/gloat-goat`

---

## License

MIT (but we stopped checking).

Use responsibly. Which is to say: don't.

🐐
