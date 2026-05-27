# State — claude-ops

**Last updated:** 2026-05-27 by Claude session (Juan)
**Repo status:** Bootstrap COMPLETE. Rule #0 reframed as active gatekeeper. 4 devs + 1 company + 2 primary-sources verified to Canonical via WebFetch. Playbook entries written for the 4 verified devs.

## 🟢 Complete (in main)

- `README.md`, `CLAUDE.md`
- `docs/foundational-brief.md`, `docs/decisions.md` (3 ADRs), `docs/glossary.md`, `docs/architecture.md`, `docs/state.md`
- `protocols/README.md` (index 15/15 ACTIVE)
- **15 protocols ACTIVE** (all full content, Rule #0 format):
  - `no-fabrication.md` (Rule #0 — refactored 2026-05-26 to active gatekeeper stance)
  - `error-loop-detection.md`, `memory-vs-reality.md`, `survey-before-building.md`
  - `postmortem-ritual.md`, `blast-radius.md`
  - `pushback-protocol.md`, `compaction-ritual.md`, `mode-separation.md`
  - `chunk-size-protocol.md`, `grand-scheme-first.md`
  - `triangulate-references.md`, `layer-by-layer.md`, `functional-first.md`, `realistic-ambitious.md`

- `playbooks/pro-dev-references.md` — **4 canonical** (Vitalik, Julia Evans, Simon Willison, Mitchell Hashimoto) + operator Mag7/Tesla/xAI list pending
- `references/README.md` — active template
- `references/developers-canonical.md` — **4 canonical** (Vitalik, Julia Evans, Simon Willison, Mitchell Hashimoto) + 11 TODO
- `references/companies-canonical.md` — **1 canonical** (Anthropic) + 11 TODO
- `references/primary-sources.md` — **2 canonical** (SRE Book Ch.15, HN thread 48090029) + 2 TODO

## 🟡 Active TODO list (work to do via WebFetch verification, NOT permanently empty)

Per Rule #0 active framing: these are work-items, not "Rule #0 forbids it" excuses.

- **developers-canonical.md TODO:** 11 candidates with explicit "Next verification step" each (Linus, Wozniak, Abramov, Rich Harris, Rauch, DHH, Karpathy, Carmack, antirez, Cassidoo, patio11)
- **companies-canonical.md TODO:** 11 candidates (OpenAI, SRE org, Stripe, Cloudflare, Vercel, Supabase, Netflix, Shopify, GitHub, HashiCorp, Discord)
- **primary-sources.md TODO:** 2 known citations (foundational-brief link, RSP doc)
- **playbooks/pro-dev-references.md TODO:** operator-specified Mag7/Tesla/xAI list (~7 candidates, names pending from Juan) + deeper quote-level fetches for the 4 already-canonical devs

Each session that touches references aims to convert 2-3 TODO → Canonical via WebFetch.

## ✅ Recently shipped (last 24h, full chronology)

- 2026-05-26 (1) — Bootstrap commit: README + CLAUDE.md + foundational-brief + docs + Rule #0 first version
- 2026-05-26 (2) — 14 protocol stubs + 1 playbook stub + 3 reference stubs
- 2026-05-26 (3) — Chunk A: 5 high-priority protocols full content
- 2026-05-26 (4) — Chunk B: 5 medium-priority protocols full content
- 2026-05-26 (5) — Chunk C: 4 remaining protocols full content (15/15 ACTIVE)
- 2026-05-26 (6) — Final: index + state + reference templates
- 2026-05-26 (7) — **REFACTOR Rule #0**: gatekeeper-not-excuse framing (operator feedback)
- 2026-05-26 (8) — **First batch verifications**: 4 devs + 1 company + 2 primary-sources via WebFetch
- 2026-05-27 (9) — Housekeeping + playbook canonical entries for the 4 verified devs (this session)

## 🔄 Pre-flight (every session using this repo)

```
1. cat protocols/no-fabrication.md     # Rule #0 (active gatekeeper)
2. cat docs/state.md                   # this file
3. cat docs/foundational-brief.md      # first time loading
4. When a Tier 2 trigger fires, load that protocol.
```

## 🚨 Risks / debt

- **Operator confirmed pasting claude-ops pointer in ~/.claude/CLAUDE.md global (2026-05-26).** Without this, repo doesn't change behavior.
- **TODO entries are real work, not "fine to leave empty."** Per Rule #0 active framing, each session aims to convert 2-3 TODO → Canonical.

## 📝 Session log

- **2026-05-26 (1-8)** — see "Recently shipped" above. Major reframe at (7) corrected Rule #0 from passive avoidance to active verification stance. First proof-of-active-stance at (8): 7 canonical entries via WebFetch.
- **2026-05-27 (9)** — Housekeeping: bumped layer-by-layer stub count to reality (15). Promoted Vitalik / Julia / Simon / Mitchell from playbook-TODO to playbook-Canonical with verified-source-backed WHEN/THEN patterns. Per operator: "como aceite a un coche" — entries kept lean, one actionable pattern each.
