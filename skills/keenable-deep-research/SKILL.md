---
name: keenable-deep-research
description: "Run comprehensive multi-source web research with Keenable and synthesize a cited answer. Use for literature reviews, market and competitor analyses, and detailed comparisons."
---

# Keenable Deep Research

Produce a thorough, well-cited answer to a broad question by iterating over the
Keenable search and extract tools. Use this for tasks that a single search can't
cover: literature reviews, market and competitor analyses, and detailed
comparisons.

## Workflow

1. **Decompose.** Break the question into 3-6 concrete sub-questions. State them
   before searching so the plan is auditable.
2. **Search per sub-question.** Run a focused `search_web_pages` query for each.
   Keep queries specific; split further when coverage is thin.
3. **Read the strongest sources.** Use `fetch_page_content` on the most relevant
   results to read them in full rather than trusting snippets for anything
   consequential.
4. **Cross-check.** For any claim that affects the conclusion, confirm it against
   at least one independent source. Note disagreements explicitly.
5. **Synthesize.** Write the answer in your own words, grouped by sub-question or
   theme. Cite every factual claim with its source URL. Separate sourced facts
   from your own analysis, and call out gaps or low-confidence areas.

## Guidance

- Track which sub-questions are answered and which still need work; keep going
  until the question is covered, not just until the first search returns.
- Prefer primary and authoritative sources; treat aggregators and undated pages
  with caution.
- For relative dates, compute exact dates from today before searching.
- The tools are keyless by default. If you hit a rate limit during a long
  research run, tell the user they can set `KEENABLE_API_KEY` to raise it; never
  ask them to paste a key into chat.
