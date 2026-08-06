# stale

[![Release](https://img.shields.io/github/v/release/libnudget/stale?logo=github&label=latest)](https://github.com/libnudget/stale/releases)

Reusable GitHub Action for closing stale issues after a period of inactivity.

## Usage

```yaml
name: Close Stale Issues

on:
  schedule:
    - cron: '0 0 * * *'
  workflow_dispatch:

permissions:
  actions: write
  issues: write

jobs:
  close-stale-issues:
    runs-on: ubuntu-latest
    steps:
      - uses: libnudget/stale@v1
```

## Inputs

| Name | Required | Default | Notes |
| --- | --- | --- | --- |
| `days-before-stale` | No | 14 | Days without activity before marking as stale |
| `days-before-close` | No | 0 | Days after being marked stale before closing (0 = immediately) |
| `stale-issue-label` | No | stale | Label to add to mark issues as stale |
| `close-issue-message` | No | (see README) | Message to post when closing |
| `operations-per-run` | No | 100 | Maximum operations per run |
