# deep-research

A structured deep-research skill for AI agents. Six stages, one hard gate, zero shallow summaries.

Most "research" from AI agents is a single search followed by a summary. This skill enforces a different discipline: confirm scope before spending tokens, build a factual foundation, go deep per item, then — critically — hunt for disagreement before presenting anything.

Works with any agent that supports the [Agent Skills format](https://github.com/anthropics/skills) (SKILL.md with frontmatter): OpenClaw, Claude Code, and OpenAI Codex.

## Why

- **Single-source answers are wrong often enough to matter.** This skill cross-references every fact.
- **Confirmation bias is the default.** Stage 4 forces opposing evidence, mechanistic explanations, and community consensus before any conclusion.
- **Token-heavy research fails when scope is wrong.** Stage 0 is a hard pause: no searching until the user confirms the plan.

## The 6 Stages

| Stage | Name | Gate |
|---|---|---|
| 0 | Confirm Requirements | **Hard stop** — user confirms scope before any searching |
| 1 | Plan | Sub-topics, execution order, definition of done |
| 2 | Factual Foundation | Verified baseline facts, 2+ sources each |
| 3 | Deep Dive Per Item | 3-5 diverse sources per item |
| 4 | Critical & Cross-Cutting Analysis | Criticism, comparisons, counter-arguments |
| 5 | Collate, Present & File | TLDR-first summary + full markdown report |

## Install

**OpenClaw:**
```bash
git clone https://github.com/Zed-Core/deep-research.git
cp -r deep-research ~/.openclaw/workspace/skills/
```

**Claude Code:**
```bash
git clone https://github.com/Zed-Core/deep-research.git
cp -r deep-research ~/.claude/skills/
```

**OpenAI Codex** (global — available in all projects):
```bash
git clone https://github.com/Zed-Core/deep-research.git
cp -r deep-research ~/.codex/skills/
```

Or project-scoped: copy to `.codex/skills/` in the repo root instead. Codex auto-discovers the skill from its description; you can also invoke it explicitly with `$deep-research`.

Or install via ClawHub (listing pending).

## Usage

Ask your agent for real research:

> "Research solid-state battery startups — do a proper analysis, I'm deciding whether to invest time following this space."

Trigger phrases the skill responds to: "research", "deep dive", "look into properly", "do a proper analysis of". The agent will restate scope, propose sub-topics, and wait for your confirmation before searching.

## Repository Structure

```
deep-research/
├── SKILL.md                  # The skill: 6-stage methodology
├── templates/
│   ├── research-plan.md      # Stage 1 plan format
│   └── findings-report.md    # Stage 5 report format
├── examples/
│   └── example-report.md     # Illustrative finished report
├── CHANGELOG.md
└── LICENSE
```

## Design Principles

1. **Never present premature conclusions** — build the full picture first
2. **Seek disagreement** — if all sources agree, look harder
3. **Multiple sources per claim** — single-source "facts" are suspect
4. **Show the methodology** — the user knows what stage the research is at
5. **Evidence trail** — every report cites sources inline and lists them fully

## Roadmap

- [ ] Source-diversity scoring — quantify the Stage 3/4 checklist instead of a manual tick-box
- [ ] Evaluation harness — score agent outputs with/without the skill on factual accuracy
- [ ] Parallel sub-agent deep dives for large item counts
- [ ] Report formats beyond markdown (structured JSON for downstream tooling)

Contributions welcome — open an issue with a concrete failure case you've seen in agent research.

## License

MIT
