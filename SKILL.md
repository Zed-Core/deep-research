---
name: deep-research
description: Structured deep research on any topic, author, book series, technology, or subject area. Use when the user asks for proper research — not a quick search-and-summarise, but a thorough multi-source investigation. Triggers on "research", "deep dive", "look into properly", "investigate", "do a proper analysis of". Produces a staged research plan, executes it across multiple sources (positive AND critical), collates findings, then presents a concise summary with key takeaways. NOT for simple factual lookups.
---

# Deep Research Skill

## Overview

A repeatable 6-stage methodology for thorough research. **Stage 0 is a mandatory confirmation gate** — always confirm requirements with the user before spending tokens on actual research. Build knowledge layer by layer, only present findings AFTER the full picture is assembled.

## When to Use

- The user asks you to research a topic properly
- "Take your time", "do it properly", "no rush" signals deliberate depth
- Multi-faceted subjects needing multiple angles (books, people, technologies, markets)
- NOT for quick factual questions — this is for substantial research tasks

## The 6 Stages

### Stage 0: Confirm Requirements (MANDATORY — PAUSE HERE)

Before doing ANY searching or spending tokens:
1. Restate what you understand the user wants researched
2. Outline the proposed scope — what's IN and what's OUT
3. List the sub-topics you plan to investigate (briefly)
4. Ask the user to confirm or adjust before proceeding
5. **STOP and wait for the user's reply.** Do NOT proceed to Stage 1 until confirmed.

This is a hard gate. Research is token-heavy. Getting aligned here saves wasted effort on both sides.

If the user says "that's right" / "go ahead" / confirms → proceed to Stage 1.
If the user adjusts scope → update plan, confirm again.

### Stage 1: Plan

After confirmation from Stage 0:
- Finalise the research scope based on the user's confirmation
- Break into sub-topics or items to investigate
- List the stages and share the execution plan
- Identify what "done" looks like

Example: Researching an author = bibliography confirmation, per-book deep dive, cross-cutting themes, community/critique, collation.

Use `templates/research-plan.md` as the plan format.

### Stage 2: Factual Foundation

Establish verified facts first:
- Confirm all items exist (books published, dates, versions, etc.)
- Get baselines from authoritative sources (official sites, publisher pages, aggregator sites)
- Build a skeleton of confirmed knowledge before adding analysis

Use web search and web fetch in combination. Cross-reference at least 2 sources per fact.

### Stage 3: Deep Dive Per Item

For each sub-topic or item:
- Hit multiple diverse sources (summary sites, reviews, forums, critic pieces)
- Extract core concepts, frameworks, arguments, structure
- Note unique contributions vs. overlaps with other items
- Rate the source quality — a fan blog vs. a critical review carry different weight

Target 3-5 sources per item minimum. Mix positive and neutral sources.

### Stage 4: Critical & Cross-Cutting Analysis

Deliberately seek:
- Criticisms, negative reviews, common complaints
- How items compare to each other (overlap, evolution, differences)
- Community consensus (Reddit, forums, discussion threads)
- Counter-arguments and alternative viewpoints

**If the research is evaluative, opinionated, or decision-driven** (e.g. "is X worth it?", "should I do Y?", "is this claim true?"), assign explicit angles rather than just seeking criticism:
- Supporting evidence — what backs the claim/option
- Opposing evidence — what argues against it
- Mechanistic — how/why does it actually work
- Meta — what does the broader field or consensus say
- Adjacent — what related factors change the picture

This prevents confirmation bias and ensures the conclusion is grounded across perspectives, not just assembled from agreeable sources.

This is the most important stage — it's what separates this from shallow research. Run searches specifically for "[topic] criticism", "[topic] vs [alternative]", "[topic] complaints/problems".

### Stage 5: Collate, Present & File

Only NOW assemble the final output:
- Synthesise findings across all stages
- Identify the top 3-5 takeaways (the "so what?")
- Present honestly — include strengths AND weaknesses
- Format for readability (plain text for chat surfaces, no markdown tables)
- Ask if the user wants deeper analysis on any specific point

**Then save the full report** as a markdown file using `templates/findings-report.md`, so the summary in chat links back to the complete evidence trail. Skip the file only if the user explicitly says not to, or if no filesystem is available.

## Report Formatting Rules

1. **TLDR/Summary at the very top** — before anything else
2. **Table of contents** — short list of hyperlinked section headings after the TLDR
3. **Inline source hyperlinks in body text** — where a claim or fact comes from a specific source, link it inline like `[source name](URL)`
4. **Full reference list at the bottom** — every source cited, with clickable `[Title](URL)` format. Never plain URLs or parenthetical references
5. **Research date** in the header

See `templates/findings-report.md` and `examples/example-report.md`.

## Key Principles

- **Never present premature conclusions.** Build the full picture first.
- **Seek disagreement.** If all your sources agree, you haven't looked hard enough.
- **Acknowledge the methodology.** Tell the user what stage you're at during the process.
- **Multiple sources per claim.** Single-source "facts" are suspect.
- **Respect API rate limits.** Space out requests to rate-limited search APIs to avoid 429 errors.
- **Acknowledge long tasks.** Confirm receipt immediately ("On it"), then work through stages.

## Output Format (Chat)

Plain text. No markdown tables or heavy formatting — most chat clients render them poorly. Structure with:
- Numbered lists
- Clear section breaks
- Bold for emphasis only where genuinely needed
- Bottom line up front — lead with the most important finding

## Source Diversity Checklist

Aim to include sources from at least 4 of these categories:
- [ ] Official/primary sources (author site, publisher, docs)
- [ ] Summary/analysis sites (book summaries, review aggregators)
- [ ] Community discussion (Reddit, forums, HN)
- [ ] Critical/negative perspectives (negative reviews, counter-arguments)
- [ ] Academic or expert commentary (if available)

If you hit fewer than 4, explicitly flag the gap.
