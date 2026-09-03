# Oratio

> AI-native decision & argumentation platform — Oratio convenes a structured "council" of perspectives to stress-test ideas, score them against explicit criteria, and turn deliberation into a documented, auditable decision trail.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Docs](https://img.shields.io/badge/docs-in%20progress-blue.svg)](./docs/README.md)
[![Status](https://img.shields.io/badge/status-pre--implementation-lightgrey.svg)](./docs/roadmap.md)

## Status

This repository is currently **documentation-only**. It exists to establish a shared, AI-friendly foundation — product vision, requirements, architecture, UX direction, evaluation methodology, and a running decision log — before any application code is written. See [`docs/roadmap.md`](./docs/roadmap.md) for what comes next.

## What is Oratio?

Oratio is being built as an AI product that helps individuals and teams reason through hard decisions and arguments by convening a **council** of distinct AI perspectives, evaluating the resulting positions against an explicit **scoring** rubric, and preserving the outcome as a durable, reviewable record. The specifics of the product are still being defined — see [`docs/vision.md`](./docs/vision.md) and [`docs/prd.md`](./docs/prd.md) for the current thinking and open questions.

## Repository layout

```
oratio/
├── README.md                  # you are here
├── LICENSE                    # MIT
├── CONTRIBUTING.md            # how to propose changes, incl. to docs
├── CODE_OF_CONDUCT.md
├── .github/                   # issue & PR templates
└── docs/
    ├── README.md               # documentation index & metadata schema
    ├── vision.md                # why Oratio exists, long-term north star
    ├── prd.md                   # product requirements
    ├── architecture.md          # system architecture & technical design
    ├── council.md               # the "council" deliberation model
    ├── scoring.md                # scoring / evaluation methodology
    ├── ux.md                     # UX principles & flows
    ├── roadmap.md                # phased roadmap
    ├── decision-log.md           # running architecture/product decision record
    └── templates/                 # reusable templates for the doc types above
```

## Documentation-first, AI-friendly by design

Every document in this repository:

- Starts with a consistent YAML metadata header (see [`docs/README.md`](./docs/README.md#metadata-header-schema)) so both humans and AI tooling can parse status, ownership, and freshness at a glance.
- Follows a fixed section structure per doc type, defined by the matching file in [`docs/templates/`](./docs/templates/).
- Is written to be safely summarized, diffed, and reasoned about by an LLM collaborator — short paragraphs, explicit lists, no buried assumptions.

## Getting started

1. Read [`docs/vision.md`](./docs/vision.md) for context on why this exists.
2. Read [`docs/prd.md`](./docs/prd.md) for what's currently in/out of scope.
3. Read [`docs/architecture.md`](./docs/architecture.md) before proposing any technical direction.
4. Check [`docs/decision-log.md`](./docs/decision-log.md) before re-litigating a decision that's already been made.
5. See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for how to propose changes.

## License

MIT — see [`LICENSE`](./LICENSE).
