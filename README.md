# setup-agentplane

Install AgentPlane in GitHub Actions.

```yaml
steps:
  - uses: basilisk-labs/setup-agentplane@v0.4.1
    with:
      version: 0.4.1
```

This generated action installs AgentPlane through the release `install.sh` asset, which verifies
the npm tarball checksum before installing the CLI.

## Inputs

| Name | Default | Description |
| --- | --- | --- |
| `version` | `0.4.1` | AgentPlane version to install. |
| `verify` | `true` | Run `agentplane --version` after installation. |
