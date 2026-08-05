# Contributing to Expedition Handbook

## Purpose

This file defines the operational contribution workflow. Behavioural constraints
are in `AGENTS.md`; repository ownership and data flow are in `ARCHITECTURE.md`.

## Before implementation

1. Read the Linear issue, acceptance criteria, and comments.
2. Confirm the branch and working-tree state.
3. Use the Linear-provided branch when practical.
4. Read relevant architecture and decision records.
5. Inspect the existing implementation and identify required validation.

Significant technical features require a design proposal and approval before
implementation. Record durable approved technical decisions in `DECISIONS.md`.

## Implementation

Keep changes within issue scope, preserve unrelated and user-authored work, and
follow canonical ownership from `ARCHITECTURE.md`. Record follow-up needs rather
than silently expanding scope.

## Validation

Run checks appropriate to the files changed. Documentation changes must verify
Markdown structure and links and pass:

```bash
mkdocs build --strict
```

Inspect the final diff and run `git status --short` before committing. Document
any check that could not be executed.

## Commits

Use an imperative commit subject:

```text
CDB-<number> concise imperative description
```

Keep commits scoped to the issue and do not include generated or local artifacts
unless the architecture explicitly requires them.

## Push and review

Push the Linear branch only when authorized. Review the pushed change against the
acceptance criteria and request human review. Do not merge, publish, or update
Linear state unless the task explicitly authorizes that action.

## Publication workflow

Pull requests run the pinned dependency checks and strict MkDocs build without
deploying. Successful pushes to `main` deploy the site to GitHub Pages. The
repository setting **Settings → Pages → Build and deployment → Source** must be
set to **GitHub Actions**.

After deployment, manually verify the published homepage, navigation, search,
theme, representative pages, and links in a desktop browser and on a physical
smartphone.

## Completion checklist

- Acceptance criteria are satisfied.
- Required checks, including the strict build, pass.
- The final diff contains only intended changes.
- The worktree has no unexplained changes.
- Authorized commit and push steps are complete.
- Review and any authorized Linear update remain traceable.
