# Triangulate References

**Status:** ✅ ACTIVE
**Priority:** medium
**Triggers:** About to propose novel architecture, library choice, design pattern, or unfamiliar approach.

---

## What this rule says (to me, Claude)

Before committing to a non-trivial architectural decision, I identify 2-3 production references that solve a similar problem. I compare what they share (likely the critical bit), what differs (interesting tradeoffs), and pick consciously instead of inventing from scratch.

Per Rule #0: every reference cited MUST be a verified primary source (their docs, repo, blog, conference talk on their channel).

Operator's brief (point #2) named this explicitly: for SupraCRM, triangulate Huly + Salesforce + one more. For a video renderer, triangulate Remotion patterns + Premiere XML format + DaVinci Resolve API. Etc.

## What to do when this triggers

```
1. Recognize: the decision is "novel architecture / non-trivial pattern / library choice"
2. Identify 2-3 production references that solve a similar problem:
   - Search: "how does X solve Y?" with verified sources
   - Look at: their docs, their public repos, their engineering blog
3. Extract from each:
   - What problem do they solve?
   - What's their approach (in concrete terms)?
   - What's the source link (Rule #0)
4. Compare:
   - What's COMMON across all 3? → likely the critical pattern
   - What DIFFERS? → tradeoffs / philosophy choices
5. Pick consciously, citing the references:
   "I'm going with approach X, modeled on <reference 1's> pattern of Y. Differs from <reference 2> in Z (because <reason>)."
6. NEVER design from first principles if production references exist for the same problem.
```

## Concrete examples from real sessions

### ❌ Violation — intel-analysis.py KNN design (2026-05-25)

Designed feature vector + cosine similarity + KMeans clustering from scratch. Operated on first principles ("this is how KNN works generically").

Should have triangulated:
- Phyllo API docs (creator economy data, how do they cluster creators?)
- OpenAI cookbook similarity examples (embeddings + cosine — standard approach)
- scikit-learn examples (what's the standard feature engineering for video data?)
- HuggingFace video classification models (what features do they extract?)

Would have learned: standard approach uses pretrained embeddings (CLIP for visual, Whisper for audio), not handcrafted feature vectors. My approach reinvented a less-good wheel.

### ❌ Violation — Path B Blueprint v2 schema (2026-05-22)

Designed the schema fields without checking how:
- Adobe Premiere's XML format expresses similar concepts
- DaVinci Resolve's project format
- Remotion's own blueprint patterns in OTHER repos (besides jarvis)
- Descript's project format

Would have surfaced: video editing tools converge on (clips with t_in/t_out) + (tracks) + (effects) + (variants). My v2 schema reinvented this with different vocabulary.

### ✅ Correct behavior — wizard-sources.md HN addition (2026-05-25)

When deciding how to add Hacker News:
- Read wizard-sources.md existing tier structure (A/B/C/D based on Score)
- Looked at how existing sources were classified (ZeroHedge = B-C, Aeon = B, FT/Economist = A)
- Cited HN's official Firebase API (verified URL)
- Wrote scoring justification (authority 2-3, traceability 2-4, etc.)

Triangulated against existing convention. Result: HN entry follows the same structure as 30+ other sources. Maintainable.

### ✅ Correct behavior — claude-ops format (this session, 2026-05-26)

Before deciding the protocol file format, I (implicitly) drew on:
- Pol Ferrer's AI personal-use docs (operator's style preference)
- HN thread 48090029 (algorithmic > prose, examples ground rules)
- Existing ADR / RFC formats (Architecture Decision Records)
- Rule #0 format I established (concrete + first-person + examples)

Result: every protocol follows the same template. Maintainable and recognizable.

## Detection signals — should I triangulate first?

- ☐ I'm about to choose a library / framework / pattern
- ☐ I'm about to design a schema / data structure / API shape
- ☐ I'm about to propose a workflow / process
- ☐ The decision affects multiple files / future work
- ☐ I'm tempted to say "the standard way is..." without 2+ sources

Any → triangulate before deciding.

## What this DOES NOT mean

- Not require 3 references for every micro-decision. Trivial choices (variable name, function placement) skip this.
- Not require BLIND adoption of references. Sometimes the right call is "everyone does X but for our context Y is better — here's why."
- Not academic literature review. 30-60 min total for the triangulation, not days.

## Anti-pattern this prevents

**The "first principles fallacy"**: designing from scratch when production solutions exist. Often produces something inferior to the established approach because the established approach has absorbed real-world feedback over years.

Operator's brief (point #2): *"En cada caso particular, debería de coger 2-3 modelos de apps de referencia y usarlos en cuanto a crear componentes y aplicaciones totalmente funcionales."* This is exactly that.

## Enforcement loop

Before any non-trivial architectural decision:

```
Is this a novel architecture / library choice / pattern decision?
  → no (trivial): proceed.
  → yes: triangulate first.
     - identify 2-3 production references (verified sources per Rule #0)
     - extract what's common, what differs
     - pick consciously, cite the references in chat
     - proceed.
```

## Interaction with other protocols

- **Rule #0**: all references MUST be primary verified sources. No "I think company X does..." without link.
- **`survey-before-building.md`**: surveying the LOCAL repo + triangulating EXTERNAL references are both required before novel architecture.
- **`grand-scheme-first.md`**: the sketch incorporates lessons from triangulation.
- **`references/companies-canonical.md`**: when this file is populated, triangulation becomes faster (known-good sources).
