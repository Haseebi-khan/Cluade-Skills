# Example: Programming Tutorial

**Input:**
> Analyze this video: https://www.youtube.com/watch?v=EXAMPLE1 — "Async Python for Beginners" (2020). I'm a beginner. Teach me the important parts in under 20 minutes.

**Abbreviated output shape:**

```markdown
# 🎥 Video-to-Mastery: Async Python for Beginners

Title: Async Python for Beginners | Creator: <channel> | Published: 2020 | Duration: 38m
Transcript available: yes

## Verdict
Freshness: ~65/100 — the async/await mental model is timeless; a couple of library
recommendations and one syntax pattern are outdated.
Difficulty: Beginner-friendly | Educational value: High for the core concept

## What's Still Correct
The event-loop mental model, `async def` / `await` syntax, and the coroutine vs.
function distinction are all still exactly as shown.

## What's Outdated
Original video: manually creates and manages the event loop with
`loop = asyncio.get_event_loop(); loop.run_until_complete(...)`
Current approach: `asyncio.run(main())` handles loop creation/teardown for you
in modern Python.
Concept that remains valid: you still need one coroutine as your entry point
that awaits everything else — only the boilerplate around it changed.

## Learn This Instead
### P0 — The event loop model
(taught properly: simple explanation → example → why it works)
### P0 — async/await syntax
### P1 — Common async libraries (httpx over the video's now-unmaintained aiohttp
alternative shown at 14:20 — noting the library recommendation, not the syntax,
is what changed)

## Modern Implementation
```python
import asyncio

async def fetch_all(urls):
    ...

asyncio.run(fetch_all(urls))
```

## Common Mistakes
Awaiting inside a loop instead of gathering concurrently; forgetting a function
that calls `await` must itself be `async def`.

## Crash Course Time Estimate
Original: 38m | Useful: ~24m | Compressed: ~15m

## Practice
Exercise 1 (basic): write one async function that sleeps and returns a value.
Exercise 2 (intermediate): fetch 3 URLs concurrently with `asyncio.gather`.

## Knowledge Check
1. Why can't you `await` inside a regular `def` function?
2. This code uses `loop.run_until_complete` — what's the modern equivalent?
3. Explain what "concurrent, not parallel" means for asyncio, in your own words.

## Next Step
Once comfortable here, structured concurrency (`asyncio.TaskGroup`, Python 3.11+)
is the natural next topic — the video predates it entirely.
```

This example demonstrates: honest freshness scoring for a mostly-current video, the original/current/concept-that-remains-valid pattern for one outdated detail without treating the whole video as obsolete, and compressing 38 minutes to 15 without losing the core model.
