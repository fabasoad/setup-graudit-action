# Setup graudit action

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![Release](https://img.shields.io/github/v/release/fabasoad/setup-graudit-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-graudit-action/actions/workflows/functional-tests.yml/badge.svg)
![security](https://github.com/fabasoad/setup-graudit-action/actions/workflows/security.yml/badge.svg)
![linting](https://github.com/fabasoad/setup-graudit-action/actions/workflows/linting.yml/badge.svg)

This action installs [graudit](https://github.com/wireghoul/graudit) CLI tool.

## Supported OS

<!-- prettier-ignore-start -->
| OS      |                    |
|---------|--------------------|
| Windows | :white_check_mark: |
| Linux   | :white_check_mark: |
| macOS   | :white_check_mark: |
<!-- prettier-ignore-end -->

## Prerequisites

The following tools have to be installed for successful work of this GitHub Action:
[curl](https://curl.se).

## Inputs

```yaml
- uses: fabasoad/setup-graudit-action@v0
  with:
    # (Optional) graudit version. Defaults to the latest version.
    version: "3.7"
    # (Optional) If "false" skips installation if graudit is already installed.
    # If "true" installs graudit in any case. Defaults to "false".
    force: "false"
    # (Optional) GitHub token that is used to send requests to GitHub API such
    # as getting latest release. Defaults to the token provided by GitHub Actions
    # environment.
    github-token: "${{ github.token }}"
```

## Outputs

<!-- prettier-ignore-start -->
| Name      | Description                          | Example |
|-----------|--------------------------------------|---------|
| installed | Whether graudit was installed or not | `true`  |
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
      - uses: fabasoad/setup-graudit-action@v0
        with:
          version: 3.7
      - name: Print version
        run: graudit -v
```

### Result

```shell
Run graudit -v
graudit version: 3.7
```

## Contributions

![Alt](https://repobeats.axiom.co/api/embed/a34fe557eddd78e7b77a9f1237d1e1ee5c093a9d.svg "Repobeats analytics image")
