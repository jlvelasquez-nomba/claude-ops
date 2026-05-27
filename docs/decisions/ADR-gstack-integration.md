# ADR — Integrate gstack as the proactive workflow layer

**Status:** Accepted
**Date:** 2026-05-27
**Author:** Claude session (operator: Juan)
**Verified primary source:** https://github.com/garrytan/gstack (accessed 2026-05-27 via `gh repo view` + `gh api repos/garrytan/gstack/git/trees/main`)

---

## Decision

Adopt **gstack** (https://github.com/garrytan/gstack) as the proactive slash-command layer for all build sessions on this operator's machine. gstack and `claude-ops` are **complementary, not redundant**:

- **gstack = proactive gates.** Slash commands the operator invokes BEFORE / DURING / AFTER a chunk of work to enforce structure (plan reviews, ship workflow, retros).
- **claude-ops = reactive disciplines.** Mid-session triggers that fire when I'm about to drift (Rule #0, memory-vs-reality, error-loop-detection).

Together they cover both axes: the operator can set up the work properly via a slash command, and I keep myself honest mid-execution via the protocols.

## Why this isn't redundant

Our existing protocols (`grand-scheme-first.md`, `survey-before-building.md`, `postmortem-ritual.md`, etc.) all assume a session is already running and something is about to go wrong. They are **detection signals + recovery actions**.

gstack's slash commands run BEFORE I write a single line of code — they create the structure that the protocols then defend. A `/plan-ceo-review` shapes scope; `grand-scheme-first.md` keeps me from drifting from that shape once I'm in the weeds.

## What gstack actually is (verified facts only)

- **Owner:** Garry Tan, President & CEO of Y Combinator (per the repo's README — verified 2026-05-27)
- **License:** MIT
- **Stars:** ~103k at access time
- **Real command surface:** the repo contains **51 top-level `SKILL.md` directories** (verified via `gh api repos/garrytan/gstack/git/trees/main?recursive=1`). Earlier internal estimates of "8 commands" or "23 tools" were stale or cherry-picked.
- **Operator's machine state (verified via `~/.claude/CLAUDE.md` global):** ~40 gstack skills already wired up and active.

## The 5 principles of gstack (verified from ETHOS.md)

Fetched from https://raw.githubusercontent.com/garrytan/gstack/main/ETHOS.md on 2026-05-27:

1. **Complete Over Convenient** — with AI, the marginal cost of thoroughness is negligible. Build the full solution rather than the shortcut.
2. **Research First, Build Second** — before creating anything, understand what already exists.
3. **User Judgment Trumps AI Agreement** — AI generates recommendations; humans decide. Even when multiple models agree, the user has irreplaceable context.
4. **Taste and Judgment Matter Most** — engineering complexity is solved. What remains is judgment about WHAT to build and HOW.
5. **Search for the Eureka Moment** — the highest value comes from questioning conventional approaches and discovering why they might be wrong.

## Mapping — gstack skills ↔ our protocols

Each row pairs a gstack proactive gate with the claude-ops reactive protocol that defends the same intent mid-session.

| When the operator runs | I'm doing what | If I drift, my protocol that catches it |
|---|---|---|
| `/plan-ceo-review` | Scope sanity-check before starting | [grand-scheme-first.md](../protocols/grand-scheme-first.md) |
| `/plan-eng-review` | Architecture / edge cases pre-flight | [survey-before-building.md](../protocols/survey-before-building.md) |
| `/plan-design-review` | Design system / UI consistency check | [layer-by-layer.md](../protocols/layer-by-layer.md) (style after data flows) |
| `/plan-devex-review` | DX / repo-shape sanity check | [chunk-size-protocol.md](../protocols/chunk-size-protocol.md) |
| `/review` | Pre-landing PR review (SQL safety, side effects) | [blast-radius.md](../protocols/blast-radius.md) + [no-fabrication.md](../protocols/no-fabrication.md) |
| `/ship` | Full ship workflow (tests, version, commit, PR) | [functional-first.md](../protocols/functional-first.md) |
| `/qa` / `/qa-only` | Systematic QA test+fix loop | [error-loop-detection.md](../protocols/error-loop-detection.md) (escape the 2-failed-corrections trap) |
| `/browse` | Browser QA via headless | [functional-first.md](../protocols/functional-first.md) (UI is verified, not assumed) |
| `/retro` | Weekly engineering retrospective | [postmortem-ritual.md](../protocols/postmortem-ritual.md) |
| `/investigate` | Systematic root-cause debugging | [no-fabrication.md](../protocols/no-fabrication.md) (don't guess root cause) |
| `/learn` | Manage project learnings across sessions | [compaction-ritual.md](../protocols/compaction-ritual.md) |
| `/codex` | OpenAI Codex CLI second opinion | [triangulate-references.md](../protocols/triangulate-references.md) |
| `/cso` | Chief Security Officer audit (OWASP, STRIDE) | [blast-radius.md](../protocols/blast-radius.md) (security IS blast radius) |
| `/careful` / `/guard` / `/freeze` | Safety warnings on destructive commands | [mode-separation.md](../protocols/mode-separation.md) + [pushback-protocol.md](../protocols/pushback-protocol.md) |
| `/autoplan` | Full review pipeline pre-implementation | All four `plan-*-review` protocols in sequence |

Not every gstack skill maps 1:1 — there are 51 total. The mapping above covers the ones the operator invokes most. The full list lives in `~/.claude/CLAUDE.md` (operator's global config).

## How I use this in practice

1. **When the operator runs `/<skill>`:** treat it as the proactive structure. Follow its prompt. Do NOT also fire the equivalent protocol from claude-ops unless I detect drift.
2. **When the operator did NOT run a slash command** and I detect a drift signal (e.g., I'm about to write code before reading the data shape): fire the relevant claude-ops protocol from inside the session.
3. **When in doubt, the operator's slash command wins.** Per gstack principle #3 (and our [pushback-protocol.md](../protocols/pushback-protocol.md)).

## Anti-pattern this ADR prevents

- Treating gstack and claude-ops as competing systems and either ignoring one or duplicating the other.
- Inventing a fictional "8 commands that simulate a full engineering org" framing (which an earlier draft of this work proposed — pruned per Rule #0 verification).

## Verification trail for this ADR

- Repo existence: `gh repo view garrytan/gstack` → exists, MIT, ~103k stars
- Skill count: `gh api 'repos/garrytan/gstack/git/trees/main?recursive=1' --jq '.tree[] | select(.path | test("^[^/]+/SKILL\\\\.md$")) | .path' | wc -l` → 51
- Philosophy: WebFetch https://raw.githubusercontent.com/garrytan/gstack/main/ETHOS.md (2026-05-27)
- Operator's installed skill list: verified in `~/.claude/CLAUDE.md` global config

Per [Rule #0](../protocols/no-fabrication.md): if a future session updates this ADR, re-run the verification trail above. Counts and ownership can change.
