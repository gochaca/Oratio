---
title: "Oratio — Decision Log"
doc_type: decision-log
status: active
owner: "Adam (founding PM)"
created: 2026-09-03
last_updated: 2026-09-03
version: 0.1.0
related_docs:
  - docs/architecture.md
  - docs/prd.md
---

# Oratio — Decision Log

<!--
Running, append-mostly record of decisions. Newest entries at the top.
Never delete an entry; mark it Superseded and link forward instead.
See docs/templates/decision-log-template.md for the entry format.
-->

## Log

### D-001: Repository is documentation-only until Phase 0 docs are reviewed

- **Date:** 2026-09-03
- **Status:** accepted
- **Owner:** Adam
- **Context:** Starting Oratio from a documentation-first foundation, per the founding brief, rather than writing application code first.
- **Decision:** No application code will be added to this repository until the docs in `docs/` (vision, PRD, architecture, council, scoring, UX) have been reviewed and reach `status: active`, per `roadmap.md` Phase 0 exit criteria.
- **Alternatives considered:** Start with a throwaway prototype in parallel with docs. Rejected for now to keep the founding direction unambiguous and avoid the prototype quietly becoming the architecture by default.
- **Consequences:** Slower to see working software, but the core mechanism (council + scoring) gets designed deliberately rather than emerging accidentally from prototype code.
- **Superseded by:** —

### D-000: MIT license chosen

- **Date:** 2026-09-03
- **Status:** accepted
- **Owner:** Adam
- **Context:** Repository needed a license from the outset.
- **Decision:** MIT License.
- **Alternatives considered:** Apache 2.0 (more explicit patent grant, more ceremony); proprietary/no license (blocks early open collaboration). MIT chosen for simplicity while the project direction is still forming; can be revisited before any public launch.
- **Consequences:** Maximally permissive reuse; revisit if a patent-grant clause becomes important later.
- **Superseded by:** —
