# Setup Helm Docs Action
This action installs [norwoodj/helm-docs](https://github.com/norwoodj/helm-docs), a tool for automatically generating markdown documentation for Helm charts.

## Usage

### Inputs
| Name      | Description                      | Required | Default               |
|-----------|----------------------------------|----------|-----------------------|
| `version` | The Helm Docs version to install | `false`  | `latest`              |
| `token`   | GitHub token                     | `false`  | `${{ github.token }}` |

### Outputs
| Name      | Description                              |
|-----------|------------------------------------------|
| `version` | The Helm Docs version that was installed |

## Example Workflow
```yaml
name: Update Chart Metadata

on: push

jobs:
  update-chart-metadata:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: gabe565/setup-helm-docs-action@v1
      - run: helm-docs
```
