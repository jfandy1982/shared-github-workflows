# shared-github-workflows

Reusable GitHub Actions workflows for all repositories owned by [@jfandy1982](https://github.com/jfandy1982).

## Available Workflows

### Garbage Collection (`retention_period.yml`)

Deletes outdated workflow runs based on a configurable retention period.

**Usage in other repos:**

```yaml
jobs:
  retention:
    uses: jfandy1982/shared-github-workflows/.github/workflows/retention_period.yml@main
    with:
      days: '30'
```

**Inputs:**

| Input | Required | Default | Description |
| --- | --- | --- | --- |
| `days` | no | `30` | Retention period in days |
| `keep_minimum_runs` | no | `5` | Minimum runs to keep regardless of age |
