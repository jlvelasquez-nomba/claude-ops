# References — verified primary sources

Per Rule #0, every external claim in this repo must be backed by a primary source. This folder is the canonical list of approved sources Claude is allowed to cite.

## Files

| File | Purpose |
|---|---|
| [developers-canonical.md](./developers-canonical.md) | ~15-20 individual developers + verified online presence (template + TODO list) |
| [companies-canonical.md](./companies-canonical.md) | Engineering orgs whose blogs/papers/repos can be cited (template + TODO list) |
| [primary-sources.md](./primary-sources.md) | Specific documents (RFCs, papers, books) referenced across protocols (template + TODO list) |

## Why all 3 are empty templates (and that's correct)

Per Rule #0, I cannot fabricate sources. Each entry must be verified via WebFetch (or operator manual confirm) before promotion to canonical.

Workflow:
1. Operator allocates a session for references curation
2. Claude takes 1 candidate at a time
3. WebFetch the candidate's primary URLs
4. If verified → write entry following template
5. If unverifiable → keep as TODO, do not extrapolate
6. Operator reviews each entry
7. Promoted entries enter canonical list

## Quality bar

Better 5 verified entries than 50 mixed verified+fabricated. Curated > comprehensive.

## When can Claude cite from this folder?

Only when an entry is in CANONICAL section (verified + operator-ratified). TODO entries are NOT cite-able — they're placeholders for future verification work.
