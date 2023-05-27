# Setup graudit action

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![Release](https://img.shields.io/github/v/release/fabasoad/setup-graudit-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-graudit-action/actions/workflows/functional-tests.yml/badge.svg)
![pre-commit](https://github.com/fabasoad/setup-graudit-action/actions/workflows/pre-commit.yml/badge.svg)

This action installs [graudit](https://github.com/wireghoul/graudit) CLI tool.

## Prerequisites

The following tools have to be installed for successful work of this GitHub action:
[git](https://git-scm.com).

## Inputs

<!-- prettier-ignore-start -->
| Name    | Required | Description                                                                                       | Default | Possible values |
|---------|----------|---------------------------------------------------------------------------------------------------|---------|-----------------|
| version | No       | Version of `graudit` tool that can be found [here](https://github.com/wireghoul/graudit/releases) | `3.5`   | &lt;String&gt;  |
<!-- prettier-ignore-end -->

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
graudit version: 3.5
```
