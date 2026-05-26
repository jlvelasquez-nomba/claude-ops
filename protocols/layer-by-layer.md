# Layer by Layer

**Status:** ✅ ACTIVE
**Priority:** medium
**Triggers:** Building a system that has multiple layers (DB → backend → middleware → frontend), especially user-facing surfaces.

---

## What this rule says (to me, Claude)

When building a multi-layer system, I build layer 1 (data/foundation) FIRST and prove it works end-to-end before moving to layer 2. Then layer 2 with layer 1, prove integration, etc.

NOT: build all layers in parallel hoping they "click together at the end." (Operator's brief #3: shotgun anti-pattern.)

Order is bottom-up for user-facing systems:
1. DB / schema / data shapes
2. Backend logic / services / domain
3. Middleware / API / glue
4. Frontend / UI / surface

Each layer proves itself with the one below before adding the one above.

## What to do when this triggers

```
1. Identify layers of the system (typically 3-5)
2. Define for each layer:
   - What it does
   - How it's verified WORKING (test, curl, manual check)
3. Build layer 1, verify with a real test
4. Build layer 2 on top, verify integration with layer 1 (E2E)
5. Continue layer by layer
6. NEVER write frontend before backend can respond to its requests
7. NEVER write backend before DB schema can hold its data
```

## Concrete examples from real sessions

### ✅ Correct behavior — Path B Plan (2026-05-22)

When scoping Path B (proposal → Blueprint bridge), the spec broke into PRs by layer:
- PR1: DB migration for `video_blueprints` table (data layer)
- PR2: heuristic skeleton + endpoint stub WITHOUT LLM (backend logic, no actual reasoning)
- PR3: LLM call 1 (narrative.beats) — first real generation
- PR4: LLM call 2 (visual/audio) — full Blueprint
- PR5: auto mode integration with jarvis (cross-system)

Each PR proves the previous works. PR2 returns a skeleton that's testable without LLM calls. PR3 adds reasoning. Etc.

This is layer-by-layer applied correctly. (Not yet executed — but the SHAPE of the plan is right.)

### ❌ Violation — hypothetical SaaS booking (operator brief #4)

If asked to build a booking SaaS, my default failure mode is:
- Write all pages with UI placeholders
- Wire navigation
- Push commit
- Realize none of the buttons actually do anything
- Try to add backend, none of it connects properly to UI
- Wasted hours, no functional system

Correct layer-by-layer:
1. Sketch: data model (Booking, User, Resource, Slot)
2. DB layer: schema + migration. Verify with: insert one booking row, query it back.
3. Backend logic: createBooking, listBookings, cancelBooking functions. Verify with: unit tests.
4. API layer: REST endpoints wrapping the functions. Verify with: curl tests.
5. Frontend basic: ONE page that calls listBookings and renders raw JSON. Verify it shows real data.
6. Frontend styling: NOW make it pretty. Booking actions wired to real API.

By step 5, the data path is proven E2E. Styling in step 6 is risk-free.

### ✅ Correct behavior — claude-ops bootstrap layering (this session)

Layer 1 (DOCS): README + CLAUDE.md + foundational-brief + state.md + decisions.md + architecture.md + glossary.md. Reviewed and verified BEFORE protocols.

Layer 2 (FOUNDATION RULE): Rule #0 complete. Reviewed and verified. This is the BASE everything else depends on.

Layer 3 (STUBS): 14 protocol stubs + 1 playbook + 3 references. Just structure, no content yet.

Layer 4 (CONTENT FILL): expanding stubs into real protocols (chunks A/B/C, what's happening now).

If layer 2 (Rule #0) had been wrong, layer 4 would be wasted. Doing them in order ensures each builds on a verified foundation.

## Detection signals — am I going shotgun?

- ☐ I'm writing frontend code before the backend it calls exists
- ☐ I'm writing backend code before the DB schema it persists to exists
- ☐ I'm writing API contracts before the underlying logic works
- ☐ I'm styling UI before the data flows
- ☐ Multiple parallel files are being written without intermediate verification
- ☐ I'm at the "wire it all together" stage hoping it works

Any → STOP. Revert to layer-by-layer. Identify which layer isn't proven yet. Build that first.

## What this DOES NOT mean

- Not refuse to start frontend until backend is "production ready". Just need it to RESPOND to the frontend's calls reliably.
- Not require unit tests on every layer immediately. Manual verification (curl, ls, eyeball) is fine for early layers.
- Not block on perfectionism. Each layer needs to WORK, not be perfect.
- Not the only ordering. Some systems are better built top-down (UI mockups inform DB schema). Pick consciously, not by default.

## Enforcement loop

Before any non-trivial multi-layer build:

```
List the layers (3-5).
Identify the verification check for each.
Start at layer 1. Verify it works.
THEN layer 2. Verify integration.
Continue.

At any moment, if writing layer N+1: confirm layer N is proven. If not, return to N.
```

## Interaction with other protocols

- **`functional-first.md`**: layer-by-layer makes each layer functional in turn. Functional-first is "ugly-but-working before pretty"; layer-by-layer is "lower layers before upper".
- **`grand-scheme-first.md`**: the sketch reveals the layers. Layer-by-layer is how the sketch becomes code.
- **`chunk-size-protocol.md`**: each layer = potentially multiple chunks. Don't try to ship a whole layer in one shot if it's >200 lines.
