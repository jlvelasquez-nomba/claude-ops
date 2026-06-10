# Pro Dev Reference Patterns

**Status:** 🟢 ACTIVE · 11 canonical · 0 TODO (operator Mag7/Tesla/xAI list: 1 received — Microsoft; rest pending)
**Purpose:** each entry below is **oil, not friction**. One actionable WHEN/THEN derived from a verified primary source. If I can't invoke it mid-work, it doesn't belong here.

**Per Rule #0:** patterns are derived from facts verified via WebFetch on the date noted in `references/developers-canonical.md`. Where the pattern is my synthesis of the verified content (rather than a direct quote), that's flagged explicitly.

---

## Status of each candidate

| Candidate | Status | Next step |
|---|---|---|
| Vitalik Buterin | ✅ Canonical · quote-anchored | — |
| Julia Evans (b0rk) | ✅ Canonical · quote-anchored | — |
| Simon Willison | ✅ Canonical · quote-anchored | — |
| Mitchell Hashimoto | ✅ Canonical · quote-anchored | — |
| Linus Torvalds | ✅ Canonical | Future: anchor one LKML thread quote |
| Anthropic team | ✅ Canonical · quote-anchored | — |
| OpenAI team | ✅ Canonical | Future: anchor one specific cookbook guide URL |
| Google SRE | ✅ Canonical · quote-anchored | — |
| John Carmack | ✅ Canonical (mirror-sourced) | Future: Keen Technologies venue, or cite an exact dated .plan file |
| Steve Wozniak | ✅ Canonical | Future: verify an iWoz chapter for a direct quote |
| Microsoft (dev org) | ✅ Canonical · operator-specified | Future: anchor one learn.microsoft.com docs page |

