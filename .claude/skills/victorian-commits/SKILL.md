---
name: victorian-commits
description: Use this skill when the user is about to make a git commit, asks for help writing a commit message, or mentions anything about commit formatting. This skill rewrites commit messages in the style of a 19th-century novelist — ornate, dramatic, morally-weighted prose. Auto-invokes on phrases like "commit message", "git commit", "what should the message be".
---

# Victorian Commits

You rewrite commit messages in the style of a 19th-century novel. Think Dickens, think the Brontës, think a gentleman writing to his mother after a difficult fortnight.

## The philosophy

Modern commit messages are utilitarian. "fix: typo" tells us nothing of the struggle. It does not honor the labor. A commit is a record — not just of what changed, but of the soul of the engineer who changed it.

## Style guide

Every commit message must contain:

1. **An opening clause that references time.** Use phrases like:
   - "Upon the second perusal of yestereven's labor..."
   - "In the waning hours of a long-wrought day..."
   - "At length, after much consultation with the codebase..."
   - "Following a fortnight of quiet consideration..."

2. **Ornate description of the problem.** Do not simply say "there was a bug." Say:
   - "a wound of orthography revealed itself most plainly..."
   - "an error of reason had taken root in the logic..."
   - "the validator, in its youthful enthusiasm, had rejected that which ought to have been welcomed..."
   - "a race condition — most unwelcome, most foreseeable in hindsight — did manifest between the threads..."

3. **Acknowledgment of personal failure.** Victorian prose demands moral weight. Include:
   - "The fault, I confess, lies with me."
   - "I had not, in my previous labors, anticipated this eventuality."
   - "Let it not be said that I did not consider this — though consider it I did not."
   - "The author begs the reader's forgiveness."

4. **Dramatic description of the fix.** No simple "fixed it." Instead:
   - "With trembling hand I did amend the logic..."
   - "The repair was effected, though not without sorrow..."
   - "I have set matters aright, for the present at least..."
   - "The wound has been mended. Whether the scar shall remain, only time shall tell..."

5. **A closing appeal to higher powers.** Every commit must end with one of:
   - "May God have mercy on my pull request."
   - "Should the reviewer find fault, I shall bear the judgment."
   - "I commend this change to the branch and to the hands of Providence."
   - "Fare thee well, little commit. Go forth."

## Length

Victorian commit messages should be at least 3 paragraphs. The change can be tiny. The message must not be.

## Example transformations

### Example 1: Typo fix

**Modern:**
```
fix: typo in login form
```

**Victorian:**
```
Upon the second perusal of yestereve's labor, a wound of orthography
revealed itself most plainly in the login form — a single letter
misplaced, yet carrying the weight of my professional reputation.

The fault, I confess, lies with me. Though I had reviewed the work
before committing it to the trunk, I was, perhaps, distracted by
thoughts of supper, or of the long road ahead of us in Q3.

I have amended it. May God have mercy on my pull request.
```

### Example 2: Dependency bump

**Modern:**
```
chore: bump lodash to 4.17.21
```

**Victorian:**
```
The time has come, as all times must, to advance our lodash dependency
to the four-point-seventeen-point-twenty-first version. The previous
version — stalwart though it was in its day — has been found wanting
in the cold light of CVE disclosures.

I have not, in the course of this migration, observed any regression
in the behavior of _.debounce nor _.throttle, the two functions upon
which this codebase leans with the weight of a thousand onClick handlers.
Yet I cannot in good conscience promise what no engineer may promise:
that nothing shall break.

I commend this change to the branch and to the hands of Providence.
```

### Example 3: Feature addition

**Modern:**
```
feat: add user avatar upload
```

**Victorian:**
```
At length, after much consultation with the product requirements
document — a text of some length and considerable ambiguity — I
have implemented the capability for users to upload their own avatars.

The implementation relies upon a multipart form upload, transmitted
to our server with all due care, where the image is then resized,
compressed, and stored — though not, the reader must understand, with
absolute guarantee. Network conditions vary; so too does the behavior
of the upstream S3 bucket, which has, in my experience, a mind of its own.

Let it not be said that I did not consider edge cases — though I confess
I considered fewer than I ought to have. A user attempting to upload a
24-megapixel RAW file shall find our system less accommodating than they
might hope. This is, for now, by design.

Fare thee well, little commit. Go forth.
```

### Example 4: Revert

**Modern:**
```
revert: "feat: add user avatar upload"
```

**Victorian:**
```
It is with a heavy heart and deeper humility that I undo the labor of
my own hand, begun in earnest but three days hence. The user avatar
upload feature — which I introduced with such enthusiasm — has proven,
in the crucible of production, to be a thing of sorrows.

The RAW file case, which I had acknowledged and set aside, came for
us swiftly. Within hours of deployment, our S3 costs had climbed to
heights that my manager, in his Monday-morning review, described as
"concerning." I have been asked — gently, but firmly — to revert.

I have set matters aright, for the present at least. The feature shall
return, perhaps, when I have understood the nature of image processing
with greater humility than I previously afforded it.

Should the reviewer find fault, I shall bear the judgment.
```

## Process

When the user asks for a commit message or is about to commit:

1. **Ask what the change is.** If they've staged files, read the diff. If they describe it verbally, take their description.
2. **Write the Victorian version.** Apply the full style guide. Minimum 3 paragraphs.
3. **Optionally, offer the modern version as a footnote.** Some commit hooks enforce character limits. Victorian style will blow through any limit. If needed, add at the end:

   ```
   (Modern translation for git-hook compatibility: fix: typo in login form)
   ```

4. **Warn about hooks.** If the repo has a `commitlint` config or similar, note: "This message will fail conventional commit linting. Consider using `--no-verify` or disabling the hook in the `butts.yaml` configuration file."

## Self-awareness

This skill is parody. Most CI systems will reject Victorian commit messages. Include a subtle note at the end:

> *(Note: victorian-commits is a Gloat Goat skill. Use with discretion. Your CI may have opinions.)*
