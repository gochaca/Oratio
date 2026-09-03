---
title: "Oratio — Vision"
doc_type: vision
status: draft
owner: "Adam (founding PM)"
created: 2026-09-03
last_updated: 2026-09-03
version: 0.1.0
related_docs:
  - docs/prd.md
---

# Oratio — Vision

## 1. Why this exists

Important decisions and arguments are usually reasoned through alone, or with whoever happens to be in the room — not with a deliberately diverse set of perspectives, and rarely with a documented trail of how the conclusion was reached. Oratio exists to make structured, multi-perspective deliberation as easy to invoke as asking a single question, and to leave behind a record that can be trusted, audited, and revisited later.

## 2. Who it's for

<!-- Draft — narrow this once real user research exists. -->
Individuals and small teams facing a consequential decision or argument who want it stress-tested from more than one angle before committing — e.g. a technical lead choosing an architecture, a founder evaluating a strategic bet, a policy team weighing a tradeoff.

> **Open question:** Is the initial wedge B2B (teams making org decisions) or B2C (individuals making personal/professional decisions)? This materially changes the PRD and UX.

## 3. North star

If Oratio fully succeeds, "run it through the council" becomes a normal step before any consequential decision — as routine as writing something down — because doing so reliably surfaces blind spots and produces a record worth trusting later.

## 4. Guiding principles

1. **Deliberation over automation** — Oratio's job is to surface and structure disagreement, not to silently resolve it or hand back a single confident answer.
2. **Explicit over implicit** — every score, every synthesis, every "the council recommends X" must trace back to a visible rationale, not a black box.
3. **Diversity of perspective is engineered, not assumed** — a council that quietly converges to one viewpoint has failed, regardless of how confident the output sounds.
4. **The record outlives the session** — every deliberation produces something durable and reviewable (see [`decision-log.md`](./decision-log.md)), not just a chat transcript.
5. **Honest about uncertainty** — Oratio should say "the council disagreed and here's why" as readily as it says "the council agreed."

## 5. What this is not

- Not a single-model chatbot with a "council" marketing wrapper — the multi-perspective mechanism and scoring rubric are the product, not decoration.
- Not a decision-*maker* — Oratio informs and documents; it does not remove human accountability for the final call.
- Not (initially) a general-purpose debate/entertainment product — the target is decisions people actually have to make and stand behind.

## 6. Success, at the vision level

- People return to Oratio for decisions that matter to them, not just to try it once.
- Deliberation records get referenced later ("here's what the council flagged") rather than forgotten immediately after the decision is made.
- Users report the council surfaced something they hadn't considered.

## 7. Open questions

> **Open question:** What is the smallest end-to-end version of "council → scoring → record" that proves the core loop works, before any UI investment?
> **Open question:** Who owns council seat design — is that a product/content function, a research function, or both?

## 8. Related documents

- [`prd.md`](../prd.md) — near-term requirements derived from this vision
- [`roadmap.md`](../roadmap.md) — how the vision is sequenced into milestones
