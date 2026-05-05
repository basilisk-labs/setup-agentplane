# setup-agentplane

[![CI](https://github.com/basilisk-labs/setup-agentplane/actions/workflows/ci.yml/badge.svg)](https://github.com/basilisk-labs/setup-agentplane/actions/workflows/ci.yml)
![release](https://img.shields.io/github/v/release/basilisk-labs/setup-agentplane?sort=semver)
![release-channel](https://img.shields.io/github/release-date/basilisk-labs/setup-agentplane)

Install AgentPlane in GitHub Actions.

```yaml
- uses: basilisk-labs/setup-agentplane@v0.4.4
  with:
    version: 0.4.4
```

This composite action installs AgentPlane from the official Bun single-file executable archives and validates each archive checksum before adding `agentplane` to PATH.

## Capabilities

- Deterministic install by release asset pin (run uses release asset URL)
- Cross-platform: macOS/Linux/Windows
- Smoke check with agentplane --version
- Explicit version control (no floating tags needed)

## Quick start

```yaml
steps:
  - uses: basilisk-labs/setup-agentplane@v0.4.4
    with:
      version: 0.4.4
```

## Smoke check

```bash
agentplane --version
```
