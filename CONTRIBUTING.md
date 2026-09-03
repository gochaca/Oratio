# Contributing to Oratio

Oratio is currently in its **documentation-first** phase — there is no application code yet, so all contributions right now are to `docs/`. This document covers how to propose changes safely.

## Ground rules

- **Docs before code.** No application code lands until the PRD, architecture, and UX docs it depends on exist and are marked `status: active` (see [`docs/README.md`](./docs/README.md#metadata-header-schema)).
- **Every doc keeps its metadata header current.** Bump `last_updated` and `version` on any substantive edit.
- **Decisions get logged.** Any change that reverses, supersedes, or meaningfully narrows a prior decision must add an entry to [`docs/decision-log.md`](./docs/decision-log.md) using [`docs/templates/decision-log-template.md`](./docs/templates/decision-log-template.md).
- **Templates are the source of truth for structure.** If a doc's shape needs to change, change its template in `docs/templates/` first, then propagate.

## Proposing a documentation change

1. Open an issue using the "Documentation change" template (see [`.github/ISSUE_TEMPLATE`](./.github/ISSUE_TEMPLATE)) describing the gap or problem — not the fix.
2. Branch from `main`: `docs/<short-description>`.
3. Edit the relevant file(s) in `docs/`, keeping the existing section structure from that doc's template.
4. Update the metadata header (`last_updated`, `version`, `status` if it changed).
5. Open a PR using the pull request template. Link the issue.
6. At least one other maintainer approves before merge. For decisions with product-wide impact, also add a `decision-log.md` entry in the same PR.

## Proposing a new document type

If a new recurring document type is needed (beyond PRD, vision, architecture, council, scoring, UX, roadmap, decision log):

1. Draft a template in `docs/templates/<type>-template.md` following the existing metadata header schema.
2. Get it reviewed like any other PR.
3. Only then create the first instance document from it.

## Style

- Write for a mixed human + AI-assistant audience: short paragraphs, explicit lists, no unstated assumptions.
- Prefer linking to another doc over restating its content.
- Mark open questions explicitly as `> **Open question:** ...` rather than leaving them implicit.
- Use `TBD` (not blank sections) for anything intentionally undecided, so it's greppable.

## Future: application code

Once the first architecture and PRD sections reach `status: active`, this file will be updated with code contribution guidelines (branching model, test requirements, CI, review process). That section is intentionally `TBD` today — see [`docs/roadmap.md`](./docs/roadmap.md).
