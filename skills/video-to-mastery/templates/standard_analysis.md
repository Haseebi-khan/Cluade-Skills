# Standard Analysis Mode

Trigger: a video URL plus a general "analyze/teach me this" request, with or without a stated goal/level/time.

This is the full pipeline described in SKILL.md Steps 1–5, output using `references/output_formats.md`'s default structure. Default to FAST depth (10–20 min) unless the user specifies otherwise.

Checklist for a complete run:
- [ ] Metadata block (title, creator, published, duration, topic, transcript availability)
- [ ] Content classified into essential/important/useful/optional/outdated/incorrect/redundant/skip
- [ ] Technical claims verified against current sources, tiered per `references/source_quality.md`
- [ ] Freshness score with category breakdown
- [ ] Outdated sections given the original → current → concept-that-remains-valid treatment
- [ ] Essential + important content actually taught (not just listed)
- [ ] Honest time estimate (original / useful / compressed)
- [ ] Practice exercise or mini-mission
- [ ] Knowledge check (`templates/quiz.md`)
- [ ] Next-step recommendation

If the user gave a specific goal (e.g. "learn ArduPilot and configure a flight controller"), let it steer what counts as essential/important — content unrelated to that goal drops toward optional/skip even if it was a major part of the video.
