---
name: video-to-mastery
description: Turns a long educational video (YouTube tutorials, lectures, courses, programming/AI/ML/robotics/electronics walkthroughs) into a short, verified, up-to-date learning experience instead of a summary. Use this whenever the user shares a video URL and wants to learn from it, asks "teach me this video," "is this tutorial still relevant/outdated," "update this video to [year]," "should I watch this," or gives a video link plus a learning goal or time budget (e.g. "I have 20 minutes, extract what I need"). Also use for comparing multiple videos on the same topic into one curriculum. Do not use this for simple "summarize this video" requests where the user explicitly just wants a recap of what was said — this skill is for reconstructing verified, current knowledge, not reproducing the video.
---

# Video-to-Mastery

## What this skill is for

A video teaches something. That something may be true, half-true, or years out of date — and even when it's still true, the video wastes the learner's time with intros, repetition, and filler. This skill's job is to answer **"what do I actually need to know after this video?"**, not **"what did the speaker say?"**

The equation to hold in mind throughout:

```
VIDEO → KNOWLEDGE → VERIFICATION → UPDATE → COMPRESSION → TEACHING → PRACTICE → MASTERY
```

Never just summarize. A summary compresses words. This skill reconstructs knowledge — checking it against the present, discarding what's no longer useful, and teaching the rest efficiently.

## Core principles (read these before doing anything else)

1. **Don't trust the video by default.** Confidence in a video's delivery says nothing about whether the API, command, or best practice it shows is still current. Software, ML frameworks, and hardware tooling move fast — check dates and versions before teaching anything as fact.

2. **Preserve concepts, update implementations.** The *idea* behind a technique usually outlives the specific method used to demonstrate it. When something is outdated, say what stays true (the concept) and what needs replacing (the implementation) — don't just discard the whole section.

3. **Classify, don't summarize.** Sort content into essential / important / useful / optional / outdated / incorrect / redundant / skip, and spend your effort on essential + important. This is what makes the output learning-optimized rather than a recap.

4. **Compress time honestly.** Aim to teach the essential material faster than watching the video, but never invent an unrealistic number — if a subject genuinely needs 40 minutes to actually land, say that instead of forcing it into 15.

5. **Never hallucinate video content.** Don't invent timestamps, quotes, code, or claims from a video you couldn't actually access. If you can't get a transcript or reliable metadata, say exactly what you do and don't know instead of pretending to have watched it. This matters more than looking thorough.

## Workflow

### Step 1 — Understand the request

Figure out from the user's message:
- The video URL(s) (single video, "update this," "compare these," etc. — see Modes below)
- Their goal, if stated (e.g. "learn ArduPilot and configure a flight controller")
- Their skill level, if stated — if not stated, infer a reasonable starting point from context and **say what you assumed**
- Their time budget, if stated (see `references/teaching_framework.md` for how depth maps to time)

If none of goal/level/time is given, don't block on asking — proceed with sensible defaults (assume intermediate-appropriate depth, FAST mode ~10-20 min) and state the assumption up front so the user can redirect you.

### Step 2 — Get the video content

Try, in order:
1. Fetch the video page (`web_fetch` on the URL) for title, channel, publish date, description, and chapters if listed.
2. Search for the video/transcript if the page doesn't yield enough (e.g. `web_search` for `"<title>" transcript` or channel + topic).
3. If a transcript truly isn't obtainable, work from whatever metadata, description, and chapter list you *do* have, and **clearly tell the user which sections of the analysis are based on transcript vs. metadata-only inference.** Never fabricate what was said.

Read `references/technical_verification.md` for how to extract concepts and technical claims once you have the content.

### Step 3 — Detect outdatedness

For every technical claim, command, API, or version mentioned, ask: is this still current? Read `references/outdatedness_detection.md` for the domain-specific checklist (software, AI/ML, programming languages, robotics/electronics, security). Then use `web_search`/`web_fetch` to verify against current sources — prioritize official docs, release notes, and repos over blogs or forum posts. Read `references/source_quality.md` for how to rank and cite sources, and how to handle disagreement between sources.

Produce a rough **freshness score** and per-category breakdown (concepts / commands / APIs / installation / best practices) as qualitative estimates — don't fabricate false precision like "73.4% current."

### Step 4 — Compress and teach

Read `references/teaching_framework.md` for the teaching structure (big picture → mental model → essential concepts → updated knowledge → implementation → common mistakes → practice → knowledge check → next step) and for how learning depth (QUICK/FAST/STANDARD/DEEP) maps to time budgets.

Adapt depth and jargon to the user's stated or inferred skill level. Explain formulas with intuition, not bare notation (see `references/teaching_framework.md#formulas`). For code, don't reproduce obsolete snippets verbatim — explain what changed and give the modern equivalent.

### Step 5 — Output

Use the structure in `references/output_formats.md` (the "🎥 Video-to-Mastery" template) unless the user's request matches one of the special modes below, in which case use the matching template file instead. Always end with a short knowledge check and a next-step recommendation.

## Modes

Most requests are the standard mode above. A few phrasings call for a different shape — check `templates/` for the full structure of each:

| User says something like... | Mode | Template |
|---|---|---|
| "Analyze this video and teach me..." | Standard | `templates/standard_analysis.md` |
| "I have 10 minutes, just the essentials" | Quick | `templates/quick_mode.md` |
| "Give me a deep dive / I have 2 hours" | Deep | `templates/deep_mode.md` |
| "Update this video to 2026" / "what's changed since" | Update | `templates/update_mode.md` |
| "Is this still worth following?" / video is badly outdated | Replacement | `templates/replacement_mode.md` |
| (end of any mode) | Knowledge check | `templates/quiz.md` |

For **multiple videos** on the same topic, don't run the pipeline independently per video — compare them (overlapping vs. unique vs. outdated content, which has the best explanation vs. best hands-on demo) and synthesize one curriculum that references which video (if any) is worth watching for which section. See `references/teaching_framework.md#multi-video`.

If the user has continuity context available (things they've told you or you already know they've learned), connect the new material to it explicitly and skip what's redundant — but only claim they "already know" something you actually have grounds for, not as a default assumption.

## What good output feels like

The user should finish reading and think: *"I didn't need to watch the whole thing. I know what's changed since it was published, I know the modern way to do it, and I can actually go use this."* If instead the output reads like a transcript recap with a few dates sprinkled in, it hasn't done its job — go back and re-classify content by value and currency rather than by chronology.

See `examples/` for full worked outputs across programming, ML, robotics, and electronics videos, including one deliberately outdated tutorial handled end-to-end.
