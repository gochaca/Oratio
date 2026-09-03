---
title: "Oratio v0 — Core Flow UX"
doc_type: ux
status: draft
owner: "Adam (founding PM)"
created: 2026-09-03
last_updated: 2026-09-03
version: 0.1.0
related_docs:
  - docs/prd.md
  - docs/vision.md
---

# Oratio v0 — Core Flow UX

## 1. Summary

Covers the primary v0 flow: a user submits a question, watches/waits for a council deliberation, and receives a scored, structured result they can trust and return to. No visual design exists yet — this is flow and content direction only.

## 2. Design principles

<!-- Draws on vision.md's guiding principles, made concrete for UX. -->

- **Show the disagreement, don't hide it** — the UI should make it easy to see where council seats diverged, not just the synthesized headline.
- **Never present the score as an answer** — frame output as "here's what the council found," not "here's what you should do" (see `vision.md` §5, "not a decision-maker").
- **Make the wait legible** — deliberation isn't instant; the user should understand what's happening, not stare at a blank spinner.

## 3. Primary user flow

1. User submits a question or artifact.
2. (If multiple councils exist) user selects a council, or system defaults to the default council (`council.md`).
3. System runs the deliberation; UI communicates progress (e.g. which seats have responded).
4. User sees the result: synthesis, per-seat positions (expandable), score with per-criterion breakdown and rationale.
5. Record is saved automatically; user can return to it later.

> **Open question:** Does the user watch seats respond in near-real-time, or only see the completed result? Real-time is more engaging but couples UX to `architecture.md`'s sequential-vs-parallel execution decision.

## 4. Key screens / states

### 4.1 Submission

- **Purpose:** Capture the user's question/artifact with enough context for the council to work with.
- **Key elements:** Input field, (optional) council selector, submit action.
- **Entry points:** App home, "new deliberation" action.
- **Exit points:** Deliberation-in-progress state.

### 4.2 Deliberation in progress

- **Purpose:** Keep the user informed while seats respond.
- **Key elements:** Progress indicator per seat (TBD exact treatment pending real-time question above).
- **Entry points:** Submission.
- **Exit points:** Result screen.

### 4.3 Result

- **Purpose:** Present synthesis, per-seat positions, and score in a way that's scannable but not oversimplified.
- **Key elements:** Headline synthesis, agreement/disagreement map, expandable per-seat positions, score + per-criterion breakdown + rationale.
- **Entry points:** Deliberation in progress (on completion), record history.
- **Exit points:** Record history, new submission.

### 4.4 Record history

- **Purpose:** Let users find and revisit past deliberations (FR5 in `prd.md`).
- **Key elements:** List of past deliberations, TBD sort/filter.
- **Entry points:** App navigation.
- **Exit points:** Result screen (for a selected record).

## 5. Edge cases & empty/error states

- No past deliberations yet (empty history state).
- A council seat fails to respond (see `architecture.md` §9 — UX treatment depends on the resolved failure-handling decision).
- User submits something outside intended scope (e.g. clearly not a decision/question) — TBD handling.

## 6. Accessibility

<!-- TBD in detail once visual design exists. Baseline commitment: keyboard-navigable, screen-reader-friendly labeling of per-seat and per-criterion content, sufficient color contrast for any score visualization. -->

## 7. Content & tone

Council and score explanations must read as informative, not authoritative — avoid phrasing like "Oratio recommends"; prefer "the council's strongest case for / against was...". This directly supports `vision.md` guiding principle 1 (deliberation over automation) and the risk noted in `prd.md` §10.

## 8. Metrics tied to this flow

<!-- Ties to prd.md §9, which is itself still TBD. Revisit together. -->

## 9. Open questions

> **Open question:** Should per-seat positions be collapsed by default (favoring the synthesis) or expanded (favoring transparency)?

## 10. Related documents

- [`prd.md`](../prd.md)
- [`vision.md`](../vision.md)
