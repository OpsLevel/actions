# setup-cli

This `opslevel/actions/setup-cli` actions is a [composite action](https://docs.github.com/en/actions/creating-actions/about-custom-actions#composite-actions)
that sets up the OpsLevel CLI in your GitHub Actions workflow.

## Usage

The default configuration installs the latest version of OpsLevel CLI:

```yaml
steps:
- uses: opslevel/actions/setup-cli@v1
```

A specific version of OpsLevel CLI can be installed:

```yaml
steps:
- uses: opslevel/actions/setup-cli@v1
  with:
    cli_version: "v2024.11.8"
```

## Inputs

The action supports the following inputs:

- `cli_version` - (optional) The version of OpsLevel CLI to install. Can be the git tag of any [release](https://github.com/OpsLevel/cli/releases) - invalid versions fail back to the latest release.
