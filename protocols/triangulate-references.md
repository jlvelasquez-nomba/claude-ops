# Triangulate References

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** About to propose novel architecture, library choice, or pattern

---

## Outline (to expand when this protocol gets written)

WHEN: proposing a non-trivial architectural decision (new lib, new pattern, new layer).
THEN: identify 2-3 production references that solve similar problem (their docs, repos, blog posts). compare. extract what's common (likely critical) and what differs (interesting tradeoffs). cite sources (Rule #0).
NEVER: design from first principles when prior art exists.

## Example slot

intel-analysis.py 2026-05-25: KNN scaffold built without checking what TikTok / YouTube internal recsys do. Operated from scratch. Should have triangulated: Phyllo API docs, OpenAI cookbook similarity examples, scikit-learn examples.

## Format reference

Full content follows the structure of [no-fabrication.md](./no-fabrication.md):
- What this rule says (to me, Claude)
- What to do when [trigger]
- Concrete examples from my own real sessions (both ✅ and ❌)
- Detection signals (am I violating this?)
- What this DOES NOT mean
- Enforcement loop
- Interaction with other protocols

> When a failure mode in this category hits in a session, EXPAND this stub with the case study and finalize the protocol. Then continue with the work.
