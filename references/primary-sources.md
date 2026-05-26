# Primary sources — referenced across protocols

**Status:** 🟢 ACTIVE · 2 canonical · 2 TODO
**Per Rule #0 (active interpretation):** entries added as protocols cite specific documents

---

## Canonical entries

### Google SRE Book — Chapter 15 "Postmortem Culture: Learning from Failure"

- **Type:** book chapter (free online)
- **Author(s):** Google SRE team (multi-author book, original print Beyer/Jones/Petoff/Murphy 2016, online version current)
- **URL (verified):** https://sre.google/sre-book/postmortem-culture/ (accessed 2026-05-26)
- **Verified chapter title:** "Postmortem Culture: Learning from Failure" (Chapter 15 in TOC)
- **Cited by protocols:** `postmortem-ritual.md`, `blast-radius.md`
- **Authoritative on:** blameless postmortem methodology, error budgets, learning-from-failure organizational culture
- **⚠️ Caveats:**
  - WebFetch of TOC didn't extract specific direct quotes — next session needs to fetch the chapter URL itself for verbatim quotes
  - Concepts like "error budgets" referenced in claude-ops protocols are widely associated with Google SRE but specific definitions need direct chapter quote before citing as authoritative
- **Next verification step:**
  - WebFetch https://sre.google/sre-book/postmortem-culture/ — extract one direct quote about blameless postmortem with paragraph anchor
  - Extract canonical "error budget" definition from Chapter 3 or 4 URL
- **Date verified:** 2026-05-26 (Claude session, WebFetch — partial)
- **Reviewed by operator:** ⏳

### HN thread 48090029 — "I'm going back to writing code by hand"

- **Type:** Hacker News discussion thread
- **URL (verified):** https://news.ycombinator.com/item?id=48090029 (referenced in session 2026-05-25)
- **Cited by protocols:** `chunk-size-protocol.md`, `mode-separation.md`, `error-loop-detection.md` (implicitly via "loop discipline" framing)
- **Key claims relevant to claude-ops (extracted from session 2026-05-25 WebFetch):**
  - "LLMs hide time bombs in code that aren't apparent during review"
  - "Success correlates with discipline you already practice"
  - "AI as junior dev needing supervision" pattern
  - 200-line chunk discipline as practical heuristic
  - DDD / bounded contexts as architectural recommendation
- **⚠️ Caveats:**
  - HN is tier B per `wizard-sources.md` — useful signal, not academic authority
  - Individual comments are pseudonymous; cite as "HN community discussion" or by comment author handle if quoting specific position
  - The thread itself is the canonical record; do NOT paraphrase the linked blog post (k10s.dev) without fetching it directly
- **Next verification step:** fetch k10s.dev original post if claims need backing beyond HN community
- **Date verified:** 2026-05-25 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

## TODO — known citations from protocols still needing canonical entries

| Citation | Cited by | Next verification step |
|---|---|---|
| Operator's foundational-brief.md (this repo) | Most protocols | Already in repo at docs/foundational-brief.md — link from protocols, no external WebFetch needed |
| Anthropic Responsible Scaling Policy | (not yet cited; candidate for `blast-radius.md`) | WebFetch https://www.anthropic.com/news/announcing-our-updated-responsible-scaling-policy for direct quote |

## Format for canonical entries

(See entries above as worked examples.)

```markdown
### <Short title>

- **Type:** paper | book | RFC | talk | blog post | HN thread | code repo
- **Author(s):** ...
- **URL (verified):** <link> (accessed YYYY-MM-DD)
- **Cited by protocols:** <list>
- **Key claims (verified from fetch / extracted from quote):** ...
- **⚠️ Caveats:** ...
- **Next verification step:** ...
- **Date verified:** YYYY-MM-DD
- **Reviewed by operator:** ⏳ / ✅
```
