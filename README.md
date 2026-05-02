# setup-agentplane

<p>
  <a href="https://github.com/basilisk-labs/setup-agentplane/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/basilisk-labs/setup-agentplane/actions/workflows/ci.yml/badge.svg" /></a>
  <img alt="release" src="https://img.shields.io/github/v/release/basilisk-labs/setup-agentplane?sort=semver" />
  <img alt="release date" src="https://img.shields.io/github/release-date/basilisk-labs/setup-agentplane" />
</p>

**Topics:** `agentplane` `github-actions` `cli` `installer`

`setup-agentplane` is the fastest and most reliable way to add AgentPlane to CI.

It saves you from manual binary downloads, checksum errors, and cross-platform conditionals.
If your pipeline already uses GitHub Actions, this action gives a deterministic install step and a built-in smoke check.

## Why this exists

- Reproducible installs across runners and OSes.
- Fast onboarding for repositories that already follow agentic workflows.
- Reduced boilerplate in CI recipes.
- Predictable rollback by pinning exact versions.

## How it works

The action downloads the requested standalone AgentPlane artifact, checks SHA-256 against `SHA256SUMS` (when available), extracts it, and adds `agentplane` to PATH.

## Usage

```yaml
- uses: basilisk-labs/setup-agentplane@v0
  with:
    version: 0.4.1
```

Use `@v0` for automatic patch/minor refresh behavior, and pin to a concrete version when strict reproducibility is required.

## Inputs

| Name | Default | Description |
| --- | --- | --- |
| `version` | `0.4.1` | AgentPlane semver to install (for example `0.4.1`). |
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
      - name: Install AgentPlane
        uses: basilisk-labs/setup-agentplane@v0
        with:
          version: 0.4.1
          verify: true

      - name: Validate
        run: |
          agentplane --version
          agentplane quickstart
```

## Security note

Pin versions for immutable environments and keep `verify: true` in production.

## Next step

After installation run:

```bash
agentplane quickstart
```

to generate repository-level guidance and align contributors quickly.

## License

This action repository is MIT-licensed.
