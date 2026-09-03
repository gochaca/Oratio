---
title: "<System/Component Name> — Architecture"
doc_type: architecture
status: draft
owner: "TBD"
created: YYYY-MM-DD
last_updated: YYYY-MM-DD
version: 0.1.0
related_docs:
  - docs/prd.md
  - docs/decision-log.md
---

# <System/Component Name> — Architecture

## 1. Overview

<!-- 2-3 sentences: what this system does and its place in the larger product. -->

## 2. Goals & constraints

<!-- Technical goals (scalability, latency, cost) and hard constraints (compliance, existing systems, team skillset). -->

## 3. High-level design

<!-- A diagram (ASCII, mermaid, or linked image) plus a short walkthrough of major components and data flow. -->

```
<diagram placeholder>
```

## 4. Components

<!-- One subsection per major component. -->

### 4.1 <Component name>

- **Responsibility:**
- **Owns data:**
- **Talks to:**
- **Key decisions:** (link to decision-log.md entries)

## 5. Data model

<!-- Core entities and their relationships. Not a full schema — just enough to reason about the system. -->

## 6. External dependencies

<!-- Third-party services, APIs, models. Include what happens if each is unavailable. -->

## 7. Scalability & performance

<!-- Expected load, bottlenecks, and how the design accommodates growth. -->

## 8. Security & privacy

<!-- Data sensitivity, auth model, isolation boundaries. -->

## 9. Failure modes & resilience

<!-- What breaks, how it's detected, how it degrades gracefully. -->

## 10. Alternatives considered

<!-- Options rejected, and why. Full rationale goes in decision-log.md; summarize here. -->

## 11. Open questions

> **Open question:** <question>

## 12. Related documents

- [`prd.md`](../prd.md)
- [`decision-log.md`](../decision-log.md)
