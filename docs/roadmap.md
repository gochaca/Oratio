---
title: "Oratio — Roadmap"
doc_type: roadmap
status: draft
owner: "Adam (founding PM)"
created: 2026-09-03
last_updated: 2026-09-03
version: 0.1.0
related_docs:
  - docs/vision.md
  - docs/prd.md
---

# Oratio — Roadmap

## 1. Sequencing principles

De-risk the core mechanism (council → scoring → durable record) before investing in UI polish, multiple councils, or account/collaboration features. If the core loop doesn't produce output people trust and return to, nothing built on top of it matters.

## 2. Phases

### Phase 0: Foundation (this repository)

- **Objective:** Establish shared, AI-friendly documentation before any code — vision, PRD, architecture, council, scoring, UX, decision log.
- **Scope:** This repo's `docs/` folder and templates. No application code.
- **Exit criteria:** All docs in `docs/` reach `status: active` (reviewed, not just drafted) and open questions critical to starting implementation are resolved and logged in `decision-log.md`.
- **Status:** in progress

### Phase 1: Prove the core loop

- **Objective:** A single working path from input → default council (`council.md`) → default scoring (`scoring.md`) → durable record, usable by one person (likely the founder) end to end.
- **Scope:** Minimal interface (could be CLI or barebones UI), one council, one rubric, one storage mechanism. No accounts, no multi-user, no polish.
- **Exit criteria:** 10+ real deliberations run, reviewed by the founder for whether the council output and score felt genuinely useful and non-redundant across seats.
- **Status:** not started

### Phase 2: First external users

- **Objective:** Validate the core loop with people outside the founding team.
- **Scope:** TBD — depends on Phase 1 learnings and the still-open B2B-vs-B2C question in `vision.md`.
- **Exit criteria:** TBD.
- **Status:** not started

### Phase 3: Expand councils & scoring

- **Objective:** Move beyond a single default council/rubric toward domain-specific configurations, if Phase 2 shows demand for it.
- **Scope:** TBD.
- **Exit criteria:** TBD.
- **Status:** not started

## 3. Milestone table

| Milestone | Phase | Target | Status | Notes |
|---|---|---|---|---|
| Repository scaffolded (this commit) | 0 | 2026-09-03 | Done | Documentation-only |
| All Phase 0 docs reach `status: active` | 0 | TBD | Not started | Blocks Phase 1 kickoff |
| First end-to-end deliberation run | 1 | TBD | Not started | Depends on architecture storage decision |

## 4. Explicitly deferred

- Multi-round council deliberation (cross-examination between seats) — deferred past v0 per `council.md` §3.
- Custom/user-defined councils — deferred past v0 per `prd.md` §4.
- Any collaboration/multi-user features — not scoped until Phase 2+ direction is set.

## 5. Dependencies & sequencing risks

- Phase 1 cannot start until `architecture.md`'s storage and LLM-provider open questions are resolved.
- Phase 2 direction depends on resolving the B2B-vs-B2C open question in `vision.md` — this could reorder priorities significantly.

## 6. Related documents

- [`vision.md`](../vision.md)
- [`prd.md`](../prd.md)
- [`decision-log.md`](../decision-log.md)
