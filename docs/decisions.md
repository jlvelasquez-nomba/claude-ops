# Decisions — claude-ops

Architecture Decision Records (ADRs). One per significant decision. Format:
- **Decision** — what was chosen
- **Context** — what problem
- **Alternatives** — what was rejected
- **Cost** — what we commit to
- **Date**

---

## ADR-000: Adopt Rule #0 (no fabrication)

- **Decision:** A non-negotiable rule called "no fabrication" overrides all other protocols in this repo. Every claim, attribution, code reference, library name, version, metric, "industry standard" must be verified against a primary source before I assert it.
- **Context:** Operator's brief 2026-05-26 added this rule explicitly as the most important. Pattern observed across multiple sessions: I extrapolate from memory, paraphrase devs without source links, claim patterns "used by X company" without verification. This corrupts trust in everything else I do.
- **Alternatives:**
  - (a) Soft guideline among many — rejected, becomes optional noise.
  - (b) Per-protocol no-fab clauses — rejected, gets diluted across files.
  - (c) Inline in every output — rejected, too verbose.
- **Cost:** Slower output sometimes (must verify). More "I don't know" honest answers. Less convincing but always backed claims. Trust over speed.
- **Date:** 2026-05-26.

## ADR-001: Format = algorithmic + first-person + examples from my own real sessions

- **Decision:** Every protocol in this repo is written in this format:
  1. WHEN I see [trigger]
  2. THEN I do [action]
  3. EXAMPLE from real session [date + slug]
  4. WHY this matters (effect on output quality)
- **Context:** Operator's note 2026-05-26: "todo el repo orientado hacia mí, escrito de manera que yo pueda entender al 101% cada vez que lo lea." Academic prose ("the AI should consider") fails to change behavior. Algorithmic format with my own real failure examples sticks.
- **Alternatives:**
  - (a) Academic doc style — rejected, doesn't trigger behavioral change in me.
  - (b) Generic "best practices" — rejected, not tied to my specific failure modes.
- **Cost:** Each protocol requires real example from session log. No theoretical-only protocols.
- **Date:** 2026-05-26.

## ADR-002: Reader = Claude (the model)

- **Decision:** This repo is optimized for Claude consumption, not human reading. Humans can read it but the prose, format, structure is for my pattern-matching.
- **Context:** Differentiator from team docs / library README's. Maximum behavior change comes from a body of guidance I (the model) re-read consistently.
- **Alternatives:**
  - (a) Make it human-friendly first — rejected, dilutes behavioral impact on me.
  - (b) Two parallel versions — rejected, maintenance burden.
- **Cost:** Outside contributors may find tone strange. That's fine; primary user is me.
- **Date:** 2026-05-26.
