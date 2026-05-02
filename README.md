# setup-agentplane

<p>
  <a href="https://github.com/basilisk-labs/setup-agentplane/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/basilisk-labs/setup-agentplane/actions/workflows/ci.yml/badge.svg" /></a>
  <img alt="release" src="https://img.shields.io/github/v/release/basilisk-labs/setup-agentplane?sort=semver" />
  <img alt="release date" src="https://img.shields.io/github/release-date/basilisk-labs/setup-agentplane" />
</p>

**Topics:** `agentplane` `github-actions` `cli` `installer`

## Discovery chips

- `agentplane`
- `github-actions`
- `cli`
- `installer`
- `npm`
- `standalone`

GitHub Action to install the AgentPlane CLI in GitHub Actions runners using
official standalone release artifacts.

## Usage

```yaml
- uses: basilisk-labs/setup-agentplane@v0
  with:
    version: 0.4.1
```

Use a major tag (`@v0`) for reproducible installs and pin to exact versions when full immutability is required.

## Inputs

| Name | Default | Description |
| --- | --- | --- |
| `version` | `0.4.1` | AgentPlane semver to install (e.g. `0.4.1`). |
| `verify` | `true` | Run `agentplane --version` after installation. |

## Outputs

This action intentionally has no outputs.

## Quick start

```yaml
name: ci
on: [push]

jobs:
  install:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: basilisk-labs/setup-agentplane@v0
        with:
          version: 0.4.1
          verify: true
```

## Smoke check

```yaml
agentplane --version
```

## Security note

Use a fixed `version` and leave `verify: true` to ensure `agentplane --version` smoke checks pass.

### License

This action repository is MIT-licensed.
