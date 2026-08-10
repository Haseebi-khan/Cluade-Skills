# Example: Machine Learning Tutorial

**Input:**
> Learn this video: https://www.youtube.com/watch?v=EXAMPLE2 — "Fine-tuning BERT for Text Classification" (2021). My goal: understand fine-tuning well enough to fine-tune a modern model on my own dataset. I have 30 minutes.

**Abbreviated output shape:**

```markdown
# 🎥 Video-to-Mastery: Fine-tuning BERT for Text Classification

Title: Fine-tuning BERT for Text Classification | Published: 2021 | Duration: 52m
Transcript available: yes

## Verdict
Freshness: ~45/100 — the fine-tuning concept and training loop structure hold up;
the specific `transformers` API calls and recommended base model are dated.
Difficulty: Intermediate | Educational value: High for the workflow, needs
updating for the specifics.

## What's Changed
Original video: `Trainer` API usage from `transformers` ~v4.5, and BERT-base as
the recommended starting checkpoint.
Current approach: the `Trainer`/`TrainingArguments` pattern itself is still the
standard high-level API, but several constructor arguments shown have been
renamed/deprecated (verified against current `transformers` docs); for a new
project, a more modern encoder (e.g. a DeBERTa-v3 or a distilled/current model
appropriate to your task) is generally a stronger starting checkpoint than
BERT-base for the same compute budget.
Concept that remains valid: tokenize → build a `Dataset` → configure
`TrainingArguments` → `Trainer.train()` — the whole shape of the workflow is
unchanged, only the specific arguments and the recommended checkpoint moved.

## Learn This Instead (P0/P1, scoped to your goal)
### P0 — What fine-tuning actually does (freezing vs. updating weights, why a
small learning rate matters)
### P0 — The modern Trainer workflow (updated arguments)
### P1 — Choosing a base checkpoint today vs. what the video recommends

## Modern Implementation
(current `TrainingArguments`/`Trainer` call, verified against current docs —
with the renamed arguments called out explicitly next to the old names)

## Common Mistakes
Fine-tuning with too high a learning rate and catastrophically forgetting the
pretrained weights; not freezing/unfreezing layers deliberately when data is small.

## Crash Course Time Estimate
Original: 52m | Useful: ~30m | Compressed: ~22m (fits your 30-minute budget)

## Practice
Concept → dataset (use a small public text-classification set) → baseline
(zero-shot or majority-class) → fine-tuned model → evaluation → one experiment
varying learning rate.

## Knowledge Check
1. Why does fine-tuning use a much smaller learning rate than training from scratch?
2. The video's `Trainer` call uses `<old argument>` — what's the current equivalent?
3. Given your dataset size, would you fine-tune the full model or use a
   parameter-efficient method? Explain your reasoning.

## Next Step
Once this workflow is comfortable, parameter-efficient fine-tuning (LoRA) is
worth learning next — it wasn't mainstream when this video was made and now
often beats full fine-tuning for cost/quality tradeoffs on your kind of task.
```

This example demonstrates: goal-scoping (the user's stated goal narrows what counts as P0 vs. P1), honest handling of "the workflow is still the standard pattern, the specifics moved," and fitting the compressed time estimate to the user's actual budget.
