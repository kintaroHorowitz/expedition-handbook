# Expedition Handbook Decision Log

## Purpose

This append-oriented log records durable technical and governance decisions. It
does not own expedition strategy, issue status, implementation instructions, or
release history.

## Decision process

Significant decisions are proposed before implementation and approved by the
user. A record may be proposed, accepted, superseded, or rejected. Superseding a
record creates a new identifier and links both records; history is not rewritten.

## Template

### ADR-XXXX — Title

- **Status:** Proposed
- **Date:** YYYY-MM-DD
- **Context:** What requires a decision.
- **Decision:** The approved choice.
- **Consequences:** Benefits, costs, constraints, and follow-up work.
- **Links:** Relevant issue, proposal, commit, or superseding record.

## Decision index

- ADR-0001 — Use MkDocs Material
- ADR-0002 — Use Linear for backlog authority
- ADR-0003 — Use Codex as implementation engineer
- ADR-0004 — Publish a mobile-first handbook
- ADR-0005 — Use a hybrid information model
- ADR-0006 — Give information one canonical owner
- ADR-0007 — Separate journals from generated reports
- ADR-0008 — Support multiple expeditions through stable namespaces
- ADR-0009 — Defer Garmin integration

## Records

### ADR-0001 — Use MkDocs Material

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** The project needs a maintainable static handbook with strong mobile navigation and Markdown support.
- **Decision:** Build and publish the handbook with MkDocs Material.
- **Consequences:** Published pages follow MkDocs conventions and strict builds become a required validation step.
- **Links:** CDB-18; `mkdocs.yml`.

### ADR-0002 — Use Linear for backlog authority

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** Work needs one authoritative location for issue scope, status, and acceptance criteria.
- **Decision:** Use Linear as the backlog and acceptance-criteria source of truth.
- **Consequences:** Repository documents may link to issues but must not duplicate live issue state.
- **Links:** CDB-18; `CONTRIBUTING.md`.

### ADR-0003 — Use Codex as implementation engineer

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** Repository implementation needs an explicit role distinct from expedition strategy ownership.
- **Decision:** Codex owns scoped repository edits, scripts, configuration, validation, and technical refactoring.
- **Consequences:** Codex escalates expedition decisions and significant unapproved designs instead of changing them silently.
- **Links:** CDB-18; `AGENTS.md`.

### ADR-0004 — Publish a mobile-first handbook

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** The handbook will commonly be read on a phone during training and travel.
- **Decision:** Treat mobile readability as a primary content and navigation constraint.
- **Consequences:** Pages favor concise sections, narrow layouts, short navigation labels, and readable checklists.
- **Links:** CDB-18; `AGENTS.md`.

### ADR-0005 — Use a hybrid information model

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** Narrative guidance, reusable metrics, and derived summaries have different maintenance needs.
- **Decision:** Use authored Markdown for narrative, YAML or JSON for reusable facts and metrics, and generated artifacts for derived views.
- **Consequences:** Future validation and generation must preserve the boundaries described in `ARCHITECTURE.md`.
- **Links:** CDB-18; `ARCHITECTURE.md`.

### ADR-0006 — Give information one canonical owner

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** Manually maintained copies drift and make automation unsafe.
- **Decision:** Assign every item one canonical owner and make other appearances references or reproducible derivatives.
- **Consequences:** Duplication triggers an ownership review and scoped refactor proposal rather than silent rewriting.
- **Links:** CDB-18; `ARCHITECTURE.md`.

### ADR-0007 — Separate journals from generated reports

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** Raw dated observations and aggregated summaries require different correction and authority rules.
- **Decision:** Store raw chronological entries in `journal/` and generated summaries with provenance in `reports/`.
- **Consequences:** Reports never become independent sources and corrections are made to canonical inputs.
- **Links:** CDB-18; `ARCHITECTURE.md`.

### ADR-0008 — Support multiple expeditions through stable namespaces

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** The repository must support Tour des Écrins, GR20, and later expeditions without copying shared knowledge.
- **Decision:** Separate shared content from expedition-specific content and reference expeditions with stable identifiers.
- **Consequences:** Migrating the existing handbook hierarchy requires a separate approved issue.
- **Links:** CDB-18; `ARCHITECTURE.md`.

### ADR-0009 — Defer Garmin integration

- **Status:** Accepted
- **Date:** 2026-08-05
- **Context:** Useful activity fields and reconciliation needs are not yet established by sustained manual records.
- **Decision:** Postpone direct Garmin import and do not design speculative Garmin schemas.
- **Consequences:** Reconsider integration only after several months of manual data reveal stable requirements.
- **Links:** CDB-18; `ROADMAP.md`.
