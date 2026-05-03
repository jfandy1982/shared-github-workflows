# shared-github-workflows

Reusable GitHub Actions workflows for all repositories owned by [@jfandy1982](https://github.com/jfandy1982).

## Available Workflows

### Garbage Collection (`reusable-retention-workflow-runs.yml`)

Deletes all workflow runs (and their associated artifacts) in the calling repository. No age filter, no minimum — complete cleanup on every run.

**Usage in other repos:**

```yaml
jobs:
  retention:
    uses: jfandy1982/shared-github-workflows/.github/workflows/reusable-retention-workflow-runs.yml@main
```

The calling workflow is responsible for defining its own trigger (schedule, dispatch, etc.). No inputs required.
