# Expedition Handbook Technical Roadmap

## Purpose

This roadmap describes broad technical capability direction. It is not an issue
tracker, delivery commitment, or expedition timeline; Linear owns actionable
work and acceptance criteria.

## Foundation

- Establish concise governance and architecture documents.
- Maintain reproducible local setup and strict MkDocs validation.
- Add automation only through separately approved issues.

## Information architecture

- Plan migration from the existing numbered handbook hierarchy to shared and
  expedition-specific namespaces.
- Define stable expedition identifiers and safe structured-data boundaries.
- Define journal and template conventions after representative manual entries exist.

## Validation and reporting

- Add schemas and validation in a dedicated issue.
- Add deterministic generators and provenance checks in a dedicated issue.
- Decide whether generated reports are committed or build-only artifacts.
- Add GitHub validation and publishing workflows after local commands stabilize.

## Multi-expedition support

- Introduce new expeditions without copying shared guidance.
- Preserve historical journal entries and stable identifiers through migrations.
- Provide expedition-specific generated views from shared canonical inputs.

## Deferred integrations

Direct Garmin integration remains deferred until several months of manual records
demonstrate stable, useful fields and reconciliation requirements. Any integration
requires a separate design proposal and issue.
