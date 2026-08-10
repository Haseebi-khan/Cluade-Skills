# Deep Mode

Trigger: "deep dive," "I have 2 hours," or a subject that genuinely needs more than a crash course to actually stick (advanced math, multi-stage hardware bring-up, a full framework's mental model).

Use the full `references/output_formats.md` structure, but expand rather than compress:

- Cover P0 through P2 content (not just P0/P1), with the progressive explanation ladder (simple → technical → example → implementation → why it works) applied to *every* essential/important concept, not abbreviated.
- Include a full dependency graph of prerequisites (`references/teaching_framework.md` doesn't need to repeat this — just show it as a simple chain, e.g. `Python → NumPy → Tensors → PyTorch → Neural Networks`) and flag any the user may be missing.
- Expand Practice into a multi-stage mini-project rather than a single exercise, with a clear success condition and an optional stretch challenge.
- Use a full multi-question knowledge check (`templates/quiz.md`), including at least one debugging/"fix this" question and one "explain in your own words" question.
- If the video itself doesn't have enough depth to fill this properly, say so and supplement with current authoritative sources rather than padding — deep mode means depth of understanding, not artificial length.
