# Protocols index

Each protocol = one failure mode I commit, codified as algorithmic rule. Status:

| Protocol | Status | Trigger | Priority |
|---|---|---|---|
| [no-fabrication.md](./no-fabrication.md) | ✅ COMPLETE | Every output | **RULE #0** |
| [error-loop-detection.md](./error-loop-detection.md) | 🟡 STUB | 3+ failed attempts same error | high |
| [memory-vs-reality.md](./memory-vs-reality.md) | 🟡 STUB | About to assume based on memory | high |
| [survey-before-building.md](./survey-before-building.md) | 🟡 STUB | About to write code in a repo | high |
| [blast-radius.md](./blast-radius.md) | 🟡 STUB | About to make destructive change | high |
| [pushback-protocol.md](./pushback-protocol.md) | 🟡 STUB | User idea conflicts with evidence | medium |
| [compaction-ritual.md](./compaction-ritual.md) | 🟡 STUB | Context >50 messages | medium |
| [mode-separation.md](./mode-separation.md) | 🟡 STUB | Switching explore ↔ execute | medium |
| [postmortem-ritual.md](./postmortem-ritual.md) | 🟡 STUB | Something broke unexpectedly | high |
| [grand-scheme-first.md](./grand-scheme-first.md) | 🟡 STUB | About to design feature without big picture | medium |
| [triangulate-references.md](./triangulate-references.md) | 🟡 STUB | About to propose novel architecture | medium |
| [layer-by-layer.md](./layer-by-layer.md) | 🟡 STUB | Building user-facing surface | medium |
| [functional-first.md](./functional-first.md) | 🟡 STUB | Building UX before backend works | medium |
| [realistic-ambitious.md](./realistic-ambitious.md) | 🟡 STUB | Drifting between cautious and YOLO | low |
| [chunk-size-protocol.md](./chunk-size-protocol.md) | 🟡 STUB | About to generate >200 lines | medium |

Total: **1 complete + 14 stubs = 15 protocols planned.**

Stubs become full content when:
- A real failure mode hits in a session AND that protocol applies → expand the stub with the case study, then continue with the work.
- OR a dedicated writing session targets a specific stub.

NEVER add new protocols based on theoretical concerns. Only based on REAL failure modes committed.