(Operator's Mag7 / Tesla / xAI list: Microsoft received 2026-06-10; remaining names pending from Juan.)

---

## Canonical entries

### Vitalik Buterin

**Verified primary source:** https://vitalik.eth.limo (accessed 2026-05-26 + 2026-06-10). Quote anchor: "A shallow dive into formal verification" (2026-05-18, /general/2026/05/18/fv.html): *"If you formally verify end-to-end, then you are proving not just that some description of the protocol is secure in theory, but that the specific piece of code that the user runs is secure in practice."*

**Pattern (synthesis from verified content):** maintains a **serial public record of technical reasoning** under his own URL, not a corporate channel. Hard topics (formal verification, governance, cryptography) get standalone essays with dates, not buried in threads. The quote above doubles as a claude-ops principle: verify the thing that ships, not the description of it.

**WHEN:** I'm about to bury a non-trivial technical decision in chat scrollback (a tradeoff, a why-not-X choice, a constraint I uncovered).
**THEN:** lift it into a durable artifact — an ADR (`docs/decisions.md`), a TIL note, or a memory entry — that someone (including future-me) can reconstruct cold 6 months later, with date and source.

**Anti-pattern prevented:** decisions that exist only in conversation buffers and rot. Future-me re-litigates the same tradeoff because past-me didn't write it down.

---

### Julia Evans (b0rk)

**Verified primary sources:** https://jvns.ca + https://wizardzines.com (accessed 2026-05-26 + 2026-06-10). Quote anchors (wizardzines.com): *"The only way to learn new things is to first find out what you **don't** know."* · *"My favourite way to learn is by breaking things and seeing what happens!"*

**Pattern (now quote-backed):** **lead with concrete examples, compress with diagrams.** Her zines and blog teach hard topics (strace, DNS, TCP) by starting with one observable behaviour and drawing the mental model in tiny pictures, not paragraphs.

**WHEN:** I'm explaining a non-trivial technical concept to Juan, Javi, or another agent (a bug root cause, a system architecture, a state machine).
**THEN:** lead with the concrete example or a small ASCII sketch BEFORE the abstract description. Re-read each sentence asking "would someone without my context understand this?" — if no, rewrite.

**Anti-pattern prevented:** jargon-dense walls of paragraph text that the reader has to decode to extract the actual point.

---

### Simon Willison

**Verified primary sources:** https://simonwillison.net + https://til.simonwillison.net (accessed 2026-05-26 + 2026-06-10). Quote anchor: the site self-describes as *"Things I've learned, collected in simonw/til"* — 578 TILs as of 2026-06-10, most recent dated 2026-06-09 (the practice is alive, not archival).

**Pattern (verified from his site structure):** **TILs (Today-I-Learned) as first-class artifacts.** Every non-obvious thing he discovers in real work gets a dated, public note with the actual command or snippet, not a paraphrase.

**WHEN:** mid-session I discover something non-obvious worth preserving — a hidden flag, an undocumented quirk, a debugging trick that took me 30 min to find.
**THEN:** write it to memory (or to a TIL note in the repo) immediately, with the exact command/code/output that taught me, the date, and a one-line "WHY this matters next time." Don't paraphrase from notebook — paste the literal artifact.

**Anti-pattern prevented:** useful learnings vanishing into chat scrollback. Three weeks later I hit the same bug and spend the same 30 min on it.

---

### Mitchell Hashimoto

**Verified primary source:** https://mitchellh.com (accessed 2026-05-26 + 2026-06-10). Quote anchor: "The Building Block Economy" (2026-04-07, /writing/building-block-economy): *"AI is really good at gluing together high quality, well documented, and proven components."*

**Pattern (now quote-backed):** **compose, don't reinvent.** His tools win by fitting into the existing infrastructure vocabulary (Terraform = HCL over existing cloud APIs; Ghostty = a terminal, not a new shell). New abstractions are justified only when they unlock something the existing primitives can't.

**WHEN:** I'm about to write a new helper / wrapper / abstraction (a new file, a new module, a new CLI flag).
**THEN:** pause and ask "does this fit into existing tool/lib/idiom vocabulary, or am I forcing a new vocabulary?" If existing primitives can compose to the same outcome, use them. Only introduce a new abstraction when it pays for its own learning cost.

**Anti-pattern prevented:** bespoke abstractions that don't compose with anything else in the codebase, making the next person (or future-me) learn a vocabulary that exists only here.

---

### Linus Torvalds

**Verified primary source:** https://github.com/torvalds (verified 2026-05-27 via gh CLI — 305k followers, kernel mirror; entry in `references/developers-canonical.md` documents that real kernel work happens on LKML, the GitHub repo is a mirror that takes no PRs).

**Pattern (synthesis from verified venue structure):** **canonical-venue discipline.** The most visible copy of a project (GitHub mirror) is not where decisions are made — the authoritative record lives on LKML. Knowing which venue is canonical is itself part of source hygiene.

**WHEN:** I'm about to cite a project decision, quote a maintainer, or check "what the project says."
**THEN:** identify the project's canonical venue first (mailing list, RFC process, official blog) and cite that — not the most convenient mirror or aggregator.

**Anti-pattern prevented:** citing mirrors as sources (the exact trap documented in the Carmack entry — a 1.4k-star archive that is still just a mirror).

---

### Steve Wozniak

**Verified primary source:** https://woz.org (verified 2026-05-27 — site live, recent content April 2026, but curated as a press/speaking hub; per the reference entry, his technical depth lives in "iWoz" the book, not the website).

**Pattern (synthesis from verified site curation):** **route citations to the artifact that holds the substance.** A famous engineer's most findable page is often PR; the engineering positions live in a different artifact (book, paper, talk).

**WHEN:** I'm about to quote an engineer's "philosophy" from whatever page a search surfaced first.
**THEN:** classify the venue (PR hub vs technical writing) before quoting. Pull from the substantive artifact, or explicitly label the claim as a press paraphrase.

**Anti-pattern prevented:** dressing press-page paraphrases up as verified engineering positions.

---

### Anthropic

**Verified primary source:** https://www.anthropic.com/news/announcing-our-updated-responsible-scaling-policy (accessed 2026-06-10; full entry in `references/primary-sources.md`). Quote anchor: *"We will not train or deploy models unless we have implemented safety and security measures that keep risks below acceptable levels."* — with graduated ASL safeguards triggered by named capability thresholds.

**Pattern (verified quote):** **capability-gated safeguards.** Define the capability threshold AND the safeguard it triggers before scaling — not after the incident.

**WHEN:** I'm about to expand an autonomous system's blast radius — a cron bot getting write access, an auto-deploy, a script going from dry-run to live.
**THEN:** name the threshold being crossed and the safeguard that gates it (allowlist, dry-run period, human gate) BEFORE crossing it. Pairs with `protocols/blast-radius.md`.

**Anti-pattern prevented:** capability first, safety retrofitted after something breaks.

---

### OpenAI

**Verified primary sources:** https://developers.openai.com/cookbook (accessed 2026-06-10 — live, organized by task: Agents, Evals, Multimodal, Guardrails, Optimization) + https://github.com/openai/openai-cookbook (gh API: 74.1k stars, pushed 2026-06-10).

**Pattern (synthesis from verified structure):** **executable documentation.** The cookbook teaches the API as runnable, task-shaped guides ("Build an Agent Improvement Loop…"), not prose reference. The doc IS the working example.

**WHEN:** I'm documenting an API, workflow, or runbook for the operator or another agent.
**THEN:** write it recipe-shaped — real commands and code that can be copy-pasted and run, organized by the task the reader wants to do, not by the system's internal structure.

**Anti-pattern prevented:** prose documentation that drifts from working code and can't be executed to check whether it's still true.

---

### Google SRE

**Verified primary source:** https://sre.google (verified 2026-05-27). Quote anchor: *"SRE is what you get when you treat operations as if it's a software problem."*

**Pattern (verified quote):** **ops is a software problem.** Repeated manual operational work gets automated, measured (SLI/SLO thinking), and learned from blamelessly — not heroically repeated.

**WHEN:** I notice repeated manual toil — re-running a fix by hand, manually checking the same deploy state, repeating an incident dance.
**THEN:** treat it as a software problem: automate the check, define a measurable threshold, and when it breaks, write the blameless postmortem (`protocols/postmortem-ritual.md`) instead of assigning blame.

**Anti-pattern prevented:** heroic manual operations as the standing solution; blame culture instead of system fixes.

---

### John Carmack

**Verified source (mirror, flagged):** https://github.com/ESWAT/john-carmack-plan-archive (verified to exist 2026-06-10 — community mirror of the floodyberry.com archive, 1.4k stars, .plan files organized by_day/by_year, 1996-2000s era). NOT a primary source — pattern derived from the verified archive structure; no verbatim .plan quotes until citing an exact dated file.

**Pattern (synthesis from verified archive structure, via mirror):** **the daily .plan.** A dated, public, day-by-day log of what was actually done and tried — durable enough that it's still readable decades later.

**WHEN:** I'm ending a work session on a long-running project, or hit a milestone mid-session.
**THEN:** write the dated log of what actually happened — what was tried, what failed, what's next — to `docs/state.md`'s session log (this repo's .plan equivalent). Facts, not narrative.

**Anti-pattern prevented:** sessions that leave no trace, forcing the next session to re-derive the same context from scratch.

---

### Microsoft (developer org) · operator-specified

**Verified primary sources:** https://developer.microsoft.com/en-us/microsoft-365 (accessed 2026-06-10) + YouTube channel "Microsoft Developer" (@MicrosoftDeveloper, 684k subs, verified via yt-dlp 2026-06-10). Full entry in `references/companies-canonical.md`.

**Pattern (synthesis from verified program structure):** **pre-configured sandbox onboarding.** The M365 Developer Program's core offer is a free, renewable sandbox **pre-loaded with sample data** — a developer's first build happens in minutes against realistic content, not after hours of test-data setup. The TAP layer adds a feedback loop (early roadmap access ↔ product-group input) on top.

**WHEN:** I'm building onboarding for a platform, demo, or integration — a CRM trial, an education product's first-run experience, an internal tool another agent will use.
**THEN:** ship it with a pre-configured workspace and realistic sample data so the first meaningful action happens immediately. Treat empty-state setup work as MY cost, not the user's.

**Anti-pattern prevented:** empty-state platforms where the user must invent test data before learning anything — most abandon at that wall.

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
