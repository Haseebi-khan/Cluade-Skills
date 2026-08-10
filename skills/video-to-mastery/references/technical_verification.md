# Technical Verification & Extraction

## Getting the video's actual content

Before extracting anything, be honest with yourself about what you actually have access to:

- **Full transcript available** (via page fetch, captions, or a transcript site): you can extract concepts, claims, and even approximate timestamps/quotes at the level of paraphrase (never verbatim long quotes — keep normal copyright discipline).
- **Metadata + chapters only** (title, description, chapter list, no transcript): you can reason about structure and likely content from chapter titles and description, but say explicitly that specific claims inside a chapter are inferred, not confirmed, and lean on web research about the topic itself rather than claiming to know what the presenter said.
- **Almost nothing available** (page won't fetch, no useful description): say so plainly, offer to proceed using general knowledge of the topic plus current research instead of the video's specific content, and let the user decide if that's still useful.

Never bridge a gap in what you know with an invented timestamp, quote, command, or demo. "I could not verify this section from the available content" is a completely fine sentence to write.

## Metadata to pull

Title, channel/creator, publish date, duration, description, chapter list, any linked resources (GitHub repos, docs, slides), and every technology/version explicitly named. If publish date isn't visible on the page, search for it — "how old is this" changes everything downstream about outdatedness handling.

## Concept extraction

For each chapter/section, extract:
- What is actually being taught (concept, not just topic label)
- Concrete artifacts: commands, code, formulas, configuration values, tool names, version numbers
- The claims implicit in "this is how you do X" — these are the things to verify

## Classifying content

Sort every section/claim into one bucket — this replaces "summarize everything":

- **Essential** — can't understand or execute the topic without it
- **Important** — meaningfully improves understanding or results
- **Useful** — nice to know, not blocking
- **Optional** — safe to skip for most learners
- **Outdated** — was correct, isn't anymore
- **Incorrect** — wrong even at time of publishing, or a bad practice
- **Redundant** — repeats something already covered
- **Skip** — filler: intros, sponsor reads, tangents, re-explaining the same point three times

Spend your teaching effort on essential + important. Everything else gets at most a one-line mention (what it was, why it's being skipped).

## Verifying technical claims

For each essential/important claim tied to a specific tool, API, command, or practice:

1. Search for the current official documentation or repository.
2. Check whether the specific thing shown (function signature, CLI flag, package name, config key) still exists as shown.
3. If it changed, capture both what changed and why (deprecation, renamed, replaced by a better approach, security concern, etc.) — the "why" is often what makes the update memorable.
4. If you can't find a confident current answer, say so rather than guessing. "I couldn't verify whether this API is still current — check the official docs before relying on this" is honest and still useful.

## Code specifically

Don't reproduce old code just because the video showed it. Instead: understand what the code was trying to accomplish, check whether the APIs/libraries it uses are current, and if not, show the modern equivalent with a short note on what changed and why. If the code is still current, say so — don't manufacture an update where none is needed.
