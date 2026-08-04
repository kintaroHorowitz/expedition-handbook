# Expedition Handbook — Agent Instructions

## Project purpose

This repository contains a mobile-first MkDocs Material handbook for preparing:

- Tour des Écrins, planned for the final week of June 2027
- GR20, planned for 2028

The handbook combines:

- week-by-week training plans
- Achilles rehabilitation and load management
- strength and mobility routines
- hiking preparation
- nutrition and hydration
- backpack and equipment management
- route planning
- progress tracking and activity journals

## Source of truth

- Markdown documentation lives under `docs/`.
- Structured reusable data lives under `data/`.
- Activity and monthly reports live under `journal/`.
- Helper and generation scripts live under `scripts/`.
- Linear is the source of truth for issue status and acceptance criteria.
- GitHub is the source of truth for committed repository history.

Do not duplicate stable values across multiple files when they can be stored once
in structured data.

## Current main objective

Prepare for the Tour des Écrins during the final week of June 2027.

Current planning assumptions:

- target duration: 6 days
- target body weight: 105–110 kg
- current body weight at project creation: approximately 124 kg
- initial training limitation: healing Achilles tendon
- running must return progressively
- indoor cycling, walking, strength and mobility may continue while running is limited

These values may evolve. Prefer current structured data over this summary whenever
the two differ.

## Repository structure

Expected top-level structure:

- `docs/` — published MkDocs content
- `data/` — YAML or JSON source data
- `journal/` — dated training and hiking reports
- `scripts/` — automation and validation tools
- `.github/workflows/` — GitHub Actions
- `mkdocs.yml` — site configuration
- `requirements.txt` — Python dependencies
- `README.md` — contributor and local-development guide

Do not place published Markdown pages outside `docs/` unless they are repository
documentation such as `README.md` or `AGENTS.md`.

## Writing style

- Write clear, direct English.
- Prefer complete sentences.
- Use metric units.
- Use ISO dates in data and technical files: `YYYY-MM-DD`.
- Use readable dates in handbook prose when appropriate.
- Avoid motivational exaggeration and unsupported certainty.
- Clearly distinguish:
  - known facts
  - estimates
  - planning assumptions
  - medical or safety warnings
- Do not present the handbook as medical diagnosis or treatment.
- Keep pages easy to read on smartphones.
- Avoid very wide tables.
- Prefer short sections, checklists and collapsible details where useful.

## Markdown and MkDocs rules

- Every published page must have exactly one level-one heading.
- Use relative links between handbook pages.
- Do not add navigation entries that point to missing files.
- Use MkDocs Material features already enabled in `mkdocs.yml`.
- Use admonitions for warnings, important decisions and safety notes.
- Keep navigation labels short enough for mobile display.
- Do not introduce new MkDocs plugins without updating `requirements.txt` and
  documenting why they are required.

## Data rules

- Store weights in kilograms.
- Store distances in kilometres.
- Store elevation gain and loss in metres.
- Store durations in an unambiguous format.
- Never commit:
  - API keys
  - access tokens
  - passwords
  - private medical documents
  - precise private addresses
- Secrets must come from environment variables or GitHub secrets.

## Git and Linear workflow

Before changing files:

1. Read the relevant Linear issue and acceptance criteria.
2. Confirm the current branch.
3. Use the Linear-provided branch name when practical.
4. Inspect the existing implementation before editing.

During implementation:

- Stay within the issue scope.
- Do not silently redesign unrelated sections.
- Note any useful follow-up work rather than expanding scope indefinitely.
- Preserve user-authored content unless the task explicitly requires replacing it.

Commit format:

```text
CDB-<number> concise imperative description
