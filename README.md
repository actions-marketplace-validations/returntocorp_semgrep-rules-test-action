# sgrep action

This action runs the tests for sgrep rules repos. Runs `make test`

## Inputs

None

## Outputs

### `results`

The test results

### `exit_code`

The exit code of `make test`

## Example usage

Put in `.github/workflows/sgrep-rules-test.yml`

```yaml
name: sgrep-rules-test

on: [push]

jobs:
  self_test:
    runs-on: ubuntu-latest
    name: A job to run sgrep rules tests
    steps:
      - uses: actions/checkout@v2
      - name: run sgrep rules tests
        id: sgrep-tests
        uses: returntocorp/sgrep-run-tests-action@master
      - name: Get the output from tests
        run: echo "results ${{ steps.sgrep-tests.outputs.results }}"
```
