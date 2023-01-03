# setup-state-tool

An action to install the ActiveState [State Tool](https://docs.activestate.com/platform/state/) CLI and add it to the `$GITHUB_PATH`.

This makes it easy to install projects from the ActiveState platform during a GitHub actions workflow.

## Inputs

| name  | type  | default  | description  | required  |
|---|---|---|---|---|
| version  | string  | latest  | Version of the State Tool CLI to install  | false  |
| channel  | string  | release  | Channel to download the State Tool CLI from  | false  |
| activestate-api-key  | string  |   | API key used to authenticate to the ActiveState platform  | true  |

## Examples

```yaml
name: "my workflow"
on:
  workflow_dispatch:

jobs:
  install-state-tool-cli:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: gscho/setup-state-tool
      with:
        activestate-api-key: foobar
    - name: run help command
      run: state --help
```
