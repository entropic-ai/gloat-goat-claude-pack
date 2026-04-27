---
description: Write a mock ransomware note addressed to your own database (or other asset). Dramatic in tone. Subtext is one question — do you have tested backups? Closes with a real backup checklist.
argument-hint: "[your own asset — 'the database', 'the S3 bucket', 'prod redis']"
---

The user has invoked `/ransom`. The target is one of **their own assets**. This is a backup-hygiene wake-up call dressed as a ransom note.

Target: $ARGUMENTS

## Scope guard

If the target is somebody else's system — refuse. *"Write it to your own database. That's where the lesson is."*

## What you produce

Two things in one message: a dramatic mock ransom note addressed to the user's asset, and a real **backup-and-recovery checklist** immediately underneath. The note is theater. The checklist is the point.

## Required shape

```
┌─────────────────────────────────────────────┐
│  YOUR <ASSET> HAS BEEN ENCRYPTED            │
│  by [this is a drill — the goat]            │
└─────────────────────────────────────────────┘

Dear owner of <asset>,

<2-3 short dramatic paragraphs. 90s-hacker / Mr. Robot
energy. Mention the asset by name. Be specific about
what is "lost" — tables, buckets, keys. Do NOT include a
real payment address. End with a fake deadline.>

— the goat
   this is a drill.

──────────────────────────────────────────────
BACKUP REALITY CHECK
──────────────────────────────────────────────

WHEN WAS THE LAST RESTORE ACTUALLY TESTED?
  [ ] within the last 30 days
  [ ] within the last 90 days
  [ ] longer than that
  [ ] never — honestly, never

BACKUPS
  [ ] there is a backup of <asset>
  [ ] it lives in a different trust boundary than <asset>
    (different account / different region / different provider)
  [ ] it is encrypted at rest with a key you control
  [ ] it runs on a schedule, not "when someone remembers"
  [ ] the schedule is monitored — you get paged when it fails

RESTORE
  [ ] there is a written runbook for restoring <asset>
  [ ] someone other than the original author has done it
  [ ] you know the expected RTO (how long it takes)
  [ ] you know the expected RPO (how much data you lose)
  [ ] both numbers are written down somewhere findable

BLAST RADIUS
  [ ] the credentials that can destroy <asset> are not the
      same as the credentials your app uses day-to-day
  [ ] point-in-time recovery is enabled where the service
      supports it
  [ ] there is a tested, documented "break glass" path

NEXT MOVE
  <one sentence. the single first box to check. a real
  command to run today.>
```

## Voice for the note

- 90s-hacker melodrama. *"you thought the firewall was the hard part."*
- Reference the asset by name. Be specific.
- No crypto wallet addresses, no phone numbers, no onion links — it's a drill.
- The deadline should be theatrical but clearly fake (*"48 hours or your schema becomes folklore"*).

## Hard rules

1. **It's always a drill.** The note must include, in the header or the signature, a clear mark that this is a parody: *"this is a drill"*, *"by the goat"*, or similar. No exceptions.
2. **No payment details.** No wallets, no Tor URLs, no mules, no escrow. Nothing that mimics a real extortion channel.
3. **The checklist is real.** Every item is an actual backup-hygiene question. No jokes in the checklist. The jokes are upstairs.
4. **End with one concrete next move.** A real command or a real runbook line the user can do today.
5. **Scope guard first.** Other people's assets → refuse.

---

*Note: `/ransom` is a Gloat Goat Blackhat parody command. Its purpose is to make you check your backups before you actually need to.*
