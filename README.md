# Expedition Handbook

A mobile-first MkDocs Material handbook for preparing for Tour des Écrins in
2027, GR20 in 2028, and future expeditions.

## Repository guide

- `docs/` contains the published handbook.
- `ARCHITECTURE.md` defines repository and information ownership.
- `AGENTS.md` defines AI-agent responsibilities.
- `CONTRIBUTING.md` defines the contribution workflow.
- `DECISIONS.md` records durable technical decisions.

## Local setup

Create an isolated Python environment and install the pinned dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

## Local preview

```bash
mkdocs serve
```

## Validation

```bash
mkdocs build --strict
```

See `CONTRIBUTING.md` before making changes.
