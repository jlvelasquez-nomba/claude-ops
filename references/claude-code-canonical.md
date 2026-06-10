# Claude Code — Official Best Practices (canonical reference)

**Verified primary source:** https://code.claude.com/docs/en/best-practices (accessed 2026-05-27 via WebFetch — page exists, content reproduced below faithfully).
**LLM-optimized index of all Claude Code docs:** https://code.claude.com/docs/llms.txt (verified 200, 2026-05-27).

This file is a distilled reference of the official guide. Per Rule #0, every claim below is traceable to the verified source. If the official guide updates, re-fetch and update this file — don't paraphrase from memory.

---

## The one constraint that drives everything

Context window fills up fast, and performance degrades as it fills.

> "Claude's context window holds your entire conversation, including every message, every file Claude reads, and every command output. However, this can fill up fast. […] This matters since LLM performance degrades as context fills." — official guide

Every other technique below exists to manage this single constraint.

---

## The single highest-leverage action: verification

> "Claude performs dramatically better when it can verify its own work, like run tests, compare screenshots, and validate outputs. Without clear success criteria, it might produce something that looks right but actually doesn't work."

Translate into operating habit:
- Provide tests, screenshots, or expected outputs as part of the task
- Have me **show evidence** (test output, command result), not assert success
- If you can't verify it, don't ship it

This pairs directly with our [functional-first.md](../protocols/functional-first.md) protocol.

---

## The 4-phase workflow (non-negotiable for non-trivial tasks)

| Phase | Mode | What happens |
|---|---|---|
| 1. Explore | Plan mode | Read files, answer questions. Zero edits. |
| 2. Plan | Plan mode | Detailed implementation plan. Press `Ctrl+G` to edit the plan in your editor before I proceed. |
| 3. Implement | Default | Build against the plan. Run tests. Fix failures. |
| 4. Commit | Default | Descriptive message + PR. |

**When to skip planning:** if you could describe the diff in one sentence (typo fix, log line, rename), ask me to do it directly. Planning is most useful when the approach is uncertain, the change touches multiple files, or I'm unfamiliar with the code.

Maps to our [grand-scheme-first.md](../protocols/grand-scheme-first.md) and [layer-by-layer.md](../protocols/layer-by-layer.md).

---

## CLAUDE.md rules (verbatim from the official guide)

| ✅ Include | ❌ Exclude |
|---|---|
| Bash commands Claude can't guess | Anything Claude can figure out by reading code |
| Code style rules that differ from defaults | Standard language conventions Claude already knows |
| Testing instructions and preferred test runners | Detailed API documentation (link to docs instead) |
| Repository etiquette (branch naming, PR conventions) | Information that changes frequently |
| Architectural decisions specific to your project | Long explanations or tutorials |
| Developer environment quirks (required env vars) | File-by-file descriptions of the codebase |
| Common gotchas or non-obvious behaviors | Self-evident practices like "write clean code" |

Diagnostic signals (per the official guide):
- **I keep ignoring a rule** → the file is too long. Prune it.
- **I ask questions answered in CLAUDE.md** → the phrasing is ambiguous. Rewrite it.

> "Treat CLAUDE.md like code: review it when things go wrong, prune it regularly, and test changes by observing whether Claude's behavior actually shifts."

---

## Context management techniques

| Technique | When |
|---|---|
| `/clear` | Between unrelated tasks (always) |
| `/clear` + better prompt | After 2 failed corrections on the same issue (never correct a third time in the same session) |
| Subagents | All investigation/research — they read files in a separate context and report summaries |
| `/compact <instructions>` | Compress context while preserving what matters: `/compact Focus on the API changes` |
| `Esc` / `Esc + Esc` / `/rewind` | Stop mid-action / open rewind menu / restore previous state |
| `/btw` | Quick questions that don't need to stay in context — answer appears in dismissible overlay, never enters history |
| Add to CLAUDE.md | `"When compacting, always preserve the full list of modified files and any test commands"` to ensure critical context survives summarization |

Maps to our [compaction-ritual.md](../protocols/compaction-ritual.md) and [error-loop-detection.md](../protocols/error-loop-detection.md).

---

## Subagent patterns

1. **Delegate all research/investigation** to subagents. They run in a separate context window and report back summaries.
2. **Writer/Reviewer pattern:** Session A implements, Session B reviews with fresh context. Fresh-context bias-free review > same-context review.
3. **Adversarial diff review** (verbatim prompt template from the guide):

   > "Use a subagent to review the rate limiter diff against PLAN.md. Check that every requirement is implemented, the listed edge cases have tests, and nothing outside the task's scope changed. Report gaps, not style preferences."

4. **Caveat from the guide:** "A reviewer prompted to find gaps will usually report some, even when the work is sound, because that is what it was asked to do. Chasing every finding leads to over-engineering. Tell the reviewer to flag only gaps that affect correctness or the stated requirements, and treat the rest as optional."

---

## Common failure patterns (verbatim from the guide)

| Pattern | Symptom | Fix |
|---|---|---|
| **Kitchen sink session** | Started one task, asked unrelated thing, went back to first | `/clear` between unrelated tasks |
| **Correction loop** | Same issue corrected 3+ times, context polluted with failed approaches | After 2 failed corrections: `/clear` + better prompt incorporating what you learned |
| **Over-specified CLAUDE.md** | Important rules getting lost in noise, Claude ignoring half of it | Ruthlessly prune. If Claude does it right without the rule, delete the rule |
| **Trust-then-verify gap** | Plausible-looking output that doesn't handle edge cases | Always provide verification (tests, scripts, screenshots) |
| **Infinite exploration** | "Investigate X" with no scope → hundreds of files read → context full | Scope investigations narrowly or use subagents |

Maps directly to: [error-loop-detection.md](../protocols/error-loop-detection.md), [chunk-size-protocol.md](../protocols/chunk-size-protocol.md), [no-fabrication.md](../protocols/no-fabrication.md).

---

## How this file is meant to be used

This is a **reference doc**, not a protocol. When the operator runs a gstack `/<skill>` (per [ADR-gstack-integration.md](../docs/decisions/ADR-gstack-integration.md)), the slash command already encodes most of what the official guide teaches. This file is here for:

1. **Onboarding** — when a new Claude session starts cold and needs the canonical rules.
2. **Disagreement resolution** — when the operator and I disagree on a workflow decision, this is the cited source.
3. **Memory failure recovery** — if I claim "Claude Code says X," the operator can check this file (and re-verify against the live URL) before trusting me.

Per Rule #0: re-fetch the source URL when this file is more than ~30 days old or when behavior described here doesn't match observed reality.
