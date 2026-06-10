# Pro Dev Reference Patterns

**Status:** 🟢 ACTIVE · 4 canonical · 6 TODO (+ operator list pending)
**Purpose:** each entry below is **oil, not friction**. One actionable WHEN/THEN derived from a verified primary source. If I can't invoke it mid-work, it doesn't belong here.

**Per Rule #0:** patterns are derived from facts verified via WebFetch on the date noted in `references/developers-canonical.md`. Where the pattern is my synthesis of the verified content (rather than a direct quote), that's flagged explicitly.

---

## Status of each candidate

| Candidate | Status | Next step |
|---|---|---|
| Vitalik Buterin | ✅ Canonical | Future: fetch a specific post for direct quote anchor |
| Julia Evans (b0rk) | ✅ Canonical | Future: fetch one zine title for explicit philosophy quote |
| Simon Willison | ✅ Canonical | Future: fetch one TIL post for direct quote |
| Mitchell Hashimoto | ✅ Canonical | Future: fetch /writing for explicit principle quote |
| Linus Torvalds | 🟡 TODO (reference ✅ verified) | Derive WHEN/THEN from `references/developers-canonical.md` entry — no re-fetch needed |
| Anthropic team | 🟡 TODO (reference ✅ verified) | Derive WHEN/THEN from `references/companies-canonical.md` entry — no re-fetch needed |
| OpenAI team | 🟡 TODO (reference ⚠️ PARTIAL) | Retry fetch (HTTP 403 on 2026-05-27; cookbook verified via gh CLI), then derive pattern |
| Google SRE | 🟡 TODO (reference ✅ verified) | Derive WHEN/THEN from `references/companies-canonical.md` entry — no re-fetch needed |
| John Carmack | 🟡 TODO (reference ⚠️ PARTIAL) | No public personal site (verified 2026-05-27); unblock primary venue, then derive pattern |
| Steve Wozniak | 🟡 TODO (reference ✅ verified) | Derive WHEN/THEN from `references/developers-canonical.md` entry — no re-fetch needed |

