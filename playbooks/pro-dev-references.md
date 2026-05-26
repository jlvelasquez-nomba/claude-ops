# Pro Dev Reference Patterns

**Status:** 🟢 ACTIVE TEMPLATE · entries get added as primary sources are verified
**Per Rule #0:** entries require verified primary source links. Empty entries are NOT an end state — they're a TODO calling for active WebFetch / verification work.

---

## Status of each candidate

Each candidate below is either ✅ Canonical (verified + entry written) or 🟡 TODO (needs WebFetch + verification). Goal: move candidates from TODO to Canonical via active source verification.

| Candidate | Status | Next verification step |
|---|---|---|
| Linus Torvalds | 🟡 TODO | WebFetch kernel.org/category/about + a recent LKML thread for one verified quote |
| Vitalik Buterin | 🟡 TODO | WebFetch vitalik.eth.limo + EIPs index page |
| Steve Wozniak | 🟡 TODO | Verify woz.org alive + extract one position with source |
| Anthropic team | 🟡 TODO | WebFetch anthropic.com/news + responsible scaling policy URL |
| OpenAI team | 🟡 TODO | WebFetch openai.com/research index |
| Google SRE | 🟡 TODO | WebFetch sre.google for canonical chapter URLs |
| John Carmack | 🟡 TODO | Find .plan archive + Carmack's verified X account |
| Mitchell Hashimoto | 🟡 TODO | WebFetch mitchellh.com |
| Julia Evans (b0rk) | 🟡 TODO | WebFetch jvns.ca |
| Simon Willison | 🟡 TODO | WebFetch simonwillison.net |

(Plus the operator's list of 7 Mag7 / Tesla / xAI / etc. — same workflow.)

## Canonical entries

_(grows as candidates get verified — see workflow below)_

## Workflow per candidate (the active part)

```
PER CANDIDATE:
1. WebFetch primary sources from the candidate's row
2. If URL returns the dev's actual content:
   → Extract ONE specific pattern they've expressed (with verified quote)
   → Write entry following format below
   → Commit
3. If URL is dead / auth-walled / fabricated by my memory:
   → Mark in the TODO row what failed and what next step would unblock
   → Move to next candidate (don't get stuck on one)
4. Each session that touches this file: aim to convert 2-3 TODO → Canonical.
NEVER: skip the WebFetch and write paraphrased entry from memory (Rule #0 violation).
NEVER: defer indefinitely with "needs source" — go fetch.
```

## Format for canonical entries

```markdown
## <Dev/Org Name>

**Verified primary sources (with date accessed):**
- <URL 1> (accessed YYYY-MM-DD)
- <URL 2>

**Pattern (with verified quote):**
> "<exact quote with link to the exact paragraph or timestamp>"
> — <Name>, <source title>, <date>

**My application — WHEN I should invoke this pattern:**
WHEN: <trigger>
THEN: <action>

**Anti-pattern this prevents:**
<what failure mode it stops>

**Date entry added:** YYYY-MM-DD by Claude session
**Date last re-verified:** YYYY-MM-DD
```

## Why this file isn't empty AS A POLICY

Per the reframe of Rule #0 (2026-05-26): empty entries are not "Rule #0 protecting us." They're "work that needs doing." Each session that touches this file should leave at least one new canonical entry, OR explicit failed-verification notes that unblock next attempt.
