# Video-to-Mastery

Turn long educational videos into short, verified, up-to-date learning experiences — not summaries.

## The problem

Video tutorials age. A confident, well-produced walkthrough from 2021 can still be teaching a deprecated API, a superseded library, or a UI that no longer exists — and nothing about how the video *sounds* tells you that. Meanwhile, even a current, accurate video wastes your time with intros, repetition, and filler you don't need.

## What this skill does

Give it a video URL (plus, optionally, your goal, skill level, and time budget) and it will:

1. Identify what the video actually teaches
2. Classify every section by value (essential → skip) and currency (current → outdated → incorrect)
3. Verify technical claims against current official sources
4. Show what changed — preserving the underlying concept while updating the stale implementation
5. Teach the essential material directly, in a fraction of the video's runtime
6. Give you practice exercises and a knowledge check
7. Recommend what to learn next

The target feeling afterward: *"I didn't need to watch the whole thing. I know what's changed since it was made, I know the modern way to do it, and I can actually use this."*

## How it works

```
VIDEO → KNOWLEDGE → VERIFICATION → UPDATE → COMPRESSION → TEACHING → PRACTICE → MASTERY
```

The skill fetches whatever video content and metadata it can access, extracts concepts and technical claims, checks them against current documentation and sources, and reconstructs a taught lesson rather than a transcript recap. When it can't verify or can't access something, it says so directly instead of guessing — see `SKILL.md`'s core principles for the hallucination-prevention rules this is built around.

## Usage

Just share a video link with what you want:

```
Analyze this video: https://www.youtube.com/watch?v=XXXXXXXX
Teach me this as quickly as possible.
```

```
Analyze this video and teach me the important parts.
My goal: learn ArduPilot and configure a flight controller.
My current level: beginner.
Time available: 30 minutes.
```

```
Is this tutorial still relevant?
Update this tutorial to 2026.
I have 20 minutes, extract only what I need.
Compare these three videos on the same topic.
```

## Output

A structured lesson: video overview, freshness verdict, what's still correct / outdated / changed, current sources, the essential concepts actually taught (with formulas explained, code modernized where needed), common mistakes, a practice exercise, a short knowledge check, and a next-step recommendation. See `references/output_formats.md` for the full template and `examples/` for worked outputs across programming, ML, robotics, and electronics.

## Supported video types

Anything with fetchable metadata or a transcript — YouTube tutorials, lectures, conference talks, and course videos work best. Programming, AI/ML, robotics, electronics, and general technical/engineering content are all supported domains (see `references/outdatedness_detection.md` for domain-specific checks).

## Update detection

The skill doesn't just flag "this is old" — it checks specific claims (versions, APIs, commands, UI flows) against current sources and, when something's changed, explains what changed and why, while explicitly preserving whatever underlying concept is still valid. See `references/outdatedness_detection.md` and `references/technical_verification.md`.

## Learning modes

| Mode | When |
|---|---|
| Standard | default — full pipeline, FAST depth unless stated otherwise |
| Quick | tight time budgets — essentials only |
| Deep | thorough sessions — full depth, multi-stage practice |
| Update | rewriting an outdated video into a current, standalone version |
| Replacement | the video is outdated enough that a different path is genuinely better |

See `templates/` for the exact structure of each.

## Architecture

```
video-to-mastery/
├── SKILL.md                        Main workflow and pipeline
├── README.md                       This file
├── references/
│   ├── technical_verification.md   Extracting and verifying content from a video
│   ├── outdatedness_detection.md   Domain checklists + freshness scoring
│   ├── source_quality.md           Source tiering and citation practice
│   ├── teaching_framework.md       Teaching structure, time-budget modes, formulas
│   └── output_formats.md           Default output template, priority tags
├── templates/
│   ├── standard_analysis.md
│   ├── quick_mode.md
│   ├── deep_mode.md
│   ├── update_mode.md
│   ├── replacement_mode.md
│   └── quiz.md
└── examples/
    ├── programming_video.md
    ├── machine_learning_video.md
    ├── robotics_video.md
    └── electronics_video.md
```

`SKILL.md` stays focused on the workflow itself; the domain-specific and mode-specific detail lives in `references/` and `templates/` so it's only loaded when relevant.

## Repository structure

Progressive disclosure: the skill's name and description are always visible to Claude; `SKILL.md`'s body loads when the skill triggers; everything in `references/`, `templates/`, and `examples/` loads on demand as the workflow calls for it.

## Limitations

- Depends on being able to fetch video metadata/transcript from the page or find it via search — some videos won't have an accessible transcript, in which case the analysis is explicitly scoped to metadata-only and says so.
- Freshness scoring is a qualitative estimate, not a measurement — treat it as a signal, not a precise metric.
- Web research quality depends on what's findable; for very niche or very new tools, current authoritative sources may be thin, and the skill will say when it can't verify something confidently rather than guessing.

## Accuracy philosophy

Two failure modes matter more than looking thorough: inventing video content that wasn't actually available (timestamps, quotes, code, claims), and presenting an unverified guess as a confirmed fact. The skill is built to prefer an honest "I couldn't verify this" over either. See `SKILL.md`'s core principles and `references/technical_verification.md`.

## Future improvements

Video providers beyond YouTube with richer transcript access, and a way to carry structured "what the learner already knows" context across multiple video sessions for better continuity.
