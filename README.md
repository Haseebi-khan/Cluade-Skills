# Claude-skills

A personal collection of [Claude Skills](https://docs.claude.com) — reusable instruction sets that give Claude specialized, repeatable workflows for specific kinds of work.

## What's a skill?

A skill is a folder with a `SKILL.md` file describing when Claude should use it and how. Claude loads a skill's name and description automatically, and pulls in the full instructions only when a task actually matches — so skills stay out of the way until they're needed.

## Skills in this repo

| Skill | What it does |
|---|---|
| [`video-to-mastery`](skills/video-to-mastery/SKILL.md) | Turns a long educational video (YouTube tutorials, lectures, programming/AI-ML/robotics/electronics walkthroughs) into a short, verified, up-to-date learning experience. Checks technical claims against current sources, flags what's outdated, preserves the underlying concept while updating stale implementation details, and teaches the essentials in a fraction of the runtime. |
| [`technical-book-tutor`](skills/technical-book-tutor/SKILL.md) | Deep, plain-language tutoring for technical book excerpts in math, programming, ML, computer vision, CUDA, robotics, drones, and embedded systems. Paste in pages and get intuition → formal definition → formula/algorithm → implementation → edge cases, with worked examples, debugging protocols, and active-recall checks — not a paraphrase of the pages. |
| [`linkedin-post-generator`](skills/linkedin-post-generator/SKILL.md) | Turns the technical concepts just discussed in a chat into a ready-to-post LinkedIn update. Triggered by the command "Create my post" — analyzes the preceding conversation and produces a formatted post (hook, why, scannable how, engagement question), a detailed image-generation prompt, and 2-3 Google Image search queries for real-world diagrams. |

## Structure

```
claude-skills/
├── README.md
├── LICENSE
└── skills/
    ├── video-to-mastery/
    │   └── SKILL.md
    ├── technical-book-tutor/
    │   └── SKILL.md
    └── linkedin-post-generator/
        └── SKILL.md
```

Each skill is self-contained in its own folder. Some skills may grow additional `references/`, `templates/`, or `examples/` subfolders as they're expanded — `SKILL.md` is always the entry point.

## Usage

**Claude.ai / Claude apps:** open a skill's `SKILL.md` (or the packaged `.skill` file, if provided) and use the "Add skill" / "Save skill" option to install it to your profile.

**Claude Code / API:** point Claude at the skill's folder, or copy it into your project's skills directory, so `SKILL.md` is discoverable at the start of a session.

Once installed, a skill triggers automatically when a request matches its description — no need to invoke it by name, though you can (e.g. "use video-to-mastery on this").

## Adding a new skill

1. Create `skills/<skill-name>/SKILL.md` with YAML frontmatter (`name`, `description`) followed by the instructions.
2. Write the description to clearly state both what the skill does and when it should trigger — this is what Claude uses to decide whether to consult it.
3. Add any supporting `references/`, `templates/`, or `examples/` files the skill needs, and link to them from `SKILL.md`.
4. Add a row to the table above.

## License

See [LICENSE](LICENSE).
