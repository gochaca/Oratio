# Oratio documentation

This folder is the source of truth for Oratio's product and technical direction. It is written to be readable by humans and reliably parsed and summarized by AI tooling.

## Index

| Doc | Purpose |
|---|---|
| [`vision.md`](./vision.md) | Why Oratio exists; the long-term north star |
| [`prd.md`](./prd.md) | What is being built, for whom, and why — scope and requirements |
| [`architecture.md`](./architecture.md) | System architecture and technical design |
| [`council.md`](./council.md) | The "council" deliberation model — Oratio's core mechanism |
| [`scoring.md`](./scoring.md) | Scoring and evaluation methodology |
| [`ux.md`](./ux.md) | UX principles, flows, and design direction |
| [`roadmap.md`](./roadmap.md) | Phased roadmap and milestones |
| [`decision-log.md`](./decision-log.md) | Running, timestamped record of product/architecture decisions |
| [`templates/`](./templates/) | The canonical template each doc type above is generated from |

## Metadata header schema

Every document in `docs/` (instances and templates) starts with a YAML frontmatter block using this schema:

```yaml
---
title: "Human-readable document title"
doc_type: prd | vision | architecture | council | scoring | ux | roadmap | decision-log
status: draft | active | approved | deprecated
owner: "Name or role responsible for keeping this current"
created: YYYY-MM-DD
last_updated: YYYY-MM-DD
version: 0.1.0
related_docs:
  - docs/other-doc.md
---
```

Field definitions:

- **title** — short, human-readable. Matches the doc's `# H1`.
- **doc_type** — one of the eight fixed types. Used by tooling to find "the PRD" etc. without relying on filename.
- **status** —
  - `draft`: actively being written, may change shape entirely.
  - `active`: current source of truth; changes should be incremental and logged.
  - `approved`: reviewed and signed off for a specific version/milestone; edits require a new decision log entry.
  - `deprecated`: superseded; kept for history, linked from its replacement.
- **owner** — a name or role, not a team. Someone accountable for the doc staying accurate.
- **created** / **last_updated** — ISO 8601 dates. `last_updated` changes on every substantive edit (not typo fixes).
- **version** — semantic-ish versioning for the *document*, not the product. Bump patch for clarifications, minor for new sections, major for structural rewrites.
- **related_docs** — relative paths to other docs this one depends on or is depended on by. Keeps the doc graph navigable without a separate index to maintain by hand.

## Why this structure

- **Consistent headers** let both humans and AI assistants answer "is this current? whose call is this? what does it depend on?" without reading the whole file.
- **One template per doc type** keeps every instance of that type shaped the same way, so diffs are meaningful and nothing gets buried in prose.
- **A single decision log** means decisions aren't scattered across PR descriptions and Slack threads — there is one place to check before re-opening a settled question.

## Current state

All docs in this repository are seeded from their templates and are `status: draft`. No application code exists yet — see [`roadmap.md`](./roadmap.md) for the plan to change that.
