# Setup Promtool in GitHub Actions

[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/nhedger/setup-promtool?label=latest&logo=github&labelColor=374151&color=60a5fa)](https://github.com/marketplace/actions/setup-promtool)
[![Test](https://github.com/nhedger/setup-promtool/actions/workflows/test.yaml/badge.svg)](https://github.com/nhedger/setup-promtool/actions/workflows/test.yaml)
[![Integrate](https://github.com/nhedger/setup-promtool/actions/workflows/integrate.yaml/badge.svg)](https://github.com/nhedger/setup-promtool/actions/workflows/integrate.yaml)

**Setup Promtool** is a GitHub action that provides a cross-platform interface
for setting up the [Promtool CLI](https://prometheus.io/docs/prometheus/latest/command-line/promtool/) in GitHub
Actions runners.

## Inputs

The following inputs are supported.

```yaml
- name: Setup Promtool
  uses: nhedger/setup-promtool@v1
  with:

    # The version of Prometheus for which to install the Promtool CLI.
    # This input is optional and by default the version will be automatically
    # detected from the project's dependencies. If no version is specified, the # latest version of Promtool will be installed.
    # Example values: "3.4.1", "latest"
    version: ""

    # The GitHub token to use to authenticate GitHub API requests.
    # This input is optional and defaults to the job's GitHub token.
    # Example value: ${{ secrets.GITHUB_TOKEN }}
    token: ${{ github.token }}
```

## Examples

### Latest version

Setup the latest version of Promtool

```yaml
- name: Setup Promtool
  uses: nhedger/setup-promtool@v1
  with:
    version: latest

- name: Run Promtool
  run: promtool --version
```

### Specific version

Install version `3.4.1` of Promtool

```yaml
- name: Setup Promtool
  uses: nhedger/setup-promtool@v1
  with:
    version: 3.4.1

- name: Run Promtool
  run: promtool --version
```

## License

Copyright © 2025, Nicolas Hedger. Released under the [MIT License](LICENSE.md).