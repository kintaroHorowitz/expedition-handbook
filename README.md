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

Python 3.12.x is required. Create an isolated environment and install the
dependencies:

```bash
python3.12 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

`requirements.txt` pins the complete environment: the direct MkDocs requirements
and their resolved transitive dependencies. Update these pins deliberately and
validate them in a fresh Python 3.12 environment; do not add unused plugins.

## Local preview

```bash
mkdocs serve
```

## Validation

```bash
python -m pip check
mkdocs build --strict
```

## Publication

The handbook is published at
<https://kintarohorowitz.github.io/expedition-handbook/>. Pull requests build the
site for validation without deploying it. A successful push to `main` deploys
the site automatically through GitHub Actions.

The repository must use **Settings → Pages → Build and deployment → Source:
GitHub Actions**. After a deployment, verify the published homepage, navigation,
search, theme, representative pages, and links on both a desktop browser and a
physical smartphone.

See `CONTRIBUTING.md` before making changes.
