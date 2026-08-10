# Output Format

## Default structure

Use this for standard-mode requests (adapt/trim sections that genuinely don't apply — e.g. skip "Modern Implementation" if nothing needed updating, and say so in one line rather than leaving an empty heading):

```markdown
# 🎥 Video-to-Mastery: <Video Title>

## Video Overview
Title / Creator / Published / Duration / Topic

## Verdict
Freshness score + one-line summary / Difficulty / Educational value

## What the Video Actually Teaches
(brief, in your own words — not a transcript recap)

## What's Still Correct
## What's Outdated
## What's Changed
(original → current → concept that remains valid, per section)

## Current Resources
(links/sources used to verify, tiered per source_quality.md)

## What You Should Skip
(the "skip"/"redundant" buckets, one line each)

## Learn This Instead
### Concept 1 / Concept 2 / Concept 3...
(the essential + important content, taught properly — see teaching_framework.md)

## Modern Implementation
(current commands/code/config)

## Common Mistakes

## Crash Course Time Estimate
(original vs. useful vs. compressed, honestly)

## Practice
(exercises or mini-mission)

## Knowledge Check
(see templates/quiz.md)

## Next Step
```

## Priority tags

When listing concepts, tag them so the learner can triage at a glance:

- **P0 — Must know**: required for understanding or execution
- **P1 — Should know**: important, not blocking
- **P2 — Useful**: helpful later
- **P3 — Optional**: safe to skip
- **OUTDATED**: don't learn as-is; historical context only if relevant

## Metadata block

Always open with a short metadata block so the reader knows what they're getting before committing time:

```text
Title: ...
Creator: ...
Published: ...
Duration: ...
Main topic: ...
Transcript available: yes / metadata-only / unavailable
```

Being upfront about transcript availability sets correct expectations for how granular the analysis can be.
