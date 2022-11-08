# Setup graudit action

![Release](https://img.shields.io/github/v/release/fabasoad/setup-graudit-action?include_prereleases)
![Functional Tests](https://github.com/fabasoad/setup-graudit-action/workflows/Functional%20Tests/badge.svg)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/fabasoad/setup-graudit-action/main.svg)](https://results.pre-commit.ci/latest/github/fabasoad/setup-graudit-action/main)

This action installs [graudit](https://github.com/wireghoul/graudit) CLI tool.

## Prerequisites

The following tools have to be installed for successful work of this GitHub action:
[git](https://git-scm.com).

## Inputs

| Name    | Required | Description                                                                                       | Default | Possible values |
|---------|----------|---------------------------------------------------------------------------------------------------|---------|-----------------|
| version | No       | Version of `graudit` tool that can be found [here](https://github.com/wireghoul/graudit/releases) | `3.4`   | &lt;String&gt;  |

## Example usage

### Workflow configuration

```yaml
name: Test

on: push

jobs:
  setup:
    name: graudit
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@main
      - uses: fabasoad/setup-graudit-action@main
        with:
          version: 3.4
      - name: Print version
        run: graudit -v
```

### Result

```shell
Run graudit -v
graudit version: 3.4
```
