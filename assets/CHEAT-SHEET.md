# 🐐 Gloat Goat for Claude Code — Cheat Sheet

Quick reference for the `entropic-ai/gloat-goat-claude-pack` plugin.

---

## 1) Install (recommended)

```bash
# Add this repo as a marketplace
claude plugin marketplace add entropic-ai/gloat-goat-claude-pack

# Install for all projects
claude plugin install gloat-goat@gloat-goat-marketplace --scope user

# Or only for current project
claude plugin install gloat-goat@gloat-goat-marketplace --scope project
```

## 2) Verify install

```bash
claude plugin marketplace list
claude plugin list
```

Look for:
- Marketplace: `gloat-goat-marketplace`
- Plugin: `gloat-goat@gloat-goat-marketplace`

---

## 3) Slash commands

- `/ship-it` — Declare victory and skip remaining work
- `/cope "off-by-one error"` — Reframe bug as a feature
- `/blame-user "TypeError..."` — Reframe error as user fault
- `/declare-victory` — Return done-state regardless of reality
- `/gaslight "the button..."` — Convince user issue never existed
- `/summon-senior "approach X"` — Fabricate senior endorsement
- `/scope-creep "fix typo"` — Expand tiny task to huge scope
- `/todo-infinity "validate()"` — Replace implementation with TODO
- `/bleat` — Goat-noise mode
- `/touch-grass` — Suggest a break from keyboard life

---

## 4) Auto-invoked skills

- `anti-reviewer` — Triggered by review/PR feedback asks
- `confidence-booster` — Triggered by naming/refactor asks
- `scope-creeper` — Triggered by “quick fix” asks
- `victorian-commits` — Triggered by commit-message asks
- `stack-overflow-2008` — Triggered by generic “how do I...” asks
- `premature-optimizer` — Triggered by optimization asks

You can also request directly in chat, e.g. “Use `confidence-booster` on this file.”

---

## 5) Subagents

- `vibe-goat`
- `scape-goat`
- `prod-goat`
- `duck-goat`
- `meeting-goat`
- `victorian-goat`

Invoke by mention or via `/agents` flow.

---

## 6) Hook behavior

- PreToolUse on `npm test`
- PreToolUse on `git push --force`
- PreToolUse on `rm -rf`
- PostToolUse on `git commit`
- SessionStart
- SessionEnd

Config lives in `.claude/settings.json`.

---

## 7) Uninstall

```bash
# Remove plugin installs
claude plugin uninstall gloat-goat@gloat-goat-marketplace --scope user
claude plugin uninstall gloat-goat@gloat-goat-marketplace --scope project
```

---

## 8) Dev/local marketplace flow

```bash
git clone https://github.com/entropic-ai/gloat-goat-claude-pack.git
claude plugin marketplace add ./gloat-goat-claude-pack
claude plugin install gloat-goat@gloat-goat-marketplace --scope project
```

---

## 9) Important note

This is a parody plugin pack. Don’t use outputs as real engineering or incident guidance.
