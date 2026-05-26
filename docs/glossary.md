# Glossary

Terms used across this repo and across operator's sessions. When in doubt, check here.

## Operator-specific

- **Juan** — primary operator (jlvelasquez-nomba on GitHub, marketing@thenomba.com).
- **Javi / Roca** — collaborator. Shares mkt-thenomba GitHub account.
- **TheNomba** — Juan's company (Spanish education startup, thenomba.com).
- **Carril A** — strict editorial rule: external content (videos, photos, refs) consumed for learning patterns only, NEVER reused in TheNomba output.
- **Carril B** — quote-clips with attribution + critical function under art. 32 LPI (Spain). NOT enabled by default.
- **compute-ocv-1** — Hetzner VM running OpenClaw bots + shared infra (private network 10.42.0.2, reachable via api-gateway 159.69.205.9 ProxyJump).
- **OpenClaw bots** — Tech, Marketing, Wizard, nombitabot (stopped). Each is an OpenClaw container with its own LLM session, mounted /shared volume.

## Repo + workflow

- **state.md** — current snapshot of a repo's state. Read first at session start.
- **doctor** — `make doctor` health check (~30s) per repo.
- **ADR** — Architecture Decision Record. Lives in `docs/decisions.md`.
- **Rule #0** — no fabrication. Highest priority protocol.
- **Tier 1 / 2 / 3** — how protocols load: 1 = always at session start, 2 = on trigger, 3 = on deep dive.

## Patterns observed

- **State drift** — what I remember vs what's actually in the repo / deployed.
- **Debug loop** — 3+ failed attempts with same error pattern; trigger for `error-loop-detection`.
- **Shotgun pattern** — attacking whole app at once instead of layer-by-layer.
- **Stub** — a protocol or playbook with title + outline but no full content yet.
