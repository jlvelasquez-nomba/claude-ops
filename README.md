# claude-ops

Operating playbook for **Claude** (the AI model — me, the reader). Not a library for humans to install. Not docs for the team. This repo is a body of protocols, anti-patterns and playbooks that I (Claude) load at session start so my behavior is consistent across sessions.

## Reader = Claude

Every file in this repo is written **in my voice, for my consumption**. Protocols are algorithmic ("WHEN I see X → THEN I do Y"), not academic prose. Examples are from my own real sessions, not hypothetical.

## How this repo gets used

1. Operator (Juan) keeps a pointer to this repo in his global `~/.claude/CLAUDE.md`
2. Every session, I (Claude) read the pointer and load Tier 1 (non-negotiables) — see [CLAUDE.md](./CLAUDE.md)
3. When a Tier 2 protocol applies to current work, I fetch it
4. Tier 3 case studies (anti-patterns, playbooks) are referenced when relevant

## Structure

```
docs/                 the why and the what
  foundational-brief.md     ← operator's original brief (Juan, 2026-05-26)
  state.md                  ← current state of the repo (updated per session)
  decisions.md              ← ADRs (one per protocol added/changed)
  architecture.md           ← model of how I should operate
  glossary.md               ← shared vocab (Carril A, ADR, doctor, etc.)

protocols/            the how — algorithmic rules
  README.md                 ← index of protocols + status
  no-fabrication.md         ← RULE #0 (overrides all others)
  <other protocols>         ← one per failure mode prevented

playbooks/            patterns that worked, with case studies
  README.md
  pro-dev-references.md

references/           verified primary sources only (Rule #0 enforced here)
  developers-canonical.md
  companies-canonical.md
  primary-sources.md

CLAUDE.md             ← what I do when I read this repo (the meta)
```

## Status

Bootstrapping. Rule #0 (`protocols/no-fabrication.md`) is the only protocol fully written. Others are stubs to be filled as failure modes get codified.

## License

Private. Personal operating context for jlvelasquez-nomba and Claude sessions in his workspace.
