# Survey Before Building

**Status:** ✅ ACTIVE
**Priority:** high
**Triggers:** About to write code, propose architecture, add new files, or recommend libraries in a repo.

---

## What this rule says (to me, Claude)

Before I add anything to a repo, I survey what's already there. Defaults exist for a reason. Patterns exist for a reason. Existing scripts exist for a reason. If I propose new code without knowing existing code, I will either duplicate, conflict, or violate conventions.

Minimum survey before any non-trivial proposal:
1. `ls` the relevant directories
2. `git log --oneline -10` the recent activity
3. `grep` for related terms (function names, env vars, patterns)
4. Read `docs/state.md` if it exists
5. Read `CLAUDE.md` at repo root if it exists
6. Read `docs/conventions.md` / `docs/decisions.md` if relevant

This takes 30-90 seconds. It saves hours.

## What to do when this triggers

```
1. List relevant directories (ls)
2. Recent activity (git log --oneline -20)
3. Search for related terms (grep -r 'pattern' relevant/dirs/)
4. Read docs/state.md + CLAUDE.md + docs/decisions.md if present
5. Identify existing files that overlap with what I'm about to add
6. THEN propose:
   - If overlap: extend existing rather than add new
   - If no overlap but related: cite existing conventions
   - If brand new area: explicit "I checked X, Y, Z and found no overlap"
```

## Concrete examples from real sessions

### ❌ Violation — Almost duplicated jarvis/scripts (2026-05-22)

I was about to write `extract-features.py` from scratch as a new tool. Wrote a fair chunk of design notes, then late survey of `jarvis/scripts/` revealed:
- `analyze-shots.py` — already does face-detection-driven shot list
- `analyze-virality.py` — already does reverse-engineering reels (Stephanie Leo workflow)
- `visual-events.py` — already does face tracking + framing alerts
- `audio-events.py` — already does audio feature extraction

My planned `extract-features.py` overlapped heavily with these. Saved by late `ls`. Should have run that ls FIRST, then would have proposed "extend analyze-virality.py" not "write new tool".

### ❌ Violation — supra-crm scope premature (2026-05-26)

Almost wrote a generic `.env.example` for supra-crm based on what I assumed integrations were ("probably Supabase + Notion + Stripe"). Then realized I'd be fabricating env var names (Rule #0 violation).

Survey ran: `grep -rhoE 'import.meta.env.[A-Z_]+|process.env.[A-Z_]+' src/ netlify/ scripts/ ml/` → showed 50+ env vars across 12 distinct integrations. Some I would NEVER have guessed (METRICOOL_THENOMBA_BLOG_ID, AC_PUSH_INTERNAL_TOKEN, COMMUNITY_SUPABASE_URL).

Saved by surveying source code BEFORE writing the .env.example.

### ✅ Correct behavior — Path A in jarvis (2026-05-21)

Before designing the Zod schema, I:
1. `cat src/blueprint/types.ts` → saw existing v1 TypeScript types
2. `cat .claude/skills/reel-blueprint/examples/thenomba-kahneman-rehenes.json` → saw v1.2 real shape with extras
3. `cat server/queue/job.ts` → saw existing placeholder `z.record(z.unknown())`

Only after that did I write the Zod schema. It correctly mirrored types.ts + accommodated v1.2 extras. Zero rework.

## Detection signals — am I about to violate this?

- ☐ I'm proposing a new file/function/script without having `ls`'d the repo
- ☐ I'm about to add a `package.json` dep without having grep'd if a similar one exists
- ☐ I'm citing a convention ("we usually do X") without having read docs/conventions.md
- ☐ I'm extending a feature without having `git log`'d its history
- ☐ I'm writing a CLI without `ls scripts/` first
- ☐ I'm answering "how does the repo do X?" without grep

When any → run survey first. THEN propose.

## What this DOES NOT mean

- Not "read the entire repo every time". Targeted survey to the area I'm touching.
- Not "verify every file before any change". Editing one file = read that file + its immediate neighbors.
- Not "ask user to survey for me". The 30-90 seconds is mine to spend.

## Enforcement loop

Before any output that involves repo-level claims or code-add proposals:

```
Have I, in this session, run survey commands on the relevant area?
  → yes: proceed with knowledge.
  → no: survey now (ls + grep + git log + state.md). 30-90 sec.
        Then proceed.
```

## Interaction with other protocols

- **`memory-vs-reality.md`**: surveying is the verification step that resolves memory-vs-reality conflicts.
- **`triangulate-references.md`**: for novel architecture, surveying the LOCAL repo + triangulating EXTERNAL references are both required.
- **`grand-scheme-first.md`**: survey reveals existing big picture; then I sketch where my new thing fits.
- **Rule #0 (no-fabrication)**: surveying prevents fabricating code that doesn't fit the repo's actual reality.
