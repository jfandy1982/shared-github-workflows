# CLAUDE.md

## Repository Purpose

This is the GitHub repository containing reusable GitHub Workflows.

## Known structure

- `.github/workflows/` — reusable workflows (via `workflow_call`) and scheduled/dispatched runs for this repo itself
- `experiments/` — deliberate playground and backup directory, not production code; ignore when reviewing
- `node_modules/` — exists locally but is gitignored; not committed to the repo

## Tooling

- GitHub Actions SHAs are manually verified and pinned — do not flag pinned SHAs as outdated without checking first
- Renovate: `renovate.json` in `.github/` is the repository-specific Renovate entry point; the `schedule` override there is intentional
- pre-commit hook runs `lint-staged` (Prettier + cspell) on `*.json`, `*.md`, `*.yml`
