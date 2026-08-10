# Teaching Framework

## Standard teaching structure

Once content is classified and verified, teach it in this order (skip a section if it genuinely doesn't apply — don't pad):

1. **Big picture** — the topic in plain language, before any jargon.
2. **Core mental model** — the simplest useful way to think about it.
3. **Essential concepts** — only what matters, explained progressively: simple explanation → technical explanation → example → implementation → why it works.
4. **Updated knowledge** — what changed since the video, using the "original / current / concept that remains valid" structure from `outdatedness_detection.md`.
5. **Practical implementation** — current commands/code/config the learner can actually run.
6. **Common mistakes** — what beginners typically get wrong here.
7. **Practice** — a small, concrete exercise or mini-mission (see below).
8. **Knowledge check** — see `templates/quiz.md`.
9. **Next step** — what to learn next, given what they now know.

## Depth / time-budget modes

| Mode | Time | Use when |
|---|---|---|
| QUICK | 5–10 min | "give me the essentials," very tight time budget |
| FAST (default) | 10–20 min | no depth specified, or a moderate time budget given |
| STANDARD | 20–40 min | user wants real working understanding, not just highlights |
| DEEP | 40–90+ min | "deep dive," "I have 2 hours," genuinely complex material that can't compress further without losing substance |

Default to FAST when nothing is specified. If the user gives an explicit time budget, pick the closest mode and say so ("you gave me 30 minutes, so here's the STANDARD pass"). If the subject genuinely can't be taught well in the requested time, say that plainly rather than force-fitting — e.g. "the video is 90 minutes on backpropagation math; I can get you a solid conceptual grasp in 20, but real fluency with the derivations will take longer than that."

Always state an honest time estimate for what you're delivering, e.g.:

```
Original video: 1h 24m
Useful content: ~48m
Outdated/redundant content: ~22m
Compressed learning time: ~25m
```

Don't claim implausible savings — if the essential material genuinely takes 35 minutes to teach well, don't round it down to sound impressive.

## Formulas

Never dump an equation without intuition. Use:

```
Formula: y = f(x)
Where: x = input, f = transformation, y = output
Intuition: <what this actually means in plain terms, and why it's shaped this way>
```

## Practice / mini-missions

Turn the material into something doable, shaped to the domain:

- **Programming**: 2–3 exercises, basic → intermediate → real-world.
- **Robotics**: theory → simulation → configuration → hardware → test.
- **ML**: concept → dataset → baseline → model → evaluation → experiment.
- **General fallback**: a "mission" with a clear goal, a few concrete steps, and a success condition.

## Multi-video mode {#multi-video}

When comparing multiple videos on one topic, don't process them independently and concatenate the results. Instead:

1. Identify overlap (same ground covered by more than one)
2. Identify what's unique to each
3. Identify which is most outdated
4. Judge which has the best conceptual explanation vs. the best hands-on/practical walkthrough
5. Produce a single curriculum that says, per section, which video (if any) to actually watch — e.g. "Video A → best conceptual explanation; skip to current docs for setup; Video B section 4 → best practical walkthrough; Video C → outdated, skip entirely."

## Learning continuity

If you have real grounds to know what the user already knows (something they've told you, prior context in this conversation), connect the new material to it and skip what's redundant. Don't assume prior knowledge you don't actually have evidence for — that produces confusing gaps, not efficiency.
