# CLAUDE.md

## Repository Purpose

This is the GitHub repository containing reusable GitHub Workflows.

## Known structure

- `.github/workflows/` — two types of files:
  - Reusable workflows: `reusable-<purpose>-<scope>.yml` — callable via `workflow_call` from other repos
  - Local orchestrators: `<purpose>.yml` — triggers scoped to this repo only
- `.github/actions/` — composite actions (not yet created, reserved for future use)
- `experiments/` — deliberate playground and backup directory, not production code; ignore when reviewing
  - `experiments/superpowers/` — brainstorming specs and implementation plans from Claude sessions (gitignored, local only); check here for prior design decisions before starting new work
- `node_modules/` — exists locally but is gitignored; not committed to the repo

## Tooling

- GitHub Actions SHAs are manually verified and pinned — do not flag pinned SHAs as outdated without checking first
- Renovate: `renovate.json` in `.github/` is the repository-specific Renovate entry point; the `schedule` override there is intentional
- pre-commit hook runs `lint-staged` (Prettier + cspell) on `*.json`, `*.md`, `*.yml`; additionally runs `js-yaml` syntax validation on `*.yml`, `*.yaml`
- Workflow `name:` field convention: `Reusable - <Purpose>` for reusable workflows, `Local <Purpose>` for orchestrators
