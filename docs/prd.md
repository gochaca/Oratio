---
title: "Oratio v0 — PRD"
doc_type: prd
status: draft
owner: "Adam (founding PM)"
created: 2026-09-03
last_updated: 2026-09-03
version: 0.1.0
related_docs:
  - docs/vision.md
  - docs/architecture.md
  - docs/ux.md
---

# Oratio v0 — PRD

## 1. Summary

Oratio takes a question or artifact from a user, runs it through a configured "council" of distinct AI perspectives, scores the resulting deliberation against an explicit rubric, and returns a structured, durable record the user can trust and revisit. This PRD covers the smallest end-to-end version of that loop (v0), not the full product.

## 2. Problem statement

<!-- Draft — replace with evidence (interviews, data) once available. -->
People making consequential decisions rarely get structured, multi-perspective input on demand, and even when they do (asking colleagues, a single AI chat), there's no consistent rubric applied and no durable record of what was considered and why.

## 3. Goals

- G1: A user can submit a question/artifact and receive a council deliberation with a scored, structured output.
- G2: Every deliberation produces a record that persists and can be revisited later.
- G3: The council mechanism visibly represents more than one distinct perspective — disagreement is preserved, not smoothed over.

## 4. Non-goals

- Not building a general chat interface competing with existing AI assistants.
- Not automating the final decision — v0 does not take actions on the user's behalf.
- Not supporting arbitrary custom council configurations in v0 — start with a small number of fixed, well-designed councils.

## 5. Users & use cases

| Persona | Scenario | Outcome they want |
|---|---|---|
| Individual decision-maker | Facing a consequential personal/professional choice | A structured second (and third, fourth) opinion with visible reasoning |
| Technical lead | Choosing between architectural approaches | Documented tradeoff analysis they can point to later |

> **Open question:** Confirm/replace these personas with real target users once identified (see `vision.md` open question on B2B vs B2C).

## 6. Requirements

### 6.1 Functional requirements

- FR1 (MUST): User can submit a question or artifact as input to a council deliberation.
- FR2 (MUST): System runs the input through a defined council (see [`council.md`](./council.md)) and produces per-seat positions.
- FR3 (MUST): System scores the deliberation using a defined rubric (see [`scoring.md`](./scoring.md)) and surfaces the score with rationale.
- FR4 (MUST): The full deliberation (inputs, per-seat positions, score, synthesis) is saved as a durable, retrievable record.
- FR5 (SHOULD): User can view past deliberation records.
- FR6 (MAY): User can annotate a past record with what actually happened / what they decided.

### 6.2 Non-functional requirements

- NFR1: Deliberation records must not be silently mutable after creation — edits create a new version, not an overwrite (supports "the record outlives the session").
- NFR2: Response time for a council deliberation should be communicated to the user (this is not expected to be instant) — no requirement finalized yet.
- NFR3: Privacy — user-submitted questions/artifacts may be sensitive; data handling requirements TBD pending architecture review.

## 7. UX summary

See [`ux.md`](./ux.md). Core flow: submit input → select or default to a council → view live/complete deliberation → view score + synthesis → record is saved automatically.

## 8. Dependencies

- [`council.md`](./council.md) must define at least one working council configuration before FR2 can be implemented.
- [`scoring.md`](./scoring.md) must define at least one working rubric before FR3 can be implemented.
- [`architecture.md`](./architecture.md) must define the storage model before FR4/NFR1 can be implemented.

## 9. Metrics & success criteria

<!-- TBD — no targets set until v0 ships and baseline data exists. -->

> **Open question:** What's the primary activation metric — first completed deliberation, or return usage (second deliberation within N days)?

## 10. Risks & mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Council perspectives converge and feel like one voice repeated | Medium | High — undermines core value prop | Design councils per `council.md` §6 (anti-groupthink safeguards); test for this explicitly |
| Scoring rubric feels arbitrary/unearned to users | Medium | High | Rubric must show its work (see `scoring.md` §7 worked example); surface rationale, not just a number |
| Users treat output as a final answer rather than input to their own judgment | Medium | Medium | UX must frame output as informative, not directive (see `ux.md` §7 content & tone) |

## 11. Open questions

> **Open question:** Fixed councils only in v0, or does the user pick from a small preset list?
> **Open question:** What does "artifact" mean concretely for v0 — text only, or documents/links too?

## 12. Related documents

- [`vision.md`](../vision.md)
- [`architecture.md`](../architecture.md)
- [`ux.md`](../ux.md)
- [`roadmap.md`](../roadmap.md)
