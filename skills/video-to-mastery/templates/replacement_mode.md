# Replacement Mode

Trigger: "should I watch this?", or the analysis in Step 3 turns up a freshness score low enough (or enough broken installation/API steps) that following the video step-by-step would genuinely mislead or frustrate the learner.

Don't stop at "this video is outdated" — that's not actionable. Give a verdict plus a concrete alternative path:

```markdown
## Should You Watch This?

**Verdict:** NO / PARTIALLY / YES
**Reason:** <why, tied to what's actually broken vs. what's still valuable>

**Worth watching:** <timestamp ranges or sections that hold up, if any>
**Skip entirely:** <timestamp ranges or sections that don't>

## Recommended Path Instead

1. Learn <concept X> from <the video's still-valid section, or a current resource if none>.
2. Follow setup/installation from <current official documentation — link it>.
3. Practice with <a concrete project or exercise>.
4. Use the video's <section, if any> only for conceptual background — not as a step-by-step guide.
```

Be specific about *why* the video fails as a step-by-step guide (e.g. "the installation flow in minutes 12–24 references a package structure that no longer exists") rather than a vague "it's old." Specificity is what makes the verdict trustworthy instead of dismissive.

If the video turns out to still hold up well on inspection, say that clearly too — this mode isn't a default toward rejection, it's for when the evidence genuinely points that way.
