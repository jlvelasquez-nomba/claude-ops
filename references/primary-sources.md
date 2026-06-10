# Primary sources — referenced across protocols

**Status:** 🟢 ACTIVE · 5 canonical · 1 partial-verification · 0 TODO
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

### Operator's foundational brief (this repo)

- **Type:** internal document (canonical operator framing)
- **Author:** Juan (operator), 2026-05-26
- **URL (verified):** [docs/foundational-brief.md](../docs/foundational-brief.md) — in-repo, no external fetch needed (verified present 2026-06-10)
- **Cited by protocols:** most protocols reference the operator's original framing
- **Authoritative on:** why claude-ops exists, the operator's expectations of Claude's working discipline
- **⚠️ Caveat:** internal source — authoritative for THIS repo's intent, not an external engineering claim
- **Date verified:** 2026-06-10 (Claude session, file present in repo)
- **Reviewed by operator:** ⏳

### Anthropic Responsible Scaling Policy (updated)

- **Type:** policy announcement (company primary channel)
- **Author:** Anthropic
- **URL (verified):** https://www.anthropic.com/news/announcing-our-updated-responsible-scaling-policy (accessed 2026-06-10)
- **Published:** 2024-10-15 (per page)
- **Verified direct quote:** "We will not train or deploy models unless we have implemented safety and security measures that keep risks below acceptable levels."
- **Verified structure:** graduated ASL Standards that increase with model capability; two named capability thresholds trigger enhanced safeguards (autonomous AI R&D, CBRN weapons assistance)
- **Cited by protocols:** candidate for `blast-radius.md` (capability-gated safeguards pattern)
- **⚠️ Caveat:** announcement page, not the full policy PDF — for clause-level claims, fetch the policy document itself
- **Date verified:** 2026-06-10 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### First Monday — "A brief history of Facebook as a media text" · ⚠️ PARTIAL VERIFICATION

- **Type:** academic journal article (First Monday, open-access journal)
- **URL:** https://firstmonday.org/ojs/index.php/fm/article/view/5423/4466 (accessed 2026-06-10)
- **Verified:** article exists, title confirmed: "A brief history of Facebook as a media text: The development of an empty structure"
- **NOT verified:** authors, year, full text — the fetch returned navigation only; supplied by operator as "interesting on the architecture side"
- **Next verification step:** re-fetch the article body (or the /5423 landing page) to extract authors, year, and one quotable architecture claim
- **Date attempted:** 2026-06-10 (Claude session, WebFetch — title only)
- **Reviewed by operator:** ⏳ (source supplied by operator)

### "Overview of Facebook scalable architecture" (Barrigas et al., 2014)

- **Type:** published academic paper (ACM Digital Library)
- **URL:** https://dl.acm.org/doi/10.1145/2618168.2618198
- **Metadata (verified via Crossref API, 2026-06-10):** "Overview of Facebook scalable architecture" — Hugo Barrigas, Daniel Barrigas, Melyssa Barata, Pedro Furtado, Jorge Bernardino (University of Coimbra / Polytechnic Institute of Coimbra, Portugal). Published 2014-05-16, Proceedings of the International Conference on Information Systems and Design of Communication (ISDOC)
- **⚠️ Caveats:**
  - This is an EXTERNAL academic analysis by Portuguese researchers — NOT a Meta/Facebook publication. Cite as third-party academic study of Facebook's architecture, never as "Facebook says"
  - Full text is paywalled (ACM DL returns 403 to WebFetch) — body content unread; do not cite specific claims from it until the PDF is actually read
  - It analyzes Facebook's architecture as of ~2014 — a decade stale for current-architecture claims; pair with Meta's own 2023 iOS-architecture post for anything recent
- **Date verified:** 2026-06-10 (Claude session, Crossref API — metadata only)
- **Reviewed by operator:** ⏳ (source supplied by operator)

## TODO — known citations from protocols still needing canonical entries

(none — all known citations have canonical entries as of 2026-06-10; the First Monday article above remains PARTIAL with an explicit retry path)

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
