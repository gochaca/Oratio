---
title: "<Council Configuration Name>"
doc_type: council
status: draft
owner: "TBD"
created: YYYY-MM-DD
last_updated: YYYY-MM-DD
version: 0.1.0
related_docs:
  - docs/scoring.md
  - docs/architecture.md
---

# <Council Configuration Name>

<!--
A "council" is a configured set of distinct perspectives (AI personas, model
configurations, and/or human roles) that deliberate on a question or artifact
together. Use this template to define one council configuration — the default
council, or a specialized one for a specific domain (e.g. legal review,
technical design review).
-->

## 1. Purpose

<!-- What kind of question or artifact is this council meant to evaluate? -->

## 2. Composition

<!-- Each seat on the council: its role, perspective/bias it's meant to represent, and what makes it distinct from the others. Councils should have irreducible, non-redundant perspectives. -->

| Seat | Perspective represented | Instructed to prioritize | Instructed to challenge |
|---|---|---|---|
| | | | |

## 3. Deliberation process

<!-- The sequence: how seats respond, whether they see each other's responses, how many rounds, how disagreement is surfaced (not resolved — resolution is scoring.md's job). -->

1. <step>

## 4. Inputs

<!-- What the council is given: the question/artifact, context, constraints. What it is explicitly NOT given (to avoid anchoring). -->

## 5. Outputs

<!-- The structured output of a council session — e.g. per-seat position, key disagreements, a synthesis. Link to scoring.md for how outputs become a score. -->

## 6. Independence & anti-groupthink safeguards

<!-- Mechanisms preventing seats from converging prematurely or one seat dominating (e.g. blind first pass, rotating devil's advocate, perspective diversity checks). -->

## 7. Failure modes

<!-- What it looks like when a council session goes wrong (e.g. all seats agree suspiciously fast, one perspective dominates) and how that's detected. -->

## 8. Governance

<!-- Who can add/remove/modify a seat's instructions, and what review that requires. -->

## 9. Open questions

> **Open question:** <question>

## 10. Related documents

- [`scoring.md`](../scoring.md) — how council output is turned into a score
- [`architecture.md`](../architecture.md) — how councils are implemented
