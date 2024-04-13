# Setup graudit action

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![Release](https://img.shields.io/github/v/release/fabasoad/setup-graudit-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-graudit-action/actions/workflows/functional-tests.yml/badge.svg)
![security](https://github.com/fabasoad/setup-graudit-action/actions/workflows/security.yml/badge.svg)
![linting](https://github.com/fabasoad/setup-graudit-action/actions/workflows/linting.yml/badge.svg)

This action installs [graudit](https://github.com/wireghoul/graudit) CLI tool.

## Prerequisites

The following tools have to be installed for successful work of this GitHub action:
[git](https://git-scm.com).

## Inputs

<!-- prettier-ignore-start -->
| Name    | Required | Description                                                                                       | Default | Possible values |
|---------|----------|---------------------------------------------------------------------------------------------------|---------|-----------------|
| version | No       | Version of `graudit` tool that can be found [here](https://github.com/wireghoul/graudit/releases) | `3.6`   | &lt;String&gt;  |
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
      - uses: actions/checkout@v4
      - uses: fabasoad/setup-graudit-action@v0
        with:
          version: 3.6
      - name: Print version
        run: graudit -v
```

### Result

```shell
Run graudit -v
graudit version: 3.6
```
