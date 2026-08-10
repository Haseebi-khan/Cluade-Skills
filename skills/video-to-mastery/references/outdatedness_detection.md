# Outdatedness Detection

Confidence in delivery is not evidence of currency. A video can be popular, well-produced, and wrong about what's current today. Check deliberately rather than trusting tone.

## What to check, by domain

**Software (general)**: version numbers, deprecated/removed APIs, changed CLI syntax or subcommands, changed install/package-manager flow, changed default config, changed UI (if it's a GUI walkthrough), architecture changes (e.g. a tool that's since been rewritten or replaced).

**AI / ML**: framework versions (PyTorch, TensorFlow, JAX), API surfaces (Hugging Face `transformers`, OpenAI/Anthropic SDKs — these change often), CUDA/cuDNN compatibility, whether the model architecture shown is still a reasonable choice or has been superseded, whether the training practice shown (e.g. specific optimizer defaults, LR schedules) is still standard.

**Programming languages**: language version and syntax changes, package manager conventions (pip vs. uv, npm vs. pnpm/bun, etc.), library API changes, compiler/toolchain changes.

**Robotics / electronics**: firmware versions (ArduPilot, PX4), board support (STM32, ESP32 toolchains), sensor/protocol availability, whether specific hardware revisions are still sold, configuration software (Mission Planner, QGroundControl, etc.) UI or workflow changes.

**Security-adjacent content**: be extra careful here — authentication flows, cryptography choices, dependency installation practices (curl-pipe-to-shell, unpinned versions), permissions/secrets handling, and deployment practices age fast and the cost of teaching an outdated *insecure* practice is higher than teaching an outdated but harmless one. Flag these clearly even if you're not fully certain, and point to current guidance.

## How to check

Search for the specific tool/library/API by name plus "current version" or "changelog" or "deprecated," and prefer official sources (see `source_quality.md`). If the video names a specific version, compare it directly against the latest stable release. If it doesn't name a version, try to infer it from the publish date and what was current then.

## Concept vs. implementation

Almost everything that goes outdated splits into two parts:
- **The concept** — the underlying idea, architecture, or principle. This usually survives.
- **The implementation** — the specific method, API call, or command shown. This is what breaks.

When you find something outdated, say both parts explicitly:

```
Original video: <method Y>
Current approach: <method Z>
Concept that remains valid: <the underlying idea>
```

This lets the learner keep the mental model while dropping the stale mechanics — much more useful than either "this is all outdated, skip it" or silently teaching stale commands.

Some old material is still worth teaching *as-is* because the concept is timeless even if a peripheral detail changed — don't reflexively downgrade a video just because it's a few years old. Judge each section on its own merits.

## Freshness score

Give a qualitative 0–100 estimate with a short breakdown by category (concepts / commands / APIs / installation / best practices), e.g.:

```
Freshness Score: ~40/100

Concepts:        mostly current
Commands:        largely outdated
APIs:             outdated
Installation:     outdated
Best practices:   partially current
```

Treat the number as a rough signal for the reader, not a measurement — don't render it with false precision like "42.7/100," and don't score sections you couldn't actually verify (say "not verified" instead of guessing a number for them).