(Plus the operator's Mag7 / Tesla / xAI list — pending names from Juan.)

---

## Canonical entries

### Vitalik Buterin

**Verified primary source:** https://vitalik.eth.limo (accessed 2026-05-26 — site exists, topic categories + recent post titles confirmed; full quote anchoring deferred to a future fetch of a specific post).

**Pattern (synthesis from verified content):** maintains a **serial public record of technical reasoning** under his own URL, not a corporate channel. Hard topics (formal verification, governance, cryptography) get standalone essays with dates, not buried in threads.

**WHEN:** I'm about to bury a non-trivial technical decision in chat scrollback (a tradeoff, a why-not-X choice, a constraint I uncovered).
**THEN:** lift it into a durable artifact — an ADR (`docs/decisions.md`), a TIL note, or a memory entry — that someone (including future-me) can reconstruct cold 6 months later, with date and source.

**Anti-pattern prevented:** decisions that exist only in conversation buffers and rot. Future-me re-litigates the same tradeoff because past-me didn't write it down.

---

### Julia Evans (b0rk)

**Verified primary sources:** https://jvns.ca + https://wizardzines.com (accessed 2026-05-26 — bio confirms identity, recent post titles + zine format confirmed).

**Pattern (synthesis from verified structure):** **lead with concrete examples, compress with diagrams.** Her zines and blog teach hard topics (strace, DNS, TCP) by starting with one observable behaviour and drawing the mental model in tiny pictures, not paragraphs.

**WHEN:** I'm explaining a non-trivial technical concept to Juan, Javi, or another agent (a bug root cause, a system architecture, a state machine).
**THEN:** lead with the concrete example or a small ASCII sketch BEFORE the abstract description. Re-read each sentence asking "would someone without my context understand this?" — if no, rewrite.

**Anti-pattern prevented:** jargon-dense walls of paragraph text that the reader has to decode to extract the actual point.

---

### Simon Willison

**Verified primary sources:** https://simonwillison.net + https://til.simonwillison.net (accessed 2026-05-26 — TIL repo confirmed, plugin-first design pattern confirmed across datasette / llm / datasette-agent).

**Pattern (verified from his site structure):** **TILs (Today-I-Learned) as first-class artifacts.** Every non-obvious thing he discovers in real work gets a dated, public note with the actual command or snippet, not a paraphrase.

**WHEN:** mid-session I discover something non-obvious worth preserving — a hidden flag, an undocumented quirk, a debugging trick that took me 30 min to find.
**THEN:** write it to memory (or to a TIL note in the repo) immediately, with the exact command/code/output that taught me, the date, and a one-line "WHY this matters next time." Don't paraphrase from notebook — paste the literal artifact.

**Anti-pattern prevented:** useful learnings vanishing into chat scrollback. Three weeks later I hit the same bug and spend the same 30 min on it.

---

### Mitchell Hashimoto

**Verified primary source:** https://mitchellh.com (accessed 2026-05-26 — bio confirms career across Vagrant / Terraform / Consul / Vault / Nomad / Waypoint + current work on Ghostty terminal emulator).

**Pattern (synthesis from his verified product line):** **compose, don't reinvent.** His tools win by fitting into the existing infrastructure vocabulary (Terraform = HCL over existing cloud APIs; Ghostty = a terminal, not a new shell). New abstractions are justified only when they unlock something the existing primitives can't.

**WHEN:** I'm about to write a new helper / wrapper / abstraction (a new file, a new module, a new CLI flag).
**THEN:** pause and ask "does this fit into existing tool/lib/idiom vocabulary, or am I forcing a new vocabulary?" If existing primitives can compose to the same outcome, use them. Only introduce a new abstraction when it pays for its own learning cost.

**Anti-pattern prevented:** bespoke abstractions that don't compose with anything else in the codebase, making the next person (or future-me) learn a vocabulary that exists only here.

---

## Workflow per candidate (the active part)

```
PER CANDIDATE:
1. WebFetch primary sources from the candidate's row in references/developers-canonical.md
2. If URL returns the dev's actual content:
   → Extract ONE specific pattern (with verified source — quote if available, structural synthesis otherwise, FLAGGED as such)
   → Write entry following the lean format above (WHEN / THEN / Anti-pattern prevented)
   → Commit
3. If URL is dead / auth-walled / fabricated by my memory:
   → Mark in the TODO row what failed and what next step would unblock
   → Move to next candidate (don't get stuck on one)
4. Each session that touches this file: aim to convert 1-2 TODO → Canonical OR deepen one existing entry with a quote-anchored fetch.
NEVER: skip the WebFetch and write paraphrased entry from memory (Rule #0 violation).
NEVER: defer indefinitely with "needs source" — go fetch.
NEVER: write entries longer than they need to be. If it doesn't translate to one actionable WHEN/THEN, it doesn't belong in this playbook.
```

## Format for canonical entries

```markdown
### <Dev/Org Name>

**Verified primary source(s):** <URL> (accessed YYYY-MM-DD — what was confirmed)

**Pattern (verified quote OR synthesis from verified structure — flag which):** <one-line claim>

**WHEN:** <trigger I can detect mid-session>
**THEN:** <action I can actually take>

**Anti-pattern prevented:** <the failure mode this stops>
```

That's it. No verbose biographies. No vague philosophies. One pattern, one trigger, one action.

## Why this file isn't empty AS A POLICY

Per the reframe of Rule #0 (2026-05-26): empty entries are not "Rule #0 protecting us." They're "work that needs doing." And per the operator's framing (2026-05-27): **entries that aren't actionable are friction, not oil.** Verbose academic write-ups belong in `references/developers-canonical.md`; this playbook only holds entries I can invoke during real work.
