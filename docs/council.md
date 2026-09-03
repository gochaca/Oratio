---
title: "Oratio v0 — Default Council"
doc_type: council
status: draft
owner: "Adam (founding PM)"
created: 2026-09-03
last_updated: 2026-09-03
version: 0.1.0
related_docs:
  - docs/scoring.md
  - docs/architecture.md
---

# Oratio v0 — Default Council

## 1. Purpose

The default council is meant to give a general-purpose "second opinion" on a consequential question or decision, before any domain-specialized councils exist. It is the council FR2 (in `prd.md`) refers to for v0.

## 2. Composition

<!-- Draft seat design — needs review before implementation. Seats should be irreducible: removing one should visibly reduce the value of the deliberation. -->

| Seat | Perspective represented | Instructed to prioritize | Instructed to challenge |
|---|---|---|---|
| Advocate | The strongest honest case *for* the option/decision on the table | Upside, opportunity cost of inaction | Excessive caution |
| Skeptic | The strongest honest case *against* | Risk, failure modes, second-order effects | Unexamined optimism |
| Pragmatist | What's actually executable given real constraints (time, money, skill) | Feasibility, sequencing | Ideas that ignore constraints |
| Outside-view | How this looks to someone with no stake in the outcome | Base rates, comparable situations, blind spots specific to the user's framing | The user's own framing of the question |

> **Open question:** Is 4 seats the right number for v0, or does that make deliberations too slow/expensive relative to the value added? See `architecture.md` §2 cost constraint.

## 3. Deliberation process

1. All four seats receive the same input independently (no seat sees another seat's response) — a "blind first pass" to avoid anchoring.
2. Each seat produces a position: their view, key reasoning, and what would change their mind.
3. Synthesis step (see `architecture.md` §4.2) identifies points of agreement and disagreement across all four positions.
4. No second round in v0 — deliberation is single-pass. A second, cross-examination round is deferred (see `roadmap.md`).

## 4. Inputs

Each seat receives: the user's question/artifact verbatim, and its own seat instructions (perspective + priorities + what to challenge, from §2). Seats do **not** receive each other's identity or prior outputs in v0 (see §6).

## 5. Outputs

Per seat: a position (view + reasoning + what would change their mind). Combined: a synthesis (agreement/disagreement map) that feeds `scoring.md`.

## 6. Independence & anti-groupthink safeguards

- Blind first pass (§3.1) — no seat sees another's output before forming its own position.
- Seat instructions are written to be genuinely irreducible (§2) — reviewed periodically to check none have drifted into saying the same thing.
- If a future version adds multi-round deliberation, safeguards for that round (e.g. rotating which seat goes last) are **not yet designed** — flagged for `roadmap.md` Phase 2+.

## 7. Failure modes

- All four seats land in the same place → likely means either the question was genuinely uncontroversial, or the seat instructions have drifted toward redundancy. v0 does not yet distinguish these automatically — flagged as a known gap.
- One seat's output is degenerate (e.g. refuses, or ignores its instructions) → TBD handling, see `architecture.md` §9.

## 8. Governance

Changes to seat instructions in this default council require a PR reviewed against `prd.md` FR2/FR3 and, if the change is significant, a `decision-log.md` entry.

## 9. Open questions

> **Open question:** Should seat identities (Advocate/Skeptic/etc.) be shown to the end user, or only the synthesized output? Showing them may build trust; hiding them may reduce anchoring on "which seat do I agree with."
> **Open question:** How domain-general can one default council be before specialized councils (technical, financial, interpersonal) become necessary?

## 10. Related documents

- [`scoring.md`](../scoring.md) — how council output is turned into a score
- [`architecture.md`](../architecture.md) — how councils are implemented
