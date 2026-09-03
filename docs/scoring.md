---
title: "Oratio v0 — Default Scoring Rubric"
doc_type: scoring
status: draft
owner: "Adam (founding PM)"
created: 2026-09-03
last_updated: 2026-09-03
version: 0.1.0
related_docs:
  - docs/council.md
  - docs/prd.md
---

# Oratio v0 — Default Scoring Rubric

## 1. Purpose

Converts the default council's (`council.md`) deliberation into an explicit, reproducible score that tells the user how settled or contested their question is — and why — rather than handing back a single unexplained recommendation.

## 2. Criteria

<!-- Draft — needs review, and ideally testing against real deliberations, before this is trusted. -->

| Criterion | Weight | Description | Evidence source |
|---|---|---|---|
| Convergence | 40% | How much the four council seats agree once reasoning is compared, not just conclusions | Synthesis agreement/disagreement map |
| Reasoning strength | 30% | How well-supported the strongest position is (specificity, use of evidence, acknowledgment of counterpoints) | Per-seat position text |
| Risk surfaced | 20% | Whether material risks/downsides were identified by at least one seat | Skeptic + Outside-view seat outputs |
| Actionability | 10% | Whether the synthesis gives the user something concrete to act on or investigate next | Synthesis output |

> **Open question:** Is "convergence" actually a good thing to score highly? High convergence could mean genuine consensus, or it could mean the question was too easy to be worth asking the council. Needs testing.

## 3. Scale

| Score | Meaning |
|---|---|
| 1 | Criterion essentially absent — e.g. no risk surfaced at all, or reasoning is assertion without support |
| 2 | Weak — present but shallow or generic |
| 3 | Adequate — present and specific to this question |
| 4 | Strong — specific, well-supported, and would hold up to challenge |
| 5 | Exceptional — specific, well-supported, and surfaces something the user likely hadn't considered |

## 4. Aggregation

```
aggregate_score = (convergence × 0.40) + (reasoning_strength × 0.30)
                + (risk_surfaced × 0.20) + (actionability × 0.10)
```

Aggregate is reported on the same 1-5 scale, to one decimal place, always shown alongside the per-criterion breakdown — never as a bare number (see `prd.md` risk table, row 2).

## 5. Calibration

<!-- Not yet built. Needs a small set of worked/gold-standard deliberations that multiple people (and, once implemented, multiple model runs) score independently and compare. -->

> **Open question:** Who calibrates this before launch, and against what set of test questions?

## 6. Disagreement handling

If per-seat positions in the source deliberation are highly polarized (per Convergence scoring low), the scoring output should say so explicitly rather than picking a side — the low convergence score itself is the signal, and the synthesis should state the actual points of divergence.

## 7. Worked example

<!-- TBD — needs a real run through the council to populate. Placeholder structure below. -->

- **Input:** <example question>
- **Per-criterion scores:** Convergence: _, Reasoning strength: _, Risk surfaced: _, Actionability: _
- **Aggregate:** _
- **Resulting record:** <link or description once generated>

## 8. Limitations

- This rubric scores the *quality of the deliberation*, not the correctness of any real-world outcome — a high score does not guarantee the decision will turn out well.
- Not designed for adversarial/red-team use cases (e.g. scoring someone else's argument to "win" a debate) — that would need a different rubric.

## 9. Open questions

> **Open question:** Should weights be configurable per council, or fixed for the default rubric?

## 10. Related documents

- [`council.md`](../council.md) — what produces the input this rubric scores
- [`prd.md`](../prd.md)
