# State — claude-ops

**Last updated:** 2026-05-26 by Claude session (Juan)
**Repo status:** bootstrapping. Rule #0 written. 14 protocol stubs + 1 playbook stub + 3 reference stubs pending content.

## 🟢 Completed (in main)

- `README.md` — purpose, structure, reader (Claude)
- `CLAUDE.md` — Tier 1/2/3 instructions for me when I read this repo
- `docs/foundational-brief.md` — Juan's original brief (verbatim)
- `docs/decisions.md` — ADR-000 (adopt Rule #0)
- `docs/glossary.md` — initial term set
- `docs/architecture.md` — 5-layer model of how I operate
- `protocols/no-fabrication.md` — **Rule #0 COMPLETE** (overrides all)
- 14 protocol stubs + 1 playbook stub + 3 reference stubs (titles + outlines, no content yet)

## 🟡 In flight (next priorities to write FULL)

1. `protocols/error-loop-detection.md` — high ROI (caught me in YouTube debugging loop)
2. `protocols/memory-vs-reality.md` — high ROI (caught me with stale Wizard memory)
3. `protocols/survey-before-building.md` — high ROI (almost duplicated jarvis scripts)
4. `protocols/postmortem-ritual.md` — incident memory is poor
5. `references/developers-canonical.md` — 10-15 verified pro devs with source links

## 🔵 Next sessions backlog

- Fill remaining 10 protocols (one per session, NOT batched)
- Fill 3 references files (per-entry verification — Rule #0 strict)
- `playbooks/pro-dev-references.md` — 5-7 patterns from verified pro devs

## 🚨 Risks / debt

- **Stubs may never become real content** if no enforcement. Mitigation: postmortem ritual auto-prompts to expand relevant stub when failure mode hit.
- **This repo only works if loaded at session start.** Operator must add pointer to global CLAUDE.md.

## 🔄 Pre-flight (for any session that uses this repo)

```bash
# at session start, I must:
cat protocols/no-fabrication.md     # Rule #0
cat docs/state.md                   # this file
cat docs/foundational-brief.md      # operator's framing (if first session)
```

## 📝 Session log

- **2026-05-26** — Bootstrap. README + CLAUDE.md + foundational-brief + decisions + glossary + architecture + Rule #0 complete + stubs.
