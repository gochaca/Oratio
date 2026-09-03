---
title: "Oratio v0 — Architecture"
doc_type: architecture
status: draft
owner: "Adam (founding PM/eng)"
created: 2026-09-03
last_updated: 2026-09-03
version: 0.1.0
related_docs:
  - docs/prd.md
  - docs/decision-log.md
---

# Oratio v0 — Architecture

<!-- No application code exists yet. This document captures the current technical direction and known unknowns, not a final design. -->

## 1. Overview

Oratio v0 needs to: accept user input, orchestrate a multi-perspective ("council") deliberation across one or more LLM calls, apply a scoring rubric to the result, and persist the full record immutably. Nothing here is implemented yet.

## 2. Goals & constraints

- **Goal:** Get the smallest correct version of the council → scoring → record loop working before investing in UI polish or account infrastructure.
- **Constraint:** Solo/early-stage build — favor managed services and well-trodden tooling over custom infrastructure until there's a reason not to.
- **Constraint:** Cost — council deliberations likely require multiple LLM calls per session; cost per deliberation needs to be modeled before scaling usage.

> **Open question:** What's the acceptable cost ceiling per deliberation at launch?

## 3. High-level design

```
User input
   │
   ▼
[Council Orchestrator] ──► seat 1 (LLM call, persona A)
                        ──► seat 2 (LLM call, persona B)
                        ──► seat n (LLM call, persona N)
   │
   ▼
[Synthesis step] ──► combines seat outputs, surfaces disagreement
   │
   ▼
[Scoring engine] ──► applies rubric from scoring.md
   │
   ▼
[Record store] ──► immutable, versioned deliberation record
   │
   ▼
User-facing output (see ux.md)
```

## 4. Components

### 4.1 Council Orchestrator

- **Responsibility:** Given an input and a council configuration (`council.md`), run each seat's deliberation step (sequential or parallel — TBD) and collect raw outputs.
- **Owns data:** Ephemeral — seat prompts/responses for the in-progress session.
- **Talks to:** LLM provider(s), Synthesis step.
- **Key decisions:** None logged yet — see [`decision-log.md`](./decision-log.md).

### 4.2 Synthesis step

- **Responsibility:** Turn N seat outputs into a structured summary that preserves disagreement rather than averaging it away.
- **Owns data:** None persistent beyond the record it hands off.
- **Talks to:** Council Orchestrator (input), Scoring engine (output).

### 4.3 Scoring engine

- **Responsibility:** Apply the active rubric (`scoring.md`) to the synthesized deliberation and produce a scored, rationale-backed result.
- **Owns data:** None persistent beyond the record it hands off.
- **Talks to:** Synthesis step (input), Record store (output).

### 4.4 Record store

- **Responsibility:** Persist the full deliberation (input, per-seat outputs, synthesis, score, rationale) immutably and make it retrievable.
- **Owns data:** All deliberation records.
- **Talks to:** User-facing application layer.
- **Key decisions:** Storage technology not yet chosen.

> **Open question:** Storage technology and immutability mechanism (append-only log vs. versioned documents vs. event-sourced) — not yet decided. Log the decision in `decision-log.md` once made.

## 5. Data model

<!-- Draft sketch only — not a schema. -->

- **Deliberation**: id, created_at, input, council_id, status
- **SeatResponse**: deliberation_id, seat_id, perspective, response, order
- **Synthesis**: deliberation_id, summary, points_of_agreement, points_of_disagreement
- **Score**: deliberation_id, rubric_id, per_criterion_scores, aggregate_score, rationale

## 6. External dependencies

- LLM provider(s) for council seat generation — provider(s) TBD; design for provider-swap-ability given how young this space is.
- No other external dependencies identified yet.

## 7. Scalability & performance

<!-- Not yet a concern at v0 scale. Revisit once usage data exists. -->

## 8. Security & privacy

User input may include sensitive personal or business decisions. Data handling policy (retention, encryption at rest, who can access records) is **not yet defined** — must be resolved before any real user data is accepted. This is a blocker for launch, not a nice-to-have.

## 9. Failure modes & resilience

- LLM provider call fails for one seat → TBD: fail the whole deliberation, retry, or proceed with N-1 seats and flag it?
- Scoring produces an unexpected/malformed result → TBD: fallback behavior.

## 10. Alternatives considered

None evaluated yet — this is the first pass at the architecture.

## 11. Open questions

> **Open question:** Sequential vs. parallel seat execution — parallel is faster and cheaper on wall-clock time but sequential allows later seats to react to earlier ones (which may be desirable per `council.md` §3, or may be exactly the groupthink risk `council.md` §6 warns against).
> **Open question:** Do we build our own orchestration or use an existing agent/orchestration framework?

## 12. Related documents

- [`prd.md`](../prd.md)
- [`decision-log.md`](../decision-log.md)
