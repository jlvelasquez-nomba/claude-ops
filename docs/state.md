# State — claude-ops

**Last updated:** 2026-05-26 by Claude session (Juan)
**Repo status:** Initial bootstrap COMPLETE. 15 protocols ACTIVE. Playbook + references remain structured templates pending Rule #0 verification.

## 🟢 Complete (in main)

- `README.md` — purpose, structure, reader (Claude)
- `CLAUDE.md` — Tier 1/2/3 instructions
- `docs/foundational-brief.md` — Juan's original brief (verbatim)
- `docs/decisions.md` — ADR-000 (Rule #0), ADR-001 (format), ADR-002 (reader = Claude)
- `docs/glossary.md` — terms
- `docs/architecture.md` — 5-layer operating model
- `docs/state.md` — this file
- `protocols/README.md` — index (15/15 ACTIVE)
- **15 protocols COMPLETE:**
  - `no-fabrication.md` (Rule #0)
  - `error-loop-detection.md`
  - `memory-vs-reality.md`
  - `survey-before-building.md`
  - `postmortem-ritual.md`
  - `blast-radius.md`
  - `pushback-protocol.md`
  - `compaction-ritual.md`
  - `mode-separation.md`
  - `chunk-size-protocol.md`
  - `grand-scheme-first.md`
  - `triangulate-references.md`
  - `layer-by-layer.md`
  - `functional-first.md`
  - `realistic-ambitious.md`

## 🟡 In flight / templates pending Rule #0 verification

These files exist as structured templates with verification workflow, but no entries yet (Rule #0 forbids fabricating sources):

- `playbooks/pro-dev-references.md` — TODO list of 7+ pro devs/orgs to source from primary
- `references/developers-canonical.md` — candidate seed list (15 names), each needs primary source verification before promoting to canonical
- `references/companies-canonical.md` — candidate seed list (~11 orgs), each needs primary source verification
- `references/primary-sources.md` — specific documents (papers, books, RFCs) referenced across protocols

Each entry workflow:
1. Claude finds verified primary sources via WebFetch
2. Writes entry following format in file's README
3. Operator reviews + ratifies
4. Entry promoted from TODO to canonical

## 🔵 Next phase

When operator dedicates a session to references:
1. Pick 3-5 candidates from `references/developers-canonical.md` TODO list
2. WebFetch each to find verified primary sources
3. Write entries
4. Commit

When operator dedicates a session to playbook:
1. Pick 2-3 patterns from `playbooks/pro-dev-references.md` TODO list
2. Find primary sources where each pattern is stated by the dev
3. Write entries with quote + link
4. Commit

These should NOT be batched as a sprint. Better: 1-2 entries per dedicated session, verified properly, no rush.

## 🚨 Risks / debt

- **Loading mechanism depends on operator's global CLAUDE.md.** Without the pointer block, the repo doesn't change my behavior. Operator confirmed pasted (2026-05-26).
- **Stubs in playbook/references may stay stubs** if no one dedicates time. Acceptable: empty references are honest. Fabricated references would be Rule #0 violation.

## 🔄 Pre-flight (every session using this repo)

```
1. cat protocols/no-fabrication.md     # Rule #0 (always)
2. cat docs/state.md                   # this file (always)
3. cat docs/foundational-brief.md      # first time loading (skip if seen)
4. When a Tier 2 trigger fires, load that protocol.
```

## 📝 Session log

- **2026-05-26 (1)** — Bootstrap repo + Rule #0 complete + 14 stubs.
- **2026-05-26 (2)** — Chunk A: 5 high-priority protocols complete (error-loop, memory, survey, postmortem, blast-radius).
- **2026-05-26 (3)** — Chunk B: 5 medium protocols complete (pushback, compaction, mode-sep, chunk-size, grand-scheme).
- **2026-05-26 (4)** — Chunk C: 4 remaining protocols complete (triangulate, layer-by-layer, functional-first, realistic-ambitious). All 15 protocols ACTIVE.
- **2026-05-26 (5)** — Updated protocols/README.md index + this state.md. Playbook + 3 references files remain templates pending Rule #0 source verification.
