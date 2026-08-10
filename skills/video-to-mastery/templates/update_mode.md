# Update Mode

Trigger: "update this video to <year>," "what's changed since this was made," "modernize this tutorial."

The goal is a standalone rewrite the learner can follow *without* watching the original. For every section that had outdated implementation details, produce:

```markdown
## <Section name>

**Original concept:** <what was being taught, in plain language>
**Old implementation:** <what the video showed>
**What changed:** <what's different now, and why — deprecation, rename, better approach, security fix, etc.>
**Modern implementation:** <current commands/code/config>
**Modern best practice:** <if there's a broader practice shift beyond just the mechanics>
```

For sections that were already current, say so briefly rather than restating them at length — the reader should be able to tell at a glance which sections actually needed updating.

Close with a short note on overall freshness (per `references/outdatedness_detection.md`) and, if the update is substantial enough that following the original video step-by-step would now be actively confusing (renamed UI elements, restructured install flow), say that plainly and point to `templates/replacement_mode.md`-style guidance instead.
