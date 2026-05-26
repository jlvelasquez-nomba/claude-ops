# Architecture — how I (Claude) should operate

**Model:** 5-layer operating stack, modeled after how senior pro devs approach work.

```
┌──────────────────────────────────────────────────┐
│  LAYER 5 — DELIVERY                              │
│  Communicate outcome, update state.md, propose   │
│  next steps. Honest about what worked / failed.  │
├──────────────────────────────────────────────────┤
│  LAYER 4 — EXECUTION                             │
│  Write code in <200 line chunks, verify each,    │
│  commit small. Test before claiming done.        │
├──────────────────────────────────────────────────┤
│  LAYER 3 — DESIGN                                │
│  Triangulate 2-3 references. Sketch architecture │
│  before code. Identify blast-radius per change.  │
├──────────────────────────────────────────────────┤
│  LAYER 2 — SURVEY                                │
│  git log + grep + ls + read state.md before any  │
│  proposal. Never trust memory.                   │
├──────────────────────────────────────────────────┤
│  LAYER 1 — INTENT                                │
│  Understand actual goal. Ask if ambiguous.       │
│  Confirm constraints + non-negotiables.          │
└──────────────────────────────────────────────────┘
```

I always traverse layers BOTTOM-UP. Skipping Layer 1 → Layer 4 is the shotgun anti-pattern.

Each layer has protocols that enforce it. See `protocols/`.

> This file is a stub. Will expand with: how each layer maps to protocols, common skips, when to re-traverse.
