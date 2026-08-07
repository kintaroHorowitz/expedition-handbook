# Contributing to Expedition Handbook

## Purpose

This file defines the operational contribution workflow. Behavioural constraints
are in `AGENTS.md`; repository ownership and data flow are in `ARCHITECTURE.md`.

## Before implementation

1. Read the Linear issue, acceptance criteria, and comments.
2. Run `git branch --show-current` before modifying any file.
3. Confirm that it is the Linear-provided issue branch and inspect the working
   tree state.
4. Read relevant architecture and decision records.
5. Inspect the existing implementation and identify required validation.

Significant technical features require a design proposal and approval before
implementation. Record durable approved technical decisions in `DECISIONS.md`.

## Protected-branch procedure

`main`, `master`, and explicitly protected branches are read-only by default. If
the branch check identifies a protected branch, stop before editing, staging,
committing, amending, rebasing, or pushing. Report the mismatch, then provide:

```bash
git switch <linear-issue-branch>
```

Use `git switch -c <linear-issue-branch>` when the issue branch does not yet
exist locally. General implementation or Git approval is not a protected-branch
exception; the user must explicitly name the protected branch and the exact
operation authorized.

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

Immediately before pushing, run `git branch --show-current` and confirm that it
exactly matches the Linear issue branch. Stop and report any mismatch. Push that
branch only when authorized, review the change against the acceptance criteria,
and request human review. Do not merge, publish, or update Linear state unless
the task explicitly authorizes that action.

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
