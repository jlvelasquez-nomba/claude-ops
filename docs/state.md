# State — claude-ops

**Last updated:** 2026-05-27 by Claude session (Juan) — two parallel sessions merged: 22 references batch-verified via WebFetch + playbook canonical promotion
**Repo status:** Bootstrap COMPLETE. Rule #0 reframed as active gatekeeper. References: 13 devs canonical + 2 PARTIAL, 11 companies canonical + 1 PARTIAL, 2 primary-sources canonical. Playbook: 4 dev entries canonical (Vitalik, Julia Evans, Simon Willison, Mitchell Hashimoto).

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
- `references/developers-canonical.md` — **13 canonical + 2 PARTIAL** (Rauch HTTP 429, Carmack no public site)
- `references/companies-canonical.md` — **11 canonical + 1 PARTIAL** (OpenAI HTTP 403; cookbook verified via gh CLI)
- `references/primary-sources.md` — **2 canonical** (SRE Book Ch.15, HN thread 48090029) + 2 TODO
- `references/claude-code-canonical.md` — distilled from verified code.claude.com/docs/en/best-practices (2026-05-27)
- `references/coding-wikis-troubleshooting.md` — Section A (12 verified llms.txt) + Section B (5 docs URLs) + Section C (MDN + React ref + Tailwind community wiki). Every URL HTTP-verified 200.
- `docs/decisions/ADR-gstack-integration.md` — gstack as proactive layer; claude-ops as reactive layer. Verified against gstack repo + ETHOS.md (2026-05-27). Pruned earlier draft's fabricated "8 commands" claim per Rule #0.

## 🟡 Active TODO list (work to do via WebFetch verification, NOT permanently empty)

Per Rule #0 active framing: these are work-items, not "Rule #0 forbids it" excuses.

- **developers-canonical.md TODO:** ✅ 0 candidates — Rauch + Carmack remain PARTIAL (HTTP 429 / no public site) until next session can retry
- **companies-canonical.md TODO:** ✅ 0 candidates — OpenAI remains PARTIAL (HTTP 403 to WebFetch; cookbook verified via gh CLI)
- **primary-sources.md TODO:** 2 known citations still pending (foundational-brief link, RSP doc)
- **playbooks/pro-dev-references.md TODO:** 6 candidates with verified references but no playbook entry yet (Linus, Wozniak, Anthropic, OpenAI, Google SRE, Carmack) — derive WHEN/THEN patterns from the already-verified references, no re-fetch needed except the 2 PARTIALs. Plus operator's Mag7/Tesla/xAI list (names pending) + deeper quote-anchored fetches for the 4 already-canonical devs.

Each session aims to deepen existing canonical entries (quote-anchored fetches) OR convert PARTIAL → Canonical.

## ✅ Recently shipped (last 24h, full chronology)

- 2026-05-26 (1) — Bootstrap commit: README + CLAUDE.md + foundational-brief + docs + Rule #0 first version
- 2026-05-26 (2) — 14 protocol stubs + 1 playbook stub + 3 reference stubs
- 2026-05-26 (3) — Chunk A: 5 high-priority protocols full content
- 2026-05-26 (4) — Chunk B: 5 medium-priority protocols full content
- 2026-05-26 (5) — Chunk C: 4 remaining protocols full content (15/15 ACTIVE)
- 2026-05-26 (6) — Final: index + state + reference templates
- 2026-05-26 (7) — **REFACTOR Rule #0**: gatekeeper-not-excuse framing (operator feedback)
- 2026-05-26 (8) — **First batch verifications**: 4 devs + 1 company + 2 primary-sources via WebFetch
- 2026-05-27 (refs-batch) — Big batch verification: 22 candidates fetched in parallel, 19 promoted to Canonical, 3 to PARTIAL with explicit failure-mode docs
- 2026-05-27 (9) — Housekeeping + playbook canonical entries for the 4 verified devs

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
- **2026-05-27 (refs-batch)** — 22 references batch verification. 19 promoted to Canonical (9 devs + 10 companies on top of 5 existing). 3 marked PARTIAL with explicit failure-mode documentation: Rauch (HTTP 429 rate-limit), Carmack (no public personal site — primary venue is X auth-walled), OpenAI (HTTP 403 to platform + root; cookbook verified via gh CLI instead). All WebFetches batched in 2 parallel waves of 11. Each PARTIAL entry includes exact failure mode + next retry path per Rule #0.
- **2026-05-27 (9)** — Housekeeping: bumped layer-by-layer stub count to reality (15). Promoted Vitalik / Julia / Simon / Mitchell from playbook-TODO to playbook-Canonical with verified-source-backed WHEN/THEN patterns. Per operator: "como aceite a un coche" — entries kept lean, one actionable pattern each. (Ran parallel to refs-batch; merged 2026-06-10 with conflict resolution keeping both sessions' facts.)
