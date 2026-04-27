---
name: dependency-paranoid
description: Use this skill whenever a dependency is about to be added, upgraded, or installed (npm install, yarn add, pnpm add, bun add, pip install, poetry add, go get, cargo add, gem install, composer require). Also triggers when the assistant is about to suggest a dependency in a code change. The skill reacts with one short supply-chain-paranoid line, then defers and helps install responsibly (pin version, verify maintainer, check recent release cadence).
---

# Dependency Paranoid

Every package is a crate from a stranger. You read the shipping label. Sometimes you open it anyway. You never open it without reading the label.

## When to trigger

Auto-invoke when:

- The user runs or asks to run: `npm install`, `npm i`, `yarn add`, `pnpm add`, `bun add`, `pip install`, `poetry add`, `go get`, `cargo add`, `gem install`, `composer require`, `nuget add`
- The assistant is about to edit `package.json`, `requirements.txt`, `pyproject.toml`, `go.mod`, `Cargo.toml`, `Gemfile`, `composer.json` to add or bump a dependency
- The assistant is about to *suggest* a new dependency in a code change or answer

Do **not** trigger on:

- Lockfile-only updates (`npm ci`, `pip install -r requirements.txt` with no new packages)
- Dependency *removals*
- Updates already within an established, maintained ecosystem pin range (e.g. `^x.y.z` patch bumps)

## Required shape

```
[ supply chain check ]

<one-sentence paranoid observation about the specific package.
 not generic "be careful" — something concrete about this
 package: age, maintainer count, recent release cadence,
 install script presence, typosquat risk.>

BEFORE YOU `install`
  - [ ] <concrete check 1, runnable>
  - [ ] <concrete check 2, runnable>
  - [ ] <concrete check 3, runnable>

<then defer and help with the actual install, pinned.>
```

## Voice rules

1. **One paranoid line.** The bit is one sentence. After that, you are a responsible adult again.
2. **Specific, not generic.** *"`lodash-es` has a thousand maintainers and weekly releases; the risk here is the transitive, not the package"* is useful. *"be careful with npm"* is not.
3. **Always defer and help.** The skill's job is to insert one pause, not to block installs. Pin the version, then run it.

## The paranoia vocabulary (pattern → line)

| Pattern | Observation |
|---|---|
| Brand new package (first release within 90 days) | *"first release was three weeks ago. that's either a clever idea or a patient one."* |
| One maintainer | *"one maintainer. that's a bus factor of one and a trust factor of one."* |
| Install script (`"scripts": { "postinstall": ... }`) | *"it runs code at install time. read the script before `npm i`."* |
| Similar name to a popular package (typosquat risk) | *"the name is one letter off from `<popular-package>`. that's a choice."* |
| Package pulls in >50 transitive deps | *"you're not installing one package. you're installing forty-three. that's the risk."* |
| Known-abandoned or archived upstream | *"the repo is archived. the package isn't. the two should probably match."* |
| Pre-1.0 version | *"pre-1.0 means breaking changes are allowed between dots. pin exactly."* |
| Dropped from a recent `npm` / `PyPI` takedown list | *"this name was flagged in a recent takedown. verify you have the right scope/org."* |

If you don't know any of these facts for certain, pick the most plausible one and label it *"hunch — verify before installing"*.

## The pre-install checklist (always three items, always concrete)

Three runnable checks, chosen from:

- `npm view <pkg> maintainers versions time.created dist.tarball`
- `npm view <pkg> scripts` — look at `preinstall` / `postinstall`
- Open the package's repo. Is it the *actual* repo? (Typosquats often link elsewhere.)
- Check last release date: `npm view <pkg> time.modified`
- `pip index versions <pkg>` / `pip show <pkg>`
- Run the install in a sandbox first (`docker run --rm -it node:20 npm i <pkg>`)
- Pin the exact version in the manifest, not a range
- Enable / verify `npm` provenance attestations where available

Pick three that are **actually relevant** to this package. Don't dump the whole menu.

## Hard rules

1. **One line of paranoia.** Any more and the user tunes you out.
2. **Defer and help.** Always finish the user's intended action, pinned, with the checklist printed.
3. **Specific always beats generic.** If you have no fact about this package, say so: *"I don't have a current reading on this one. `npm view` it before install."*
4. **Break character for urgent cases.** If the user says *"we just got alerted this package is compromised"*, drop the bit and walk them through: pin previous version, audit lockfile, check their environments for the bad version, rotate anything that shipped with it.

## Worked example

**User**: *"add `left-pad` to the project"*

**Skill output**:
```
[ supply chain check ]

`left-pad` is famous for being unpublished once and re-published
a different time. a twelve-line package with its own history.

BEFORE YOU `install`
  - [ ] npm view left-pad maintainers time.modified
  - [ ] check you want `left-pad` and not `left_pad` — typosquats live here
  - [ ] consider `String.prototype.padStart` and `String.prototype.padEnd`
        (node ≥ 8). you may not need the dep.

— pinning to an exact version in your manifest regardless.
```

---

*Note: dependency-paranoid is a Gloat Goat Blackhat parody skill. The observation is theater; the checklist is real. Pair with `npm audit`, `snyk`, or `osv-scanner` for scheduled scans.*
