# Expedition Handbook Architecture

## Purpose and scope

This document defines the target repository architecture and information
ownership model. It does not define agent behaviour, contribution procedure, or
expedition strategy. CDB-18 documents the target; it does not migrate the current
handbook hierarchy or implement automation.

## Architectural principles

- Use a hybrid model: authored Markdown for narrative knowledge, YAML or JSON for
  reusable facts and metrics, and generated artifacts for derived views.
- Give every item exactly one canonical owner.
- Treat generated content as reproducible output, never an independent source.
- Separate shared knowledge from expedition-specific content using stable
  expedition identifiers.
- Keep source formats understandable without specialized tooling.
- Automate established workflows only after their useful inputs are understood.

## Phase A — Governance architecture

Root governance files have distinct responsibilities:

- `AGENTS.md` owns AI behaviour, authority, and completion standards.
- `ARCHITECTURE.md` owns repository structure, information flow, and boundaries.
- `CONTRIBUTING.md` owns branch, commit, validation, review, and issue procedure.
- `DECISIONS.md` owns approved technical and governance decision records.
- `ROADMAP.md` owns broad, non-binding technical capability direction.
- `CHANGELOG.md` owns release-level summaries of delivered changes.

These files cross-reference one another rather than restating rules. `README.md`
remains the short entry point for the project and local setup.

## Phase B — Information architecture

### Information classes

**Authored content** is narrative knowledge intentionally maintained by a person
or agent. **Structured content** is reusable data with stable fields and units.
**Journal content** is a raw dated observation or activity record. **Generated
content** is a deterministic view derived from canonical inputs. **Templates**
are scaffolds used to create source records and never completed records themselves.

### Canonical ownership

| Information | Canonical owner |
| --- | --- |
| Stable handbook narrative | `docs/` |
| Reusable facts, metrics, identifiers, and configuration | `data/` |
| Raw dated activities and observations | `journal/` |
| Generated summaries and their provenance | `reports/` |
| Reusable record scaffolds | `templates/` |
| Validation and transformation logic | `scripts/` |
| CI, release, and publishing orchestration | `.github/` |
| Issue state and acceptance criteria | Linear |
| Committed and release history | GitHub |

Derived views may repeat canonical information only through a documented,
reproducible transformation. Corrections belong in the canonical input.

## Target repository structure

### `docs/`

Owns authored, mobile-first handbook narrative and static published assets. The
target model separates shared knowledge from expedition-specific narrative under
stable expedition namespaces. It must not own reusable metrics, raw journal
entries, generated statistics presented as authored facts, or governance rules.
The existing numbered hierarchy remains unchanged in CDB-18; a later approved
migration may introduce shared and `expeditions/<expedition-id>/` sections.

### `data/`

Owns safe-to-commit YAML or JSON facts, metrics, identifiers, units, and
generation configuration. Shared values and expedition-specific values should be
separate and expedition values should use stable identifiers. It must not own
long narrative, raw diary prose, derived aggregates, secrets, private medical
documents, or precise private addresses. Schemas are future work, not part of
CDB-18.

### `journal/`

Owns raw dated activity, training, hiking, measurement, and observation entries.
Entries may reference identifiers from `data/` and may associate with one or more
expeditions. It must not own monthly or yearly summaries, readiness aggregates,
stable guidance, or current targets. Corrections must preserve the source
record's traceability.

### `reports/`

Contains generated monthly, yearly, readiness, expedition, and other summaries,
together with provenance. It has no independent authority: every substantive
value must be reproducible from canonical inputs. Reports must not be manually
corrected or contain new strategy decisions. Whether generated artifacts are
committed or created only during builds will be decided with the future generator.

### `templates/`

Contains reusable scaffolds for journal entries, expedition documents, and
reviews. Templates may define prompts and expected structure but do not own
completed records, live plans, canonical facts, or generated output. Completed
records belong in `journal/` or `docs/`.

### `scripts/`

Owns deterministic validation, generation, and migration logic. Scripts may read
canonical sources and write only declared generated or temporary targets. They
must not hide expedition strategy in constants, overwrite raw journal entries,
or contain secrets. CDB-18 creates no validators, generators, or migrations.

### `.github/`

Owns GitHub-specific validation, review, release, and publishing orchestration.
Workflows should call stable repository scripts instead of embedding domain logic.
This directory must not duplicate Linear issue state, canonical content, or
expedition strategy. CDB-18 creates no workflows.

## Multi-expedition model

Shared knowledge and catalogues should remain expedition-neutral. Each expedition
should receive a stable identifier used consistently by narrative, structured
data, journal associations, and reports. Adding an expedition must not require
copying shared training, nutrition, equipment, or safety guidance. The exact
directory migration and identifier catalogue require a separate design and issue.

## Data flow

Authors maintain narrative in `docs/`, reusable values in `data/`, and dated raw
records in `journal/`. Future scripts will validate those sources and derive
artifacts in `reports/` or a disposable build area. MkDocs will publish authored
pages plus explicitly selected generated views. GitHub workflows may later run
the same validation and publishing commands used locally.

## Generated-content boundaries

Generated artifacts must identify their generator, input scope, and generation
time where the format permits. They must be reproducible, visibly marked as not
hand-authored, and written only to declared targets. A correction is made to the
canonical source and regenerated. Generated readiness views may summarize
approved rules but must not invent medical or training recommendations.

## Automation boundaries

Future automation may validate formats, links, units, dates, identifiers, and
canonical references; aggregate journal metrics; generate approved summaries;
and build or publish the site. It must not silently alter expedition strategy,
overwrite raw observations, move canonical ownership, infer recommendations from
correlations, or store sensitive credentials or payloads.

## Garmin integration

Direct Garmin integration and speculative Garmin schemas are postponed. Several
months of manual records must first show which fields are consistently useful.
A later design must address authority, deduplication, corrections, timezones,
units, privacy, retention, authentication, idempotence, and failure recovery.

## Evolution and privacy

Future schemas and migrations should be versioned and preserve stable identifiers
and historical records. Secrets must come from environment variables or GitHub
secrets. API keys, access tokens, passwords, private medical documents, and
precise private addresses must never be committed.

## Related documents

Agent conduct is in `AGENTS.md`, contribution procedure in `CONTRIBUTING.md`, and
architectural rationale in `DECISIONS.md`. `ROADMAP.md` identifies follow-up
capabilities without replacing Linear, and `CHANGELOG.md` records delivery.
